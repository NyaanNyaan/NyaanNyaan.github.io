---
title: "公式集"
description: ""
lead: ""
date: 2021-05-05T02:52:07+09:00
lastmod: 2021-05-05T02:52:07+09:00
draft: true
images: []
menu: 
  docs:
    parent: "FPS"
weight: 999
toc: true
---

形式的冪級数の公式をまとめた。

### 前提知識

数列 $(a_n)_{n \geq 0}$ の **OGF(通常型母関数)** $A(x)$ は

$$A(x) = \sum_{n \geq 0} a_n x^n$$

で定義される。OGF の第 $N$ 項を取得する作用素を $\lbrack x^N \rbrack$ で表し、

$$\lbrack x^N \rbrack A(x) = a_n$$

のように使用する。

数列 $(a_n)_{n \geq 0}$ の **EGF(指数型母関数)** $\hat{A}(x)$ は

$$\hat{A}(x) = \sum_{n \geq 0} \frac{a_n}{n!} x^n$$

で定義される。OGF の第 $N$ 項を取得する作用素を $\left\lbrack \frac{x^N}{N!} \right\rbrack$ で表し、

$$\left\lbrack \frac{x^N}{N!} \right\rbrack \hat{A}(x) = a_n$$

のように使用する。

### OGF

$[\mathrm{cond}]$ は $\mathrm{cond}$ が真の時に $1$、偽の時に $0$ を取る関数である。

|数列|一般項|母関数|
|:---:|:---:|:---:|
|$1,0,0,0,0,\ldots$|$[n=0]$|$1$|
|$1,1,1,1,1,\ldots$|$1$|$\frac{1}{1-x}$|
|$1,2,3,4,5,\ldots$|$n+1$|$\frac{1}{(1-x)^2}$|
|$1,3,6,10,15,\ldots$|$\binom{n+2}{2}$|$\frac{1}{(1-x)^3}$|
|$1,4,10,20,35,\ldots$|$\binom{n+3}{3}$|$\frac{1}{(1-x)^4}$|
|$1,k,\frac{k(k+1)}{2},\ldots$|$\binom{n+k-1}{k-1}$|$\frac{1}{(1-x)^k}$|
|$1,k,\frac{k(k-1)}{2},\ldots$|$\binom{n}{k}$|$(1+x)^k$|
|$1,-1,1,-1,1,\ldots$|$(-1)^n$|$\frac{1}{1+x}$|
|$1,c,c^2,c^3,c^4,\ldots$|$c^n$|$\frac{1}{1-cx}$|
|$1,1,2,3,5,8,\ldots$|$\frac{1}{\sqrt{5}}\left(\phi^n+(1-\phi)^n\right)$|$\frac{1}{1-x-x^2}$|
|$c_1+c_2,c_1\alpha+c_2\beta,\ldots$|$c_1\alpha^n+c_2\beta^n$|$\frac{c_1}{1-\alpha x}+\frac{c_2}{1-\beta x}$|
|$0,1,4,9,16,25,\ldots$|$n^2$|$\frac{x(1+x)}{(1-x)^3}$|
|$0,1,\frac{1}{2},\frac{1}{3},\frac{1}{4}\ldots$|$\frac{1}{n}$|$\log(\frac{1}{1-x})$|
||$[n=ja]\cdot\frac{1}{j}$|$\log(\frac{1}{1-x^a})=\sum_{j=1}^\infty\frac{x^{aj}}{j}$|
||||
|$0,\ldots,0,a_0,a_1,a_2,\ldots$|$[n \geq k] \cdot a_{n-k}$|$A(x)x^k$|
|$a_0,-a_1,a_2,-a_3,a_4,\ldots$|$(-1)^na_n$|$A(-x)$|
|$a_0,a_1c,a_2c^2,a_3c^3,\ldots$|$a_nc^n$|$A(cx)$|
|$a_0,0,a_2,0,a_4 \ldots$|$a_n \cdot [n\text{ is even}]$|$\frac{A(x)+A(-x)}{2}$|
|$0,a_1,0,a_3,0 \ldots$|$a_n \cdot [n\text{ is odd}]$|$\frac{A(x)-A(-x)}{2}$|
|$a_0,a_0+a_1,a_0+a_1+a_2\ldots$|$\sum_{i=0}^n a_n$|$\frac{A(x)}{1-x}$|
|$a_0,a_1-a_0,a_2-a_1, \ldots$|$a_n-a_{n-1}$|$A(x)(1-x)$|
|$a_1,2a_2,3a_3,4a_4,\ldots$|$(n+1)a_{n+1}$|$\frac{d}{dx}A(x)$|
|$0,a_1,a_22^k,a_33^k,a_44^k\ldots$|$a_nn^k$|$\left(x\frac{d}{dx}\right)^k A(x)$|
||$\sum_{i+j=n}a_ib_j$|$A(x)B(x)$|

### EGF

|数列|一般項|母関数|
|:---:|:---:|:---:|
|$1,1,1,1,1,\ldots$|$1$|$e^x$|
|$0,1,2,3,4,\ldots$|$n$|$xe^x$| 
|$1,2,6,24,\ldots$|$n!$|$\frac{1}{1-x}$|
|$1,c,c^2,c^3,\ldots$|$c^n$|$e^{cx}$| 
|$1,0,1,0,1,\ldots$|$[n\text{ is even}]$|$\frac{e^x+e^{-x}}{2}$|
|$0,1,0,1,0,\ldots$|$[n\text{ is odd}]$|$\frac{e^x-e^{-x}}{2}$|
||||
|$a_k,a_{k+1},a_{k+2},\ldots$|$a_{n+k}$|$\left(\frac{d}{dx}\right)^kA(x)$|
|$0,a_0,2a_1,3a_2,\ldots$|$na_{n-1}$|$xA(x)$|
||$\sum_{i+j=n}a_ib_j \binom{i + j}{i}$|$A(x)B(x)$|
