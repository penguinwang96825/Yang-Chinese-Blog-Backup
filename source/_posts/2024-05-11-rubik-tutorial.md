---
mathjax: false
abbrlink: 1635b73a
title: 魔術方塊LBL解法
date: 2024-05-11 17:29:35
cover: /cover/wallhaven-0jk3ey.jpg
categories:
  - - 生活
    - 娛樂
tags:
  - 魔術方塊
---

魔術方塊，這個1974年由Ernő Rubik所發明的智力遊戲，迄今仍吸引著全球數百萬愛好者。解開魔術方塊的過程不僅能增強記憶與解決問題的能力，還能帶來極大的樂趣和成就感。因此，我決定撰寫這個部落格來分享我解魔術方塊的心得與技巧，希望能幫助初學者輕鬆入門，並為那些尋求提高解題速度的人提供策略。

# 國際轉動代號

轉動代號在魔術方塊社群中起著一種普遍語言的作用，全球的玩家都使用這些代號來溝通解題的步驟和方法，甚至在比賽中也以這種代號來出題！因此，當我們希望進一步提升自己的技能和實力時，學會這些轉動代號變得極其關鍵，因為只有理解這些代號，我們才能夠明白其他玩家分享的解題公式應如何操作。

## 外層轉動符號

<table>
    <thead>
        <tr>
        <th>轉動代號</th>
        <th>圖例</th>
        <th>轉動代號</th>
        <th>圖例</th>
        </tr>
    </thead>
    <tbody>
        <tr>
        <td class="align-middle text-center" style="text-align: center;">R <span class="text-muted small">(Right)</span></td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_R.svg" alt="Rotate_R" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
        <td class="align-middle text-center" style="text-align: center;">R'</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_R'.svg" alt="Rotate_R" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
        </tr>
        <tr>
        <td class="align-middle text-center" style="text-align: center;">U <span class="text-muted small">(Up)</span></td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_U.svg" alt="Rotate_R" style="width: 100px; height: 100px; max-width: 100%"></td>
        <td class="align-middle text-center" style="text-align: center;">U'</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_U'.svg" alt="Rotate_R" style="width: 100px; height: 100px; max-width: 100%"></td>
        </tr>
        <tr>
        <td class="align-middle text-center" style="text-align: center;">F <span class="text-muted small">(Front)</span></td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_F.svg" alt="Rotate_R" style="width: 100px; height: 100px; max-width: 100%"></td>
        <td class="align-middle text-center" style="text-align: center;">F'</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_F'.svg" alt="Rotate_R" style="width: 100px; height: 100px; max-width: 100%"></td>
        </tr>
        <tr>
        <td class="align-middle text-center" style="text-align: center;">L <span class="text-muted small">(Left)</span></td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_L.svg" alt="Rotate_R" style="width: 100px; height: 100px; max-width: 100%"></td>
        <td class="align-middle text-center" style="text-align: center;">L'</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_L'.svg" alt="Rotate_R" style="width: 100px; height: 100px; max-width: 100%"></td>
        </tr>
        <tr>
        <td class="align-middle text-center" style="text-align: center;">D <span class="text-muted small">(Down)</span></td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_D.svg" alt="Rotate_R" style="width: 100px; height: 100px; max-width: 100%"></td>
        <td class="align-middle text-center" style="text-align: center;">D'</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_D'.svg" alt="Rotate_R" style="width: 100px; height: 100px; max-width: 100%"></td>
        </tr>
        <tr>
        <td class="align-middle text-center" style="text-align: center;">B <span class="text-muted small">(Back)</span></td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_B.svg" alt="Rotate_R" style="width: 100px; height: 100px; max-width: 100%"></td>
        <td class="align-middle text-center" style="text-align: center;">B'</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_B'.svg" alt="Rotate_R" style="width: 100px; height: 100px; max-width: 100%"></td>
        </tr>
    </tbody>
</table>

除此之外，為了明確的表示更多的方向與動作，在這些英文的符號後面會出現三種情況：
 - '：代表為動作符號逆時針旋轉。例如：R'
 - 2：代表所指的這個動作要旋轉180度，即轉動兩步(次)。例如：R2
 - w：代表所指的這個動作，一次要轉動兩層。例如：Rw

## 整顆旋轉代號

