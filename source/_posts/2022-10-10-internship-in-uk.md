---
title: 英國Research Intern的經歷
mathjax: false
cover: /cover/wallhaven-g8g373.png
categories:
  - - 生活
    - 留學
  - - 工作
    - 實習
tags:
  - 英國
  - 實習
abbrlink: a949fbb9
date: 2022-05-30 17:33:19
---

這邊來稍微紀錄一下我在英國實習的經過。想當初從Google上面搜尋別人分享的海外實習經歷，都只能跳出一些留學仲介發的廣告文，或是那種求職網站給的JD(job describtion)。我就想說我要分享給其他有需要的人們，或許某些正在英國找實習的人可以從中找到啟發。

# VoiceBase Centre

在英國讀碩士的期間，我做了兩份實習。

第一份實習，算是非常非常的幸運，可以說是被我撿到的。

## 運氣爆棚

剛開學那時候，整個學院大概有200位學生要準備去搶碩士題目。但是我對大部分的題目都是興致缺缺。所以我就選擇自己寫了一份research proposal，貼在學校的網站布告欄上，希望有教授對我的topic感興趣。我給大約20位教授發了信，跟他們自薦了一番，希望我可以成為他們的指導學生。不過到最後，只有三位教授給我回了信。

大約過了一周，SpandH組的Thomas Hain教授也給我發了封信。他說非常抱歉沒有在選題目的deadline之前給我回信，因為他人不舒服無法給我回應(我猜應該是covid)。Thomas跟我說他實驗室有研究實習的缺，問我有沒有興趣。我當時高興到飛天，馬上就給了他一個正面回應。

## 語音識別面試

過了兩三天，Thomas就說想跟我面試一下，看一下我的research ability。在面試的過程中，Mauro Nicolao和‪Md Asif Jalal‬(未來的兩位internship supervisors)也在場跟Thomas一起面試我。基本上就是一些motivations和數學相關的問題。也問了一些當時碩士課程裡面的語音相關問題，還有對深度學習神經網路的理解程度。我把當時被問的題目整理成下面的bullet points：

- Describe an important project you've worked on.
- Have you ever worked on a project related to speech?
- Why is it possible to use matrix decomposition to speed up the neural networks?
- What else you can apply to with the help of matrix decomposition technique?
- Do you know how to use speech recognition tools like HTK or Kaldi?

過沒多久，我就收到了offer，也得知了要在裡面做什麼樣的project。這是有關於robust channel demixing的語音任務。如果之後有人有興趣，我也會對此單獨發一篇文來分享一下。

我知道這份實習的前半部分一定會很煎熬，畢竟當時還有60學分要努力，還得每周固定跟Thomas報告我項目的進度。我還要摸熟很多我根本就沒碰過的技術，包含HPC (high performance computing)、mini-framework、linux等等。我那時也對語音領域一竅不通，也就是剛學會一些filter bank、MFCC之類的鬼東西的程度。但隨著課程的跟進和我對這些frameworks的熟悉後，我也就開始漸入佳境。

# eSalesHub

另外一份實習，我只能說是用我之前的努力換來的回報。

## 碩論空窗期

快要畢業的時候，我的指導教授Chenghua Lin對我的碩士論文挺滿意的，所以就推薦我去一間在Doncaster的公司eSalesHub做research intern。這是一間很local的英國新創。我進去的時候公司可能才創立不到半年吧。

我在那邊的主要任務就是要把machine learning導入到公司的產品生態裡面。希望可以讓公司透過一系列的machine learning算法來提升企業獲利。

## ML不是萬能

老實說，像eSalesHub這樣的新創公司有很多data相關規範，以及如何處理data的pipelines都不成熟。**很多老闆都以為買台電腦，明天就可以把事情解決。**

我認為只有老闆懂了甚麼是AI、cloud technique、machine learning，才有可能讓技術真正落地。再來如果企業思維跟文化跟不上(例如跨部門整合)，說再多也只是徒勞。

## ML業務

我在這個項目裡面負責的產品是Intent Classification in Call Centre。簡單來說，就是要把call centre接到的所有雙聲道phone calls做分類。我當時拿到的data是經過AWS轉換過後的transcription而非原始的audio data，所以我只能把它當作一個文字分類的任務來做。我的solution是把agent和customer的文字分別做encoder，再把他們的representations做fusion後丟進一個LightGBM分類器去做訓練。假如有人敲碗想知道細節的話，我之後會再發一篇來分享。

## 實習小插曲

我拿到的dataset非常的支離破碎。轉換成文字後，裡面的斷句(tokenisation)很多都是錯的，甚至ASR的結果也不正確，然後還有一堆filling words。這對於我要做一個text classifier是極度的不友善。我跟老闆還有工程團隊反應過後也沒有任何幫助或是回應。就連我希望可以拿到更多的data samples也是經過好幾個月才拿到一個不完整的。到後來因為老闆覺得維運困難，就把這個項目shutdown了。

在此奉勸想要去新創做machine learning的人，要記得在面試的時候就先問清楚裡面團隊對於data運作處理的方式，以及遇到各種情境的應對方式。不然就會落得跟我一樣的下場。

# 結語

總之，在英國的一年半裡，我過得還滿充實的。每天都是10小時以上的coding，除了睡覺吃飯以外都是在敲代碼。實習算是海龜生活的過客而已，但也因此認識了很多大佬研究員。總覺得這樣特別的經歷以後應該也很難會有了。