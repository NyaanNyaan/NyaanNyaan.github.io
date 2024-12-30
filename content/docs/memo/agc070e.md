---
title: "AGC070E 裏話(ネタバレ注意)"
description: ""
lead: ""
date: 2024-12-31T00:00:00+09:00
lastmod: 2024-12-31T00:00:00+09:00
draft: false
images: []
menu: 
  docs:
    parent: "memo"
weight: 999
toc: true
---

AGC070 E は元々は "Remove Three Edges" という題名の原案でした。つまり、今の問題の $K = 1$ 版でした。

$K = 1$ 版は想定解を気に入っていたのと個人的に何度か挫折した末に解けたので思い入れがあったのですが、10 日前くらいに maroon さんに $K$ 一般で解けることを指摘されて強化された結果、幻のバージョンに…

というわけで没になった $K = 1$ 版ですが、既に書き終えていた editorial が存在するのでこちらで公開します。

(以下、ネタバレ注意)

--------

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

## Editorial

はじめに数え上げる対象を整理します。まず、次の事実が証明できます。

> 木 $T$ が条件を満たすとする。$T$ の辺を長さ $3$ のパス $N$ 本に分割して、全てのパスに対して真ん中の辺(パスの端点を含まない辺)を青く塗る。この時、$T$ のパスをどのように分解しても、青く塗られる辺の集合は変わらない。

正当性は $T$ の根を任意に取って深さが最大の葉を端点とするパスに注目することで示せます。  
この事実により、結局次の条件を満たすグラフを数え上げる問題になります。

> #### 言い換え後の問題
> 
> 辺に赤色か青色が塗られた $3N+1$ 頂点の木であって次の条件を全て満たすものの個数は？
>
> - 辺のうち $N$ 本が青く、$2N$ 本が赤く塗られている。
> - (赤い辺)-(青い辺)-(赤い辺) からなるパス $N$ 本に分割することが出来る。 

この問題を直接解くのは少し難しいと考えられるので、まずは青い辺が連結である場合を解くことにします。そうすると条件はさらに具体的に書けて、次の問題になります。

> #### 部分問題 1
> 
> 辺に赤色か青色が塗られた $3m+1$ 頂点の木であって次の条件を全て満たすものの個数は？
>
> - 辺のうち $m$ 本が青く、$2m$ 本が赤く塗られている。
> - **青い辺と青い辺に隣接する頂点からなるグラフは連結である。**
> - **全ての青い辺に隣接する頂点について、(隣接する青い辺の本数) と (隣接する赤い辺の本数) が一致する。**

部分問題 1 の答えを $U_m$ と置きます。目標は $U_1, U_2, \dots, U_N$ を列挙することです。  
$U_m$ を計算するために適宜式変形すると、部分問題 2 が登場します。

> #### 部分問題 2
> 
> $n$ 頂点の無向木の重みを $\prod_{1 \leq i \leq n} \frac{1}{\deg(i)!}$ として定義する。($\deg(i)$ は頂点 $i$ の次数)  
> $n$ 頂点の木 $n^{n-2}$ 通り全てに対して重みを足し合わせた値は？

部分問題 2 の答えを $T_n$ と置くと、$U$ と $T$ の間には

$$U_n = \binom{3n+1}{n+1} \cdot (2n)! \cdot T_{n+1}$$

という関係式が成り立ちます。よって $U_1, U_2, \dots, U_N$ を列挙するためには $T_2, T_3, \dots, T_{N+1}$ を列挙すればよいことがわかります。

$T_n$ を pruefer code を利用して計算します。頂点 $i$ の次数が $d_i$ であるような木の個数は

$$\binom{n-2}{d_1-1, d_2-1, \dots, d_n -1}$$

であり、この木の重みが $\frac{1}{d_1! d_2! \dots d_n!}$ となるようにすればよいです。よって $T_n$ は次式で表せます。