<table class="table table-bordered bg-BgGray text-center text-nowrap">
    <thead>
        <tr>
        <th>轉動代號</th>
        <th>圖例</th>
        <th>轉動代號</th>
        <th>圖例</th>
        </tr>
    </thead>
    <tbody>
        <tr>
        <td class="align-middle" style="text-align: center;">x</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_x.svg" alt="Rotate_x" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
        <td class="align-middle" style="text-align: center;">x'</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_x'.svg" alt="Rotate_x'" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>  
        </tr>
        <tr>
        <td class="align-middle" style="text-align: center;">y</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_y.svg" alt="Rotate_y" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
        <td class="align-middle" style="text-align: center;">y'</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_y'.svg" alt="Rotate_y'" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
        </tr>
        <tr>
        <td class="align-middle" style="text-align: center;">z</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_z.svg" alt="Rotate_z" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
        <td class="align-middle" style="text-align: center;">z'</td>
        <td><img src="https://chiacube.tw/images/Rotate/rotate_z'.svg" alt="Rotate_z'" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
        </tr>
    </tbody>
</table>

## 中層轉動代號

<table class="table table-bordered bg-BgGray text-center text-nowrap">
    <thead>
        <tr>
            <th>轉動代號</th>
            <th>圖例</th>
            <th>轉動代號</th>
            <th>圖例</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="align-middle" style="text-align: center;">M</td>
            <td><img src="https://chiacube.tw/images/Rotate/rotate_M.svg" alt="Rotate_M" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
            <td class="align-middle" style="text-align: center;">M'</td>
            <td><img src="https://chiacube.tw/images/Rotate/rotate_M'.svg" alt="Rotate_M'" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
        </tr>
        <tr>
            <td class="align-middle" style="text-align: center;">E</td>
            <td><img src="https://chiacube.tw/images/Rotate/rotate_E.svg" alt="Rotate_E" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
            <td class="align-middle" style="text-align: center;">E'</td>
            <td><img src="https://chiacube.tw/images/Rotate/rotate_E'.svg" alt="Rotate_E'" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
        </tr>
        <tr>
            <td class="align-middle" style="text-align: center;">S</td>
            <td><img src="https://chiacube.tw/images/Rotate/rotate_S.svg" alt="Rotate_S" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
            <td class="align-middle" style="text-align: center;">S'</td>
            <td><img src="https://chiacube.tw/images/Rotate/rotate_S'.svg" alt="Rotate_S'" style="width: 100px; height: 100px; min-width:80px; max-width: 100%"></td>
        </tr>
    </tbody>
</table>

# LBL

LBL (Layer-By-Layer)解法是解魔術方塊中最基本也是最適合初學者學習的一種方法。這種方法按照層次逐層解開魔術方塊，讓解題者能夠較容易地理解和記憶所需的算法。步驟大致區分如下：

1. 第一層
2. 第二層 (F2L)
3. 第三層十字 (OLL)
4. 第三層頂面 (OLL)
5. 第三層頂層角塊 (PLL)
6. 第三層頂層邊塊 (PLL)

這邊我們會直接略過第一層，然後從第二層的公式開始教起。

# F2L

F2L (First 2 Layers)是LBL的第二個步驟，也就是將第一層的角塊和第二層的邊塊一起解好的技術。

