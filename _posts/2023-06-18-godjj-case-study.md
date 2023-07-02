---
layout: post
title: "用godjj的steam帳號被盜事件淺談個人資安防治"
subtitle: ""
date: 2023-06-18
author: "Peter"
header-img: "img/post-bg-2022.jpg"
tags: [資安]
---

> 懶人包: 被盜走的原因很有可能是信箱外漏連帶其他綁在一起的steam洩漏，聯絡steam客服取回，並在信箱、steam上面用手機驗證可以緩解這類攻擊手法。

今天godjj的帳號打開發現登不進去，並被其他好友發現在玩永劫無間，可以確定的事情有：

1. 帳號被外國人登走
2. 信箱被改掉
3. 原信箱內有很多帳號驗證碼的通知信，以及通知信箱更改的信件
4. 本人表示有開啟信箱驗證
5. 本人表示信箱好像沒有二階段驗證

從種種跡象可以大概率判斷是信箱被盜走所引起的一系列攻擊手法，攻擊者只需要拿到信箱就可以登入你帳號關聯的所有其他服務。

拿到信箱的方法有很多，坊間有很多帳號洩漏的檔案，基本上有心人士都找得到。我建議各位可以頻繁地查看自己的密碼是否有外洩，網站有很多，例如： https://haveibeenpwned.com/
這邊分兩個部分講如何守好自己的資料，首先是steam帳號，steam帳號提供了兩種保護手法，一種是透過email接收驗證，另外一種是透過手機的app接收。我建議除非很篤定自己的信箱不會被盜，不然我推薦使用手機驗證，手機驗證的好處是其他人幾乎無法獲取，就算手機遺失去通報客服也需要好幾天的作業時間。

另外一種則是信箱驗證，godjj這次的情況很有可能就是信箱驗證所衍伸出來的，當只用信箱驗證時，steam帳號基本就是綁定於信箱上，則信箱的安全控管就會非常重要，強烈建議在信箱上開手機的二階段驗證，或是用實體金鑰如yubikey。

有一部分的人講有可能是cookie洩漏或是木馬，這兩者有一定的關聯性，我分成兩個部分談，首先是木馬程式。現在的木馬程式主要是透過網路釣魚的手法，誘拐用戶開啟一個pdf檔等等的文件在電腦上開啟一個後門。比較常見的網路釣魚中，攻擊者會透過email等等方式誘導用戶在電腦上執行程式，並直接將你的電腦資料傳送出去。

其中電腦資料裡面，最有價值的莫過於瀏覽器的資料，而瀏覽器中就有大家講的cookie(session)，用戶只要複製你的session令牌就可以在任意的電腦上假裝是你操作。這類攻擊多發生在youtube的頻道上，時常看到很多youtube頻道被改成一些加密貨幣的頻道，多半都是攻擊者通過執行後門，將瀏覽器中的cookie竊取並登入youtube更改資料。

但本人親測發現，steam在進行這類的操作十分嚴格，不像youtube只要有cookie(session)就可以更改頻道的東西，而steam在執行如更改帳號密碼email這類的行為時，都需要再進一步的驗證。而且買賣過程規則相當嚴格，必須要開啟行動驗證才能進行物品交易。
另外一種是透過瀏覽器的javascript竊取cookie，這類攻擊統稱XSS(跨瀏覽器腳本執行)，這類攻擊現在變得比較少，因為瀏覽器的防護規則變得嚴格，通常不會允許其他網站的程式碼存取cookies。

況且，一般windows電腦上面應該都會裝有防毒軟體，此外也很難透過簡單的一個pdf程式安裝後台(就我所知在windows電腦的情況下)。但防不勝防，新的攻擊手段層出不窮，最好還是管好自己的手，看到一些詭異的程式就不要執行。或是把檔案先丟到 https://www.virustotal.com/gui/home/upload 看看是不是病毒。

總的來說，我會建議各位把自己信箱、高價值服務的二階段驗證設定好，並避免使用同樣的密碼於各式服務。可以使用密碼管理器等等產生密碼也方便記錄。如果覺得太麻煩的話，記得一定要把手機驗證打開，手機驗證或是手機的authenticater是現在最安全的幾個驗證之一。

本文同步發布於粉專：[PP學習筆記](https://www.facebook.com/pplearningnote)