---
title: "透過 WSPR APP 來確認傳播"
date: 2023-10-18T19:15:07+09:00
draft: false
toc: false
images: [https://yakumotw.s3.ap-northeast-1.amazonaws.com/af203b1f312cbf14544a09dd61e15e61126a7df49e32e2578361214aed09aa5c.jpg]
tags:
  - 業餘無線電
  - 短波
---
## 前言
當我們出門通訊的時候往往會希望可以有好的傳播，這樣才能有高機率才能跟其他火腿通聯那麼本次將要介紹 WSPR 以及在 ios 上相關的 APP 。
## 什麼是 WSPR ？
WSPR 是由 **Joe Taylor, K1JT** 所發明的，它是一個極弱訊號的傳輸協定，它可以以小功率的射頻輸出把訊號給傳到很遠的地方，最低的解碼 SNR 可達 -34 但相對的代價是它的傳輸時間十分的長傳輸一個新標需約 110 秒，而且只能攜帶呼號、座標網格與發射功率的資訊。(等於說用用傳輸速率來換取傳輸距離)

所以該協定設計的特性就被用來觀測電離層的傳播現象當發射機發射完信標接收機收到訊號後會嘗試解碼訊號，如有解碼出來解碼軟體將會把資料上傳到網路的平台來讓使用者查閱。
![picture 8](https://yakumotw.s3.ap-northeast-1.amazonaws.com/eeaf600da9ffcc1d7ee59f7b106269ec2250e432bb3fd2fe29a835ca1a1c493c.png)  


接下來筆者將要介紹一款免費但功能強大的 ios WSPR APP 。
## 開始使用
這個 APP 可以觀察多個波段的傳播狀況但是在本次的教學中將以觀察台灣島內是否有傳播來做 SSB 通訊來做為範例。

首先[點選這邊](https://apps.apple.com/tw/app/wspr-watch/id532487317)下載。

下載完後就可以打開 APP ，該 APP 一進去的介面是長這樣。
![picture 2](https://yakumotw.s3.ap-northeast-1.amazonaws.com/9e9d676f058d30ae2e0790ee3eac5ea595cf613315737e300d51f12a0dfcae2e.jpg)  

你會發現裡面一堆根本不是台灣的呼號所以要進行資料的過濾，所以我們點選 APP 介面的 Settings 來進行資料的篩選。
首先由於我台中的家裡有代管兩台接收機來觀察傳播，所以可以在 Receiver call 輸入我的呼號 BX4ACP 。

輸入完就可以左上角返回到剛剛的設定，此時由於我們的教學是要關注島內的傳播，所以在 Band 波段選擇 40 M ( 7 Mhz )，在 Transmit call 中可以設定 BV6YA 等等台灣國內的站台，然後由於主要要觀察一天 24 小時的傳播狀況因此 Duration 設定成 24h ，再來 Server 如果不是 WSPRnet API 就選擇它這樣資料最豐富，最後網下滑把 Display local times 給打開，這樣等等圖表顯示的畫面時間就是我們本地的時間。

設定完成後，我們可點選 APP 左下角回到一開始的頁面。

![picture 3](https://yakumotw.s3.ap-northeast-1.amazonaws.com/c11f43f0e4ad2fbd70c5d6175ea3f1ae56dddc1445dbdb70eccca25aa7da89f2.jpg)

回到主頁面後就會發現 APP 已經過濾出我們感興趣的資料了，從這邊我們即可看到我託管的站台接收 BV6YA 的訊號強度狀態。
![picture 6](https://yakumotw.s3.ap-northeast-1.amazonaws.com/dbe4e353cef5f0f5c8414ec6efad327fcf312aede204d3475ade48de2895b3ac.jpg)  

但是這樣的資料還不夠視覺化，所以我們點下方的 Chart 到統計圖表的頁面。

這個畫面便是視覺化信標強度的統計圖表，從這張圖表中我們可以觀察到，在近24小時 40 米在清晨 3 點到早晨 6 點半是完全沒有傳播的，
其餘時刻有時有傳播但是時好時壞。
![picture 7](https://yakumotw.s3.ap-northeast-1.amazonaws.com/af203b1f312cbf14544a09dd61e15e61126a7df49e32e2578361214aed09aa5c.jpg)  

> 這個傳播的訊號強度是「WSPR」的，由於 WSPR 是一個可以解碼極弱訊號的協定，所以 WSPR 能收的到，在語音話務或是其他數據模式**未必**能使用。以我的經驗 SSB 大約需要 0 以上才比較有機會，而我玩的[短波 APRS 的傳輸](https://yakumo.tw/posts/2023/10/varahfaprs/)協定則是在 -10 以上有機會。

## 結尾
以上就是以觀察台灣島內傳播狀態的設定方式，事實上如果你對於其他波段的傳播也有興趣，可以進入前文所述的設定的更改篩選的資料查詢。
謝謝大家的閱讀。