$$
\begin{aligned}
T_n &= (n-2)! \times [x^{2n-2}] \left( \sum_{m \geq 1} \frac{x^m}{(m-1)!m!}\right)^n \newline
&= \left\lbrack \frac{x^{n-2}}{(n-2)!} \right\rbrack \left( \sum_{m \geq 0} \frac{x^m}{m!(m+1)!}\right)^n
\end{aligned}
$$

この式は $T_n$ が 1 個しか計算できないのでこの式をそのまま用いて $T_n$ を列挙すると計算量が破綻します。そこでラグランジュの反転公式を使います。反転公式を振り返ると、$f(x), g(x)$ が逆関数の関係にある時に

$$\lbrack x^n \rbrack h(f(x)) = \frac{1}{n} \lbrack x^{n-1} \rbrack h^{\prime}(x) \left(\frac{x}{g(x)}\right)^n$$

が成り立つ、というものが反転公式でした。よって

$$f(x) = x\left( \sum_{m \geq 0} \frac{f(x)^m}{m!(m+1)!}\right)$$

$$g(x) = \frac{x} {\sum_{m \geq 0} \frac{x^m}{m!(m+1)!}}$$

とおくと $g(f(x)) = x$ が成り立ち $f(x), g(x)$ は逆関数の関係となるので反転公式を適用できます。

$$h(x) = \frac{x^2}{2}$$

も合わせると、

$$
\begin{aligned}
&T_n \newline
&= \left\lbrack \frac{x^{n-2}}{(n-2)!} \right\rbrack \left( \sum_{m \geq 0} \frac{x^m}{m!(m+1)!}\right)^n \newline
&= n\cdot (n-2)! \cdot \frac{1}{n} \lbrack x^{n-1} \rbrack  x \left( \sum_{m \geq 0} \frac{x^m}{m!(m+1)!}\right)^n\newline
&= n\cdot (n-2)! \cdot \frac{1}{n} \lbrack x^{n-1} \rbrack h^{\prime}(x) \left(\frac{x}{g(x)}\right)^n \newline
&= n\cdot (n-2)! \cdot \lbrack x^n \rbrack h(f(x))
\end{aligned}
$$

となります。以上より

$$f(x) = x\left( \sum_{m \geq 0} \frac{f(x)^m}{m!(m+1)!}\right)$$

を満たす $f(x)$ を高速に計算すれば $T_n$ を列挙できることがわかりました。

今年、2024 年において $f(x)$ を最も手っ取り早く計算する方法は、今年発見された Kinoshita-Li algorithm (あるいは noshi91-Elegia algorithm と呼んだ方が聞き覚えがある名前かもしれませんね) を利用する方法です。

