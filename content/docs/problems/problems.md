---
title: "作問一覧"
description: ""
lead: ""
date: 2000-01-01T00:00:00+09:00
lastmod: 2000-01-01T00:00:00+09:00
draft: false
images: []
menu: 
  docs:
    parent: "problems"
weight: 1
toc: true
---

自分が原案を担当した問題をまとめた。(注：ABC は原案担当と準備担当が分かれているため、自分が準備者でない問題も存在する。)

最終更新日：2024 年 12 月 31 日

<script>
window.addEventListener('load', function () {
  let column_no = 0;
  let column_no_prev = 0;
  document.querySelectorAll('#sort_table th').forEach(elm => {
    elm.onclick = function () {
      column_no = this.cellIndex;
      let table = this.parentNode.parentNode.parentNode;
      let sortType = 0;
      let sortArray = new Array;
      for (let r = 1; r < table.rows.length; r++) {
        let column = new Object;
        column.row = table.rows[r];
        column.value = table.rows[r].cells[column_no].textContent;
        sortArray.push(column);
        if (isNaN(Number(column.value))) {
          sortType = 1;
        }
      }
      if (sortType == 0) {
        if (column_no_prev == column_no) {
          sortArray.sort(compareNumberDesc);
        } else {
          sortArray.sort(compareNumber);
        }
      } else {
        if (column_no_prev == column_no) {
          sortArray.sort(compareStringDesc);
        } else {
          sortArray.sort(compareString);
        }
      }
      let tbody = this.parentNode.parentNode;
      for (let i = 0; i < sortArray.length; i++) {
        tbody.appendChild(sortArray[i].row);
      }
      if (column_no_prev == column_no) {
        column_no_prev = -1;
      } else {
        column_no_prev = column_no;
      }
    };
  });
});
function compareNumber(a, b)
{
  return a.value - b.value;
}
function compareNumberDesc(a, b)
{
  return b.value - a.value;
}
function compareString(a, b) {
  if (a.value < b.value) {
    return -1;
  } else {
    return 1;
  }
  return 0;
}
function compareStringDesc(a, b) {
  if (a.value > b.value) {
    return -1;
  } else {
    return 1;
  }
  return 0;
}
</script>
<table id="sort_table">
<tr><th>Contest</th><th>Index</th><th>Name</th><th>Difficulty</th></tr>
<tr><td>ABC208</td><td>ABC-A</td><td><a href=https://atcoder.jp/contests/abc208/tasks/abc208_a>Rolling Dice</a></td><td>28</td></tr>
<tr><td>ABC208</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc208/tasks/abc208_b>Factorial Yen Coin</a></td><td>51</td></tr>
<tr><td>ABC208</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc208/tasks/abc208_c>Fair Candy Distribution</a></td><td>142</td></tr>
<tr><td>ABC208</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc208/tasks/abc208_e>Digit Products</a></td><td>2024</td></tr>
<tr><td>ABC208</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc208/tasks/abc208_f>Cumulative Sum</a></td><td>2772</td></tr>
<tr><td>ABC212</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc212/tasks/abc212_d>Querying Multiset </a></td><td>775</td></tr>
<tr><td>ABC212</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc212/tasks/abc212_h>Nim Counting</a></td><td>2741</td></tr>
<tr><td>ABC213</td><td>ABC-A</td><td><a href=https://atcoder.jp/contests/abc213/tasks/abc213_a>Bitwise Exclusive Or</a></td><td>33</td></tr>
<tr><td>ABC213</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc213/tasks/abc213_b>Booby Prize</a></td><td>26</td></tr>
<tr><td>ABC213</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc213/tasks/abc213_c>Reorder Cards</a></td><td>481</td></tr>
<tr><td>ABC213</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc213/tasks/abc213_d>Takahashi Tour</a></td><td>710</td></tr>
<tr><td>ABC213</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc213/tasks/abc213_f>Common Prefixes</a></td><td>2215</td></tr>
<tr><td>ABC213</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc213/tasks/abc213_g>Connectivity 2</a></td><td>2663</td></tr>
<tr><td>ABC213</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc213/tasks/abc213_h>Stroll</a></td><td>2806</td></tr>
<tr><td>ABC215</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc215/tasks/abc215_h>Cabbage Master</a></td><td>3101</td></tr>
<tr><td>ABC217</td><td>ABC-A</td><td><a href=https://atcoder.jp/contests/abc217/tasks/abc217_a>Lexicographic Order</a></td><td>21</td></tr>
<tr><td>ABC217</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc217/tasks/abc217_c>Inverse of Permutation</a></td><td>49</td></tr>
<tr><td>ABC217</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc217/tasks/abc217_d>Cutting Woods</a></td><td>802</td></tr>
<tr><td>ABC217</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc217/tasks/abc217_e>Sorting Queries</a></td><td>986</td></tr>
<tr><td>ABC217</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc217/tasks/abc217_g>Groups</a></td><td>2047</td></tr>
<tr><td>ABC217</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc217/tasks/abc217_h>Snuketoon</a></td><td>3112</td></tr>
<tr><td>ABC219</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc219/tasks/abc219_c>Neo-lexicographic Ordering</a></td><td>260</td></tr>
<tr><td>ABC220</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc220/tasks/abc220_h>Security Camera</a></td><td>3047</td></tr>
<tr><td>ABC221</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc221/tasks/abc221_d>Online games</a></td><td>832</td></tr>
<tr><td>ABC222</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc222/tasks/abc222_b>Failing Grade</a></td><td>9</td></tr>
<tr><td>ABC222</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc222/tasks/abc222_d>Between Two Arrays</a></td><td>865</td></tr>
<tr><td>ABC222</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc222/tasks/abc222_e>Red and Blue Tree</a></td><td>1491</td></tr>
<tr><td>ABC222</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc222/tasks/abc222_f>Expensive Expense</a></td><td>1934</td></tr>
<tr><td>ABC222</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc222/tasks/abc222_h>Beautiful Binary Tree</a></td><td>3477</td></tr>
<tr><td>ABC224</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc224/tasks/abc224_d>8 Puzzle on Graph</a></td><td>1376</td></tr>
<tr><td>ABC225</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc225/tasks/abc225_d>Play Train</a></td><td>778</td></tr>
<tr><td>ABC226</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc226/tasks/abc226_b>Counting Arrays</a></td><td>192</td></tr>
<tr><td>ABC226</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc226/tasks/abc226_d>Teleportation</a></td><td>706</td></tr>
<tr><td>ABC226</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc226/tasks/abc226_f>Score of Permutations</a></td><td>2086</td></tr>
<tr><td>ABC226</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc226/tasks/abc226_h>Random Kth Max</a></td><td>2813</td></tr>
<tr><td>ABC228</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc228/tasks/abc228_d>Linear Probing</a></td><td>1035</td></tr>
<tr><td>ABC230</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc230/tasks/abc230_d>Destroyer Takahashi</a></td><td>963</td></tr>
<tr><td>ABC230</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc230/tasks/abc230_h>Bullion</a></td><td>3528</td></tr>
<tr><td>ABC232</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc232/tasks/abc232_h>King's Tour</a></td><td>2780</td></tr>
<tr><td>ABC235</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc235/tasks/abc235_c>The Kth Time Query</a></td><td>249</td></tr>
<tr><td>ABC235</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc235/tasks/abc235_d>Multiply and Rotate</a></td><td>862</td></tr>
<tr><td>ABC235</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc235/tasks/abc235_e>MST + 1</a></td><td>1304</td></tr>
<tr><td>ABC235</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc235/tasks/abc235_g>Gardens</a></td><td>2462</td></tr>
<tr><td>ABC236</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc236/tasks/abc236_c>Route Map</a></td><td>80</td></tr>
<tr><td>ABC239</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc239/tasks/abc239_b>Integer Division</a></td><td>57</td></tr>
<tr><td>ABC239</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc239/tasks/abc239_f>Construct Highway</a></td><td>1959</td></tr>
<tr><td>ABC239</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc239/tasks/abc239_g>Builder Takahashi</a></td><td>2215</td></tr>
<tr><td>ABC239</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc239/tasks/abc239_h>Dice Product 2</a></td><td>2686</td></tr>
<tr><td>ABC241</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc241/tasks/abc241_h>Card Deck Score</a></td><td>2881</td></tr>
<tr><td>ABC243</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc243/tasks/abc243_h>Builder Takahashi (Enhanced version)</a></td><td>3884</td></tr>
<tr><td>ABC244</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc244/tasks/abc244_b>Go Straight and Turn Right</a></td><td>30</td></tr>
<tr><td>ABC244</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc244/tasks/abc244_e>King Bombee</a></td><td>1125</td></tr>
<tr><td>ABC247</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc247/tasks/abc247_c>1 2 1 3 1 2 1</a></td><td>149</td></tr>
<tr><td>ABC247</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc247/tasks/abc247_h>Rearranging Problem</a></td><td>2664</td></tr>
<tr><td>ABC251</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc251/tasks/abc251_b>At Most 3 (Judge ver.)</a></td><td>181</td></tr>
<tr><td>ABC251</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc251/tasks/abc251_c>Poem Online Judge</a></td><td>246</td></tr>
<tr><td>ABC251</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc251/tasks/abc251_d>At Most 3 (Contestant ver.)</a></td><td>1463</td></tr>
<tr><td>ABC251</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc251/tasks/abc251_h>Fill Triangle</a></td><td>3108</td></tr>
<tr><td>ABC252</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc252/tasks/abc252_e>Road Reduction</a></td><td>1294</td></tr>
<tr><td>ABC252</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc252/tasks/abc252_h>K-th beautiful Necklace</a></td><td>3015</td></tr>
<tr><td>ABC256</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc256/tasks/abc256_c>Filling 3x3 array</a></td><td>541</td></tr>
<tr><td>ABC256</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc256/tasks/abc256_h>I like Query Problem</a></td><td>2531</td></tr>
<tr><td>ABC260</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc260/tasks/abc260_c>Changing Jewels</a></td><td>413</td></tr>
<tr><td>ABC260</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc260/tasks/abc260_e>At Least One</a></td><td>1692</td></tr>
<tr><td>ABC260</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc260/tasks/abc260_f>Find 4-cycle</a></td><td>1995</td></tr>
<tr><td>ABC260</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc260/tasks/abc260_g>Scalene Triangle Area</a></td><td>2339</td></tr>
<tr><td>ABC260</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc260/tasks/abc260_h>Colorfulness</a></td><td>3339</td></tr>
<tr><td>ABC264</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc264/tasks/abc264_d>"redocta".swap(i,i+1)</a></td><td>414</td></tr>
<tr><td>ABC265</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc265/tasks/abc265_c>Belt Conveyor</a></td><td>212</td></tr>
<tr><td>ABC265</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc265/tasks/abc265_h>No-capture Lance Game</a></td><td>3319</td></tr>
<tr><td>ABC269</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc269/tasks/abc269_e>Last Rook</a></td><td>1030</td></tr>
<tr><td>ABC269</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc269/tasks/abc269_g>Reversible Cards 2</a></td><td>2440</td></tr>
<tr><td>ABC269</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc269/tasks/abc269_h>Antichain</a></td><td>3178</td></tr>
<tr><td>ABC270</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc270/tasks/abc270_h>add 1 </a></td><td>3159</td></tr>
<tr><td>ABC272</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc272/tasks/abc272_d>Root M Leaper</a></td><td>804</td></tr>
<tr><td>ABC272</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc272/tasks/abc272_g>Yet Another mod M</a></td><td>2187</td></tr>
<tr><td>ABC273</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc273/tasks/abc273_h>Inv(0,1)ving Insert(1,0)n</a></td><td>3598</td></tr>
<tr><td>ABC274</td><td>ABC-A</td><td><a href=https://atcoder.jp/contests/abc274/tasks/abc274_a>Batting Average</a></td><td>23</td></tr>
<tr><td>ABC274</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc274/tasks/abc274_h>XOR Sum of Arrays</a></td><td>3191</td></tr>
<tr><td>ABC277</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc277/tasks/abc277_c>Ladder Takahashi</a></td><td>540</td></tr>
<tr><td>ABC278</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc278/tasks/abc278_g>Generalized Subtraction Game</a></td><td>2533</td></tr>
<tr><td>ABC278</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc278/tasks/abc278_h>make 1</a></td><td>3768</td></tr>
<tr><td>ABC280</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc280/tasks/abc280_h>Substring Sort</a></td><td>3307</td></tr>
<tr><td>ABC281</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc281/tasks/abc281_h>Alchemy</a></td><td>3180</td></tr>
<tr><td>ABC284</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc284/tasks/abc284_b>Multi Test Cases</a></td><td>14</td></tr>
<tr><td>ABC284</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc284/tasks/abc284_c>Count Connected Components</a></td><td>193</td></tr>
<tr><td>ABC284</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc284/tasks/abc284_h>Count Unlabeled Graphs</a></td><td>3125</td></tr>
<tr><td>ABC289</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc289/tasks/abc289_h>Trio</a></td><td>3246</td></tr>
<tr><td>ABC291</td><td>ABC-A</td><td><a href=https://atcoder.jp/contests/abc291/tasks/abc291_a>camel Case</a></td><td>8</td></tr>
<tr><td>ABC291</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc291/tasks/abc291_b>Trimmed Mean</a></td><td>32</td></tr>
<tr><td>ABC291</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc291/tasks/abc291_h>Balanced Tree</a></td><td>2097</td></tr>
<tr><td>ABC294</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc294/tasks/abc294_b>ASCII Art</a></td><td>25</td></tr>
<tr><td>ABC294</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc294/tasks/abc294_d>Bank</a></td><td>385</td></tr>
<tr><td>ABC294</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc294/tasks/abc294_f>Sugar Water 2</a></td><td>1891</td></tr>
<tr><td>ABC296</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc296/tasks/abc296_f>Simultaneous Swap</a></td><td>1811</td></tr>
<tr><td>ABC297</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc297/tasks/abc297_c>PC on the Table</a></td><td>96</td></tr>
<tr><td>ABC297</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc297/tasks/abc297_d>Count Subtractions</a></td><td>273</td></tr>
<tr><td>ABC298</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc298/tasks/abc298_d>Writing a Numeral</a></td><td>882</td></tr>
<tr><td>ABC298</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc298/tasks/abc298_e>Unfair Sugoroku</a></td><td>1300</td></tr>
<tr><td>ABC299</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc299/tasks/abc299_g>Minimum Permutation</a></td><td>2066</td></tr>
<tr><td>ABC300</td><td>ABC-A</td><td><a href=https://atcoder.jp/contests/abc300/tasks/abc300_a>N-choice question</a></td><td>8</td></tr>
<tr><td>ABC300</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc300/tasks/abc300_b>Same Map in the RPG World</a></td><td>353</td></tr>
<tr><td>ABC300</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc300/tasks/abc300_c>Cross</a></td><td>534</td></tr>
<tr><td>ABC300</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc300/tasks/abc300_d>AABCC</a></td><td>908</td></tr>
<tr><td>ABC300</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc300/tasks/abc300_e>Dice Product 3</a></td><td>1354</td></tr>
<tr><td>ABC300</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc300/tasks/abc300_g>P-smooth number</a></td><td>2343</td></tr>
<tr><td>ABC300</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc300/tasks/abc300_h>Fibonacci: Revisited</a></td><td>3209</td></tr>
<tr><td>ABC301</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc301/tasks/abc301_d>Bitmask</a></td><td>885</td></tr>
<tr><td>ABC301</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc301/tasks/abc301_e>Pac-Takahashi </a></td><td>1673</td></tr>
<tr><td>ABC301</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc301/tasks/abc301_g>Worst Picture</a></td><td>3262</td></tr>
<tr><td>ABC302</td><td>ABC-A</td><td><a href=https://atcoder.jp/contests/abc302/tasks/abc302_a>Attack</a></td><td>24</td></tr>
<tr><td>ABC302</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc302/tasks/abc302_b>Find snuke</a></td><td>352</td></tr>
<tr><td>ABC302</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc302/tasks/abc302_c>Almost Equal</a></td><td>469</td></tr>
<tr><td>ABC302</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc302/tasks/abc302_h>Ball Collector</a></td><td>2407</td></tr>
<tr><td>ABC305</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc305/tasks/abc305_b>ABCDEFG</a></td><td>23</td></tr>
<tr><td>ABC305</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc305/tasks/abc305_c>Snuke the Cookie Picker</a></td><td>159</td></tr>
<tr><td>ABC305</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc305/tasks/abc305_d>Sleep Log</a></td><td>671</td></tr>
<tr><td>ABC305</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc305/tasks/abc305_e>Art Gallery on Graph</a></td><td>1158</td></tr>
<tr><td>ABC305</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc305/tasks/abc305_f>Dungeon Explore</a></td><td>1420</td></tr>
<tr><td>ABC305</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc305/tasks/abc305_h>Shojin</a></td><td>3344</td></tr>
<tr><td>ABC306</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc306/tasks/abc306_b>Base 2</a></td><td>0</td></tr>
<tr><td>ABC307</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc307/tasks/abc307_h>Marquee</a></td><td>2754</td></tr>
<tr><td>ABC308</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc308/tasks/abc308_d>Snuke Maze</a></td><td>619</td></tr>
<tr><td>ABC311</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc311/tasks/abc311_e>Defect-free Squares</a></td><td>1293</td></tr>
<tr><td>ABC311</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc311/tasks/abc311_h>Many Illumination Plans</a></td><td>3605</td></tr>
<tr><td>ABC312</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc312/tasks/abc312_h>snukesnuke</a></td><td>2477</td></tr>
<tr><td>ABC315</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc315/tasks/abc315_h>Typical Convolution Problem</a></td><td>2807</td></tr>
<tr><td>ABC317</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc317/tasks/abc317_g>Rearranging</a></td><td>2649</td></tr>
<tr><td>ABC317</td><td>ABC-H</td><td><a href=https://atcoder.jp/contests/abc317/tasks/abc317_h>Walk</a></td><td>3426</td></tr>
<tr><td>ABC318</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc318/tasks/abc318_g>Typical Path Problem</a></td><td>2260</td></tr>
<tr><td>ABC319</td><td>ABC-A</td><td><a href=https://atcoder.jp/contests/abc319/tasks/abc319_a>Legendary Players</a></td><td>10</td></tr>
<tr><td>ABC319</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc319/tasks/abc319_f>Fighter Takahashi</a></td><td>2480</td></tr>
<tr><td>ABC322</td><td>ABC-A</td><td><a href=https://atcoder.jp/contests/abc322/tasks/abc322_a>First ABC 2</a></td><td>12</td></tr>
<tr><td>ABC322</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc322/tasks/abc322_b>Prefix and Suffix</a></td><td>54</td></tr>
<tr><td>ABC322</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc322/tasks/abc322_d>Polyomino</a></td><td>1310</td></tr>
<tr><td>ABC322</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc322/tasks/abc322_f>Vacation Query</a></td><td>1806</td></tr>
<tr><td>ABC327</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc327/tasks/abc327_d>Good Tuple Problem</a></td><td>709</td></tr>
<tr><td>ABC327</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc327/tasks/abc327_g>Many Good Tuple Problems</a></td><td>2968</td></tr>
<tr><td>ABC331</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc331/tasks/abc331_e>Set Meal</a></td><td>1018</td></tr>
<tr><td>ABC331</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc331/tasks/abc331_f>Palindrome Query</a></td><td>1666</td></tr>
<tr><td>ABC336</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc336/tasks/abc336_b>CTZ</a></td><td>27</td></tr>
<tr><td>ABC336</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc336/tasks/abc336_c>Even Digits</a></td><td>343</td></tr>
<tr><td>ABC336</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc336/tasks/abc336_e>Digit Sum Divisible</a></td><td>1538</td></tr>
<tr><td>ABC336</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc336/tasks/abc336_g>16 Integers</a></td><td>3138</td></tr>
<tr><td>ABC340</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc340/tasks/abc340_c>Divide and Divide</a></td><td>528</td></tr>
<tr><td>ABC340</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc340/tasks/abc340_f>S = 1</a></td><td>1516</td></tr>
<tr><td>ABC340</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc340/tasks/abc340_g>Leaf Color</a></td><td>2401</td></tr>
<tr><td>ABC342</td><td>ABC-A</td><td><a href=https://atcoder.jp/contests/abc342/tasks/abc342_a>Yay!</a></td><td>31</td></tr>
<tr><td>ABC342</td><td>ABC-C</td><td><a href=https://atcoder.jp/contests/abc342/tasks/abc342_c>Many Replacement</a></td><td>505</td></tr>
<tr><td>ABC345</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc345/tasks/abc345_b>Integer Division Returns</a></td><td>91</td></tr>
<tr><td>ABC345</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc345/tasks/abc345_f>Many Lamps</a></td><td>2157</td></tr>
<tr><td>ABC345</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc345/tasks/abc345_g>Sugoroku 5</a></td><td>3343</td></tr>
<tr><td>ABC347</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc347/tasks/abc347_g>Grid Coloring 2</a></td><td>2876</td></tr>
<tr><td>ABC351</td><td>ABC-A</td><td><a href=https://atcoder.jp/contests/abc351/tasks/abc351_a>The bottom of the ninth</a></td><td>11</td></tr>
<tr><td>ABC351</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc351/tasks/abc351_b>Spot the Difference</a></td><td>34</td></tr>
<tr><td>ABC351</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc351/tasks/abc351_g>Hash on Tree</a></td><td>2920</td></tr>
<tr><td>ABC357</td><td>ABC-B</td><td><a href=https://atcoder.jp/contests/abc357/tasks/abc357_b>Uppercase and Lowercase</a></td><td>26</td></tr>
<tr><td>ABC357</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc357/tasks/abc357_e>Reachability in Functional Graph</a></td><td>1295</td></tr>
<tr><td>ABC357</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc357/tasks/abc357_g>Stair-like Grid</a></td><td>3159</td></tr>
<tr><td>ABC363</td><td>ABC-D</td><td><a href=https://atcoder.jp/contests/abc363/tasks/abc363_d>Palindromic Number</a></td><td>975</td></tr>
<tr><td>ABC363</td><td>ABC-F</td><td><a href=https://atcoder.jp/contests/abc363/tasks/abc363_f>Palindromic Expression</a></td><td>1913</td></tr>
<tr><td>ABC363</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc363/tasks/abc363_g>Dynamic Scheduling</a></td><td>3358</td></tr>
<tr><td>ABC370</td><td>ABC-E</td><td><a href=https://atcoder.jp/contests/abc370/tasks/abc370_e>Avoid K Partition</a></td><td>1453</td></tr>
<tr><td>ABC370</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc370/tasks/abc370_g>Divisible by 3</a></td><td>3428</td></tr>
<tr><td>ABC376</td><td>ABC-G</td><td><a href=https://atcoder.jp/contests/abc376/tasks/abc376_g>Treasure Hunting</a></td><td>2858</td></tr>
<tr><td>AGC070</td><td>AGC-A</td><td><a href=https://atcoder.jp/contests/agc070/tasks/agc070_a>Multiples in the String</a></td><td>2006</td></tr>
<tr><td>AGC070</td><td>AGC-B</td><td><a href=https://atcoder.jp/contests/agc070/tasks/agc070_b>Odd Namori</a></td><td>3217</td></tr>
<tr><td>AGC070</td><td>AGC-C</td><td><a href=https://atcoder.jp/contests/agc070/tasks/agc070_c>No Streak</a></td><td>2983</td></tr>
<tr><td>AGC070</td><td>AGC-D</td><td><a href=https://atcoder.jp/contests/agc070/tasks/agc070_d>2D Solitaire</a></td><td>4211</td></tr>
<tr><td>AGC070</td><td>AGC-E</td><td><a href=https://atcoder.jp/contests/agc070/tasks/agc070_e>Remove 2K+1 Edges</a></td><td>9999</td></tr>
<tr><td>ARC139</td><td>ARC-A</td><td><a href=https://atcoder.jp/contests/arc139/tasks/arc139_a>Trailing Zeros</a></td><td>599</td></tr>
<tr><td>ARC139</td><td>ARC-E</td><td><a href=https://atcoder.jp/contests/arc139/tasks/arc139_e>Wazir</a></td><td>3222</td></tr>
<tr><td>ARC148</td><td>ARC-A</td><td><a href=https://atcoder.jp/contests/arc148/tasks/arc148_a>mod M</a></td><td>656</td></tr>
<tr><td>ARC148</td><td>ARC-B</td><td><a href=https://atcoder.jp/contests/arc148/tasks/arc148_b>dp</a></td><td>975</td></tr>
<tr><td>ARC148</td><td>ARC-C</td><td><a href=https://atcoder.jp/contests/arc148/tasks/arc148_c>Lights Out on Tree</a></td><td>1488</td></tr>
<tr><td>ARC148</td><td>ARC-D</td><td><a href=https://atcoder.jp/contests/arc148/tasks/arc148_d>mod M Game</a></td><td>2009</td></tr>
<tr><td>ARC148</td><td>ARC-E</td><td><a href=https://atcoder.jp/contests/arc148/tasks/arc148_e>≥ K</a></td><td>2785</td></tr>
<tr><td>ARC148</td><td>ARC-F</td><td><a href=https://atcoder.jp/contests/arc148/tasks/arc148_f>998244353 → 1000000007</a></td><td>3621</td></tr>
<tr><td>ARC160</td><td>ARC-A</td><td><a href=https://atcoder.jp/contests/arc160/tasks/arc160_a>Reverse and Count</a></td><td>1275</td></tr>
<tr><td>ARC160</td><td>ARC-E</td><td><a href=https://atcoder.jp/contests/arc160/tasks/arc160_e>Make Biconnected</a></td><td>3284</td></tr>
<tr><td>ARC160</td><td>ARC-F</td><td><a href=https://atcoder.jp/contests/arc160/tasks/arc160_f>Count Sorted Arrays</a></td><td>3202</td></tr>
<tr><td>ARC171</td><td>ARC-A</td><td><a href=https://atcoder.jp/contests/arc171/tasks/arc171_a>No Attacking</a></td><td>614</td></tr>
<tr><td>ARC171</td><td>ARC-B</td><td><a href=https://atcoder.jp/contests/arc171/tasks/arc171_b>Chmax</a></td><td>1374</td></tr>
<tr><td>ARC171</td><td>ARC-C</td><td><a href=https://atcoder.jp/contests/arc171/tasks/arc171_c>Swap on Tree</a></td><td>2244</td></tr>
<tr><td>ARC171</td><td>ARC-D</td><td><a href=https://atcoder.jp/contests/arc171/tasks/arc171_d>Rolling Hash</a></td><td>2377</td></tr>
<tr><td>ARC171</td><td>ARC-E</td><td><a href=https://atcoder.jp/contests/arc171/tasks/arc171_e>Rookhopper's Tour</a></td><td>3034</td></tr>
<tr><td>ARC171</td><td>ARC-F</td><td><a href=https://atcoder.jp/contests/arc171/tasks/arc171_f>Both Reversible</a></td><td>3730</td></tr>
<tr><td>ARC185</td><td>ARC-A</td><td><a href=https://atcoder.jp/contests/arc185/tasks/arc185_a>mod M Game 2</a></td><td>1042</td></tr>
<tr><td>ARC185</td><td>ARC-B</td><td><a href=https://atcoder.jp/contests/arc185/tasks/arc185_b>+1 and -1</a></td><td>1332</td></tr>
<tr><td>ARC185</td><td>ARC-C</td><td><a href=https://atcoder.jp/contests/arc185/tasks/arc185_c>Sum of Three Integers</a></td><td>2242</td></tr>
<tr><td>ARC185</td><td>ARC-D</td><td><a href=https://atcoder.jp/contests/arc185/tasks/arc185_d>Random Walk on Tree</a></td><td>2649</td></tr>
<tr><td>ARC185</td><td>ARC-E</td><td><a href=https://atcoder.jp/contests/arc185/tasks/arc185_e>Adjacent GCD</a></td><td>2185</td></tr>
<tr><td>yuki</td><td>yuki</td><td><a href=https://yukicoder.me/problems/no/1754>T-block Tiling</a></td><td>400</td></tr>
<tr><td>yuki</td><td>yuki</td><td><a href=https://yukicoder.me/problems/no/1755>Almost Palindrome</a></td><td>2000</td></tr>
<tr><td>yuki</td><td>yuki</td><td><a href=https://yukicoder.me/problems/no/1756>Rider's Triangle</a></td><td>2000</td></tr>
<tr><td>yuki</td><td>yuki</td><td><a href=https://yukicoder.me/problems/no/1759>Silver Tour</a></td><td>2800</td></tr>
<tr><td>yuki</td><td>yuki</td><td><a href=https://yukicoder.me/problems/no/1762>🐙🐄🌲</a></td><td>3600</td></tr>
<tr><td>yuki</td><td>yuki</td><td><a href=https://yukicoder.me/problems/no/1783>Remix Sum</a></td><td>0</td></tr>
<tr><td>yuki</td><td>yuki</td><td><a href=https://yukicoder.me/problems/no/2166>Paint and Fill</a></td><td>0</td></tr>
<tr><td>yuki</td><td>yuki</td><td><a href=https://yukicoder.me/problems/no/2583>Differential Equation (Enhanced version)</a></td><td>0</td></tr>
<tr><td>yuki</td><td>yuki</td><td><a href=https://yukicoder.me/problems/no/3000>Optimal Run Length Encoding</a></td><td>0</td></tr>
</table>