<table width="100%">
  <thead>
    <tr>
      <th width="33%">I</th>
      <th width="33%">II</th>
      <th width="33%">III</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <!-- <td width="33%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&fc=nnnnnnnrnnnnnrnrrrnbnnbnbbbwwwwwwwwwoooooooooggggggggg"/></td> -->
      <td width="33%"><img src="{% asset_path 1.png %}"/></td>
      <!-- <td width="33%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&fc=nnnnnbnnnnrnnrnrrrnnnnbnbbbwwwwwwwwwoooooooooggggggggg"/></td> -->
      <td width="33%"><img src="{% asset_path 2.png %}"/></td>
      <!-- <td width="33%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&fc=nnnnnnnnnnnnbrnrrrnnnnbrbbbwwwwwwwwwoooooooooggggggggg"/></td> -->
      <td width="33%"><img src="{% asset_path 3.png %}"/></td>
    </tr>
    <tr>
      <td width="33%" style="text-align: center;"><strong>F U F U F U' F' U' F'</strong></td>
      <td width="33%" style="text-align: center;"><strong>R' U' R' U' R' U R U R</strong></td>
      <td width="33%" style="text-align: center;"><strong>(R U U R' U)2 F' U' F</strong></td>
    </tr>
  </tbody>
</table>


# OLL

OLL (Orientation of the Last Layer)是魔術方塊解法中的一個重要階段。這一階段的目的是通過一系列的旋轉公式，調整最後一層的所有方塊，使頂面的顏色統一。這涉及到旋轉方塊使其頂面的顏色與魔術方塊的頂面顏色一致，而不關心方塊之間的相對位置，位置的調整留待PLL階段處理。為了減少需要記憶的公式數量，我選擇使用兩階段OLL，這涉及到使用更少的公式來進行兩次操作。首先是形成一個頂面十字，然後再將其餘方塊調整到正確的方向。

## OLL第一階段

<table width="100%">
  <thead>
    <tr>
      <th width="33%">邊塊單點</th>
      <th width="33%">邊塊直線</th>
      <th width="33%">邊塊L形</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <!-- <td width="33%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=nnnnunnnnnnnnnnnnnnnnnnnnnndddddddddnnnnnnnnnnnnnnnnnn"/></td> -->
      <td width="33%"><img src="{% asset_path oll-1-1.png %}"/></td>
      <!-- <td width="33%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=nnnuuunnnnnnnnnnnnnnnnnnnnndddddddddnnnnnnnnnnnnnnnnnn"/></td> -->
      <td width="33%"><img src="{% asset_path oll-1-2.png %}"/></td>
      <!-- <td width="33%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=nnnnuununnnnnnnnnnnnnnnnnnndddddddddnnnnnnnnnnnnnnnnnn"/></td> -->
      <td width="33%"><img src="{% asset_path oll-1-3.png %}"/></td>
    </tr>
    <tr>
      <td width="33%" style="text-align: center;"><strong>F (R U R' U') S (R U R' U') Fw'</strong></td>
      <td width="33%" style="text-align: center;"><strong>F (R U R' U') F'</strong></td>
      <td width="33%" style="text-align: center;"><strong>Fw (R U R' U') Fw'</strong></td>
    </tr>
  </tbody>
</table>

## OLL第二階段

<table width="100%">
  <thead>
    <tr>
      <th width="50%">角塊3翻I</th>
      <th width="50%">角塊3翻II</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <!-- <td width="50%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=nuuuuunununnnnnnnnunnnnnnnndddddddddunnnnnnnnnnnnnnnnn"/></td> -->
      <td width="50%"><img src="{% asset_path oll-2-1.png %}"/></td>
      <!-- <td width="50%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=uunuuununnnunnnnnnnnunnnnnndddddddddnnunnnnnnnnnnnnnnn"/></td> -->
      <td width="50%"><img src="{% asset_path oll-2-2.png %}"/></td>
    </tr>
    <tr>
      <td width="50%" style="text-align: center;"><strong>R U2 R' U' R U' R'</strong></td>
      <td width="50%" style="text-align: center;"><strong>L' U2 L U L' U L</strong></td>
    </tr>
  </tbody>
</table>

<table width="100%">
  <thead>
    <tr>
      <th width="50%">角塊4翻I</th>
      <th width="50%">角塊4翻II</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <!-- <td width="50%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=nunuuununnnnnnnnnnununnnnnndddddddddnnnnnnnnnununnnnnn"/></td> -->
      <td width="50%"><img src="{% asset_path oll-2-3.png %}"/></td>
      <!-- <td width="50%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=nunuuununnnnnnnnnnnnunnnnnndddddddddununnnnnnunnnnnnnn"/></td> -->
      <td width="50%"><img src="{% asset_path oll-2-4.png %}"/></td>
    </tr>
    <tr>
      <td width="50%" style="text-align: center;"><strong>F (R U R' U')3 F'</strong></td>
      <td width="50%" style="text-align: center;"><strong>R U2 R2 U' R2 U' R2 U2 R</strong></td>
    </tr>
  </tbody>
</table>

<table width="100%">
  <thead>
    <tr>
      <th width="33%">角塊2翻I</th>
      <th width="33%">角塊2翻II</th>
      <th width="33%">角塊2翻III</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <!-- <td width="33%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=uunuuunuunnunnnnnnunnnnnnnndddddddddnnnnnnnnnnnnnnnnnn"/></td> -->
      <td width="33%"><img src="{% asset_path oll-2-5.png %}"/></td>
      <!-- <td width="33%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=nuuuuunuunnnnnnnnnunnnnnnnndddddddddnnnnnnnnnnnunnnnnn"/></td> -->
      <td width="33%"><img src="{% asset_path oll-2-6.png %}"/></td>
      <!-- <td width="33%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=nunuuuuuunnnnnnnnnnnnnnnnnndddddddddnnnnnnnnnununnnnnn"/></td> -->
      <td width="33%"><img src="{% asset_path oll-2-7.png %}"/></td>
    </tr>
    <tr>
      <td width="33%" style="text-align: center;"><strong>L' B' R' B L B' R B</strong></td>
      <td width="33%" style="text-align: center;"><strong>L' B' R B L B' R' B</strong></td>
      <td width="33%" style="text-align: center;"><strong>R2 D' R U2 R' D R U2 R</strong></td>
    </tr>
  </tbody>
</table>

# PLL

在魔術方塊的PLL (Permutation of the Last Layer)階段，我們的目標是將最後一層的方塊全部排列到正確的位置上。本篇我們會使用兩段式PLL。這個策略將最後一層的置換分為兩個階段來完成。在這種策略下，解題者會先確定最後一層所有<em><strong>角塊</strong></em>的正確位置，然後再進行<em><strong>邊塊</strong></em>的置換。

## PLL第一階段

PLL第一階段會先確定最後一層所有<em><strong>角塊</strong></em>都到正確位置。第一階段只會有兩種情況：無一側角落同色或是有一側角落同色。

<table width="100%">
  <thead>
    <tr>
      <th width="50%">無一側角落同色</th>
      <th width="50%">有一側角落同色</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <!-- <td width="50%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=uuuuuuuuunnnnnnnnnnnnnnnnnndddddddddnnnnnnnnnnnnnnnnnn"/></td> -->
      <td width="50%"><img src="{% asset_path pll-1-1.png %}"/></td>
      <!-- <td width="50%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&fd=uuuuuuuuunnnnnnnnnnnnnnnnnndddddddddlnlllllllnnnnnnnnn"/></td> -->
      <td width="50%"><img src="{% asset_path pll-1-2.png %}"/></td>
    </tr>
    <tr>
      <td width="50%" style="text-align: center;"><strong>F R U' R' U' R U R' F' (R U R' U') (R'F R F')</strong></td>
      <td width="50%" style="text-align: center;"><strong>(R U R' U') R' F R2 U' R' U' R U R' F'</strong></td>
    </tr>
  </tbody>
</table>

## PLL第二階段

PLL第二階段會確定最後一層所有<em><strong>邊塊</strong></em>都到正確位置。

<table width="100%">
  <thead>
    <tr>
      <th width="50%">Ua-Perm</th>
      <th width="50%">Ub-Perm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <!-- <td width="50%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&alg=M2U3MU2M3U3M2&arw=U5U3-s7,U7U5-s7,U3U7-s7"/></td> -->
      <td width="50%"><img src="{% asset_path pll-ua.png %}"/></td>
      <!-- <td width="50%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&alg=M2UMU2M3UM2&arw=U3U5-s7,U5U7-s7,U7U3-s7"/></td> -->
      <td width="50%"><img src="{% asset_path pll-ub.png %}"/></td>
    </tr>
    <tr>
      <td width="50%" style="text-align: center;"><strong>M2 U M U2 M' U M2</strong></td>
      <td width="50%" style="text-align: center;"><strong>M2 U' M U2 M' U' M2</strong></td>
    </tr>
  </tbody>
</table>

<table width="100%">
  <thead>
    <tr>
      <th width="50%">H-Perm</th>
      <th width="50%">Z-Perm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <!-- <td width="50%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&alg=M2U(M2U2M2)UM2&arw=U1U7,U7U1,U3U5,U5U3"/></td> -->
      <td width="50%"><img src="{% asset_path pll-h.png %}"/></td>
      <!-- <td width="50%"><img src="http://cube.rider.biz/visualcube.php?fmt=svg&size=150&pzl=3&bg=t&view=plan&alg=M3UM2UM2UM3U2M2U&arw=U1U5,U5U1,U3U7,U7U3"/></td> -->
      <td width="50%"><img src="{% asset_path pll-z.png %}"/></td>
    </tr>
    <tr>
      <td width="50%" style="text-align: center;"><strong>M2 U (M2 U2 M2) U M2</strong></td>
      <td width="50%" style="text-align: center;"><strong>M' U (M2 U M2 U) M' U2 M2</strong></td>
    </tr>
  </tbody>
</table>

# 結語

練習是達到高效解題的關鍵。因為每一次的嘗試都讓我們更接近成為魔術方塊高手的目標。希望這個部落格能啟發讀者的魔術方塊探索之旅，解開更多的可能性。如果未來有更快的魔術方塊解法，我也會在此分享。

# References

1. https://1hrbld.tw/category/algdb/3x3-pll-algs/
2. http://cube.rider.biz/visualcube.php
3. https://chiacube.tw/Basic/Rotate
4. https://www.cubeskills.com/uploads/pdf/tutorials/f2l.pdf