- Kinoshita と Li は関数合成および逆関数の計算を(次数を $N$ として) $\mathrm{O}(N \log^2 N)$ で計算するアルゴリズムを発見しました。Kinoshita と Li の論文や CodeForces での関連記事などは [maspy さんの記事](https://codeforces.com/blog/entry/128814) に関連リンクがまとまっているのでそちらをご参照ください。
 
$f(x)$ は $g(x)$ の逆関数で、$g(x)$ の係数は既知なので、上記のアルゴリズムを用いれば $f(x)$ の $N$ 次までの係数を $\mathrm{O}(N \log^2 N)$ で十分高速に計算できます。  
それはそれとして、この解説では Kinoshita-Li algorithm を使用せずに $f(x)$ を  $\mathrm{O}(N \log^2 N)$ で計算する方法を説明します。(余談ですがこの問題が完成したのは 2023 年のことで、当時は逆関数の計算が $\mathrm{O}(N \log^2 N)$ で出来ることになるとはゆめにも思わない時期でした)  
さて、$P(x)$ を次のように置きます。

$$P(x) = \sum_{m \geq 0} \frac{x^m}{m!(m+1)!}$$

すると $f(x)$ は

$$G(f) = x P(f) - f = 0$$

という式を満たすので、ニュートン法、すなわち

$$f \gets f - \frac{G(f)}{G^{\prime}(f)}$$

という操作の反復により計算することが出来ます。ニュートン法の計算に必要なのは

$$G(f) = xP(f) - f, G^{\prime}(f)=xP^{\prime}(f)-1$$

なので、$f \bmod{x^k}$ が与えられたときに $P(f), P^{\prime}(f) \bmod{x^{2k}}$ を高速に計算できればよいです。$P(f)$ がわかれば $P^{\prime}(f)$ は chain rule により容易に計算できるので、以降では $f$ が与えられた時に $P(f)$ を計算するアルゴリズムを説明します。

まず、数列 $(\frac{1}{m!(m+1)!})_{m \geq 0}$ は P-recursive である事に注目すると、$P(x)$ は D-finite 、すなわち多項式係数の微分方程式で表せることがわかります。少し計算すると次の微分方程式を得られます。

$$2P^{\prime}(x) + xP^{\prime\prime}(x) = P(x)$$

よって $2P^{\prime}(f) + f P^{\prime\prime}(f) = P(f)$ という関係式を得られますが、このままでは効率的な計算が出来ません。  
(以下では簡単のため $\frac{d}{dx}\left(f(x)\right)$ を $f(x)^{\prime}$ と書き $f^{\prime}(x)$ と区別することにする。)分割統治 FFT をするために $P^{\prime}(f), P^{\prime\prime}(f)$ を $P(f)^{\prime}, P(f)^{\prime\prime}$ に置き換えます。$P(f(x))$ の微分を考えると

$$P(f)^{\prime} = P^{\prime}(f)f^{\prime}$$

$$P(f)^{\prime\prime} = P^{\prime\prime}(f)f^{\prime 2} + P^{\prime}(f)f^{\prime\prime}$$

なので

$$P^{\prime}(f) = \frac{P(f)^{\prime}}{f^{\prime}}$$

$$P^{\prime\prime}(f) = \frac{P(f)^{\prime\prime}f^{\prime} - P(f)^{\prime}f^{\prime\prime}}{f^{\prime 3}}$$

です。これを微分方程式に代入すると

$$P(f) f^{\prime 3} = 2 P(f)^{\prime} f^{\prime 2} + f (P(f)^{\prime\prime}f^{\prime} - P(f)^{\prime}f^{\prime\prime})$$

となり、$P^{\prime}(f), P^{\prime\prime}(f)$ を $P(f)^{\prime}, P(f)^{\prime\prime}$ に置き換えることができました。簡単のため $P(f) = Q, A = f^{\prime 3}, B = ff^{\prime\prime}-2f^{\prime 2},C=-ff^{\prime}$ と置き換えると

$$QA + Q^{\prime}B + Q^{\prime\prime}C = 0$$

となり、この式は分割統治 FFT が可能です。  
注意点も多いので分割統治 FFT の内容をもう少し深く掘り下げておきます。上式の $x^n$ の係数に注目すると

$$\left(\sum_{i=0}^n q_i A_{n-i} \right) + \left(\sum_{i=0}^n (i+1)q_{i+1}B_{n-i}\right) + \left(\sum_{i=0}^n (i+2)(i+1)q_{i+2}C_{n-i} \right)=0$$

で、$q_{n+1}, q_{n+2}$ が出て来る項のみを開くと

$$
\begin{aligned}
&\left(\sum_{i=0}^n q_{i} A_{n-i}\right)+ \newline
&\left(\sum_{i=0}^{n-1} (i+1) q_{i+1} B_{n-i}\right)+ \newline
&\left(\sum_{i=0}^{n-2} (i+2)(i+1) q_{i} C_{n-i}\right)+ \newline
&((n+1)B_0 + (n+1)n \cdot C_1) q_{n+1} + \newline
&(n + 2)(n + 1) C_0 q_{n+2}
=0
\end{aligned}
$$

を得ます。ここで、簡単な計算により $f(x)$ は

$$f(x) = x + \frac{1}{2} x^2 + \mathrm{O}(x^3)$$

を満たすことがわかるので、ニュートン法の初期解を $f(x) = x + \frac{1}{2}x^2$ から開始することにします。そうすると $C_0, C_1, B_0$ の係数が一意に定まり、

$$B_0 = -2, C_0 = 0, C_1 = -1$$

となります。これらを式に代入して整理すると

$$
\begin{aligned}
&\left(\sum_{i=0}^n q_{i} A_{n-i}\right)+ \newline
&\left(\sum_{i=1}^{n} i q_{i} B_{n+1-i}\right)+ \newline
&\left(\sum_{i=2}^{n} i(i-1) q_{i} C_{n+2-i}\right)\newline
&=(n+1)(n+2) q_{n+1}
\end{aligned}
$$

となりこの式は分割統治 FFT (relax convolution) をそのまま適用できる式になっています。

以上の内容を適切に実装することで $U_1, U_2, \dots, U_N$ を $\mathrm{O}(N \log^2 N)$ で計算することが出来ました。この値をもとに言い換え後の問題(以下に再掲しました)を解くことにします。

> #### 言い換え後の問題
> 
> 辺に赤色か青色が塗られた $3N+1$ 頂点の木であって次の条件を全て満たすものの個数は？
>
> - 辺のうち $N$ 本が青く、$2N$ 本が赤く塗られている。
> - (赤い辺)-(青い辺)-(赤い辺) からなるパス $N$ 本に分割することが出来る。 

さて、$U_1, U_2, \dots, U_N$ の情報を生かすためにグラフを捉え直します。まず、適当に根を取ってグラフを根付き木とみなします。そして、グラフを「青い辺からなる $m$ 辺の連結成分 + それに付随する $2m$ 辺の赤い辺および隣接する頂点」からなる virtual な頂点を根とする木たちに分解します。そして分解後に青い辺に隣接する頂点を青い頂点、そうでない頂点を赤い頂点と呼びます。詳しくは下図を参考にしてください。(四角い頂点が virtual な頂点です。また、1 つの木に対して根を決め打った時に分解が一意に定まることは明らかです。)

![image](https://img.atcoder.jp/agc070/5ec1868c4a9112adb9fd7d3c0cdd5bd3.jpg)

このように言い換えて、数え上げる木の頂点ラベルは 「virtual な頂点、あるいは $1, 2, \dots, 3N$」を張ったものとして数えることにして問題ないです。また、virtual な頂点とその頂点に対応する virtual でない頂点 (図で言う四角い頂点とそこに隣り合う丸い頂点) の色の関係性を考えると、

- virtual な赤い頂点は virtual でない赤い頂点・青い頂点に対応付けられる一方、
- virtual な青い頂点は virtual でない赤い頂点にしか対応付けられない(青い頂点はダメ) こと、および
- virtual な青い頂点が 2 個以上同じ箇所に対応してはいけない

ことが確認できます。

以上のような事実を踏まえた上で、数え上げの対象を母関数で表します。  
$F_n, G_n, R_n, B_n$ を次のように定義します。

- $F_n$ : virtual な頂点の次数が $1$ で赤い頂点であるような $3n+1$ 頂点のグラフの個数
- $G_n$ : virtual な頂点の次数が $1$ で青い頂点であるような $3n+1$ 頂点のグラフの個数
- $R_n$ : virtual な頂点は高々 $1$ 個の青い頂点と任意の個数の赤い頂点が重なってできたものであるような $3n+1$ 頂点のグラフの個数
- $B_n$ : virtual な頂点は任意の個数の赤い頂点が重なってできたものであるような $3n+1$ 頂点のグラフの個数

求めたい答えは $R_N$ です。

$F_n$ の母関数 $F(x)$ を $\left\lbrack \frac{x^n}{(3n)!}\right\rbrack F(x) = F_n$ となるように定義します。($G(x), R(x), B(x)$ も同様) すると考察を重ねることにより次の関係式が成り立つことがわかります。

$$
\begin{aligned}
F_n &= (3n)! \sum_{k = 1}^n \frac{2k U_k}{(3k + 1)!} \lbrack x^{n-k} \rbrack R(x)^{2k-1} B(x)^{k+1} \newline
G_n &= (3n)! \sum_{k = 1}^n \frac{(k+1) U_k}{(3k + 1)!} \lbrack x^{n-k} \rbrack R(x)^{2k} B(x)^{k} \newline
R_n &= \left\lbrack \frac{x^n}{(3n)!} \right\rbrack \exp(F(x)) (1 + G(x)) \newline
B_n &= \left\lbrack \frac{x^n}{(3n)!} \right\rbrack \exp(F(x))
\end{aligned}
$$

これを母関数同士の関係式で表すと

$$
\begin{aligned}
F(x) &= \sum_{k = 1}^\infty \frac{2k U_k}{(3k + 1)!} R(x)^{2k-1} B(x)^{k+1} x^k \newline
G(x) &= \sum_{k = 1}^\infty \frac{(k+1) U_k}{(3k + 1)!} R(x)^{2k} B(x)^{k} x^k \newline
R(x) &= \exp(F(x)) (1 + G(x)) \newline
B(x) &= \exp(F(x))
\end{aligned}
$$

となり、$R(x), B(x)$ の式を $F(x), G(x)$ の式に代入することで

$$
\begin{aligned}
F(x) &= \sum_{k=1}^\infty \frac{2k U_k}{(3k + 1)!} \exp(3k F )(G+1)^{2k-1} x^k \newline
G(x) &= \sum_{k=1}^\infty \frac{(k+1)U_k}{(3k + 1)!} \exp(3k F) (G+1)^{2k} x^k
\end{aligned}
$$

を得られて、この式を上手く解くことが出来ればよいです。

ここで $\exp(3F(x)) (G(x)+1)^2 x = z$ と変数変換します。すると

$$
\begin{aligned}
F(G + 1) &= \sum_{k=1}^\infty \frac{2k U_k}{(3k + 1)!} z^k \newline
G &= \sum_{k=1}^\infty \frac{(k + 1)U_k}{(3k+1)!} z^k
\end{aligned}
$$

となるので、$F, G$ を $z$ で表現した時の式を得られます。これを $\hat{F}(z), \hat{G}(z)$ とします。そしてここから $x$ と $z$ の関係式

$$x = \frac{z}{\exp(3\hat{F}(z)) (\hat{G}(z) + 1)^2} := \hat{S}(z)$$

が得られます。

$x$ と $z$ の関係式が得られたので後は反転公式を利用すればよいです。すなわち、$x=\hat{S}(z)$ の逆関数を $z=\hat{S}^{\langle -1 \rangle}(x)$ と表し、また 

$$R(x) = \exp(F(x)) (1 + G(x)) = \exp(\hat{F}(z)) (1 + \hat{G}(z)) := \hat{R}(z)$$

と置くと

$$
\begin{aligned}
[x^N] R(x) 
&= [x^N] \hat{R}(z) \newline
&= [x^N] \hat{R}(\hat{S}^{\langle -1 \rangle}(x)) \newline
&= \frac{1}{N} \lbrack x^{N-1} \rbrack \hat{R}^{\prime}(x) \left( \frac{x}{\hat{S}(x)} \right)^{N}
\end{aligned}
$$

であり、$\hat{R}(x), \hat{S}(x)$ は既知の式なので計算できます。(なお、オーバーキル気味の別解として、$\hat{S}(z)$ を得られた時点で先述した Kinoshita-Li を利用して全てを逆関数と関数合成で処理する方法でも解けます。)

以上よりこの問題を $\mathrm{O}(N \log^2 N)$ で解くことが出来て、これは十分高速です。
