---
title: "NEO-D9C 測試"
date: 2023-09-09T15:48:07+09:00
draft: true
toc: false
images:
url: /gnss/neod9c
tags:
  - GNSS
---
## 前言
在我買了 F9P 後，我無意間發現 u-blox 還有賣一款 NEO-D9C 這款 L6 訊號接收模組，可以接收日本的準天頂衛星系統 (QZSS) 在 L6 的頻段提供的 CLAS 高精度差分訊號，這個訊號能在不使用任何地面 RTK 服務（網路 RTK、現場架設基準站）的情況下，提供高精準度的差分訊號，而且這個服務是開放給大眾使用的，於是我找到日本一家公司推出的 NEO-D9C 的開發版，便購買來進行研究。由於該模組需要跟 F9P 配合才能發揮效用，而我的 F9P 暫時還沒到貨，所以暫時無法測試實際定位的精準度。於是本篇文章將先單獨使用 NEO-D9C 模組，透過電腦上面的軟體來讀取資料。

## CLAS 簡介
這個是日本的準天頂衛星系統 (QZSS) 新開放的L6頻段的校正訊號；原理大概如下：首先收集部署於日本國土內各地的 GNSS 連續觀測站的資料，然後透過網路的方式把原始資料送到一個處理中心進行訊號的分析，最後把分析出來的校正訊號上傳到衛星，然後衛星再往地球廣播校正的訊號。至於在台灣能不能使用這個訊號，這個要等我八月份回台，進行實測才能知道。（精度較低的 SLAS 則是確定可用）
![](https://i.imgur.com/dhT4dwX.png)
[圖片來源](https://www.magellan.jp/fundamental/166)
## 開箱
賣家是使用黑貓郵寄，盒子非常的完整。
![](https://i.imgur.com/hUcFe82.jpg)
打開裡面後的樣子。
![](https://i.imgur.com/MFPQBkV.jpg)
模組接收器盒子本體，讓我們繼續看下去。
![](https://i.imgur.com/RDIWxWr.jpg)
打開後印入眼簾的是開發版的簡單說明書。
![](https://i.imgur.com/TCwcrbr.jpg)
終於快要看到本體了。
![](https://i.imgur.com/odiCeTk.jpg)
登登~開發版本體出現啦 NEO-D9C 就在板子的正中心。
另外那根跳線，是要接給 F9P 的，等於說訊號先進來到 NEO-D9C 然後再把訊號餵給 F9P 。
***注意事項： NEO-D9C 開發版天線座的旁邊，有一個控制是否要灌電的開關，由於 F9P 會灌電，在這邊請把開關用成「開路」的狀態，此步驟很重要，如果忽略可能會損壞模組設備。***
![](https://i.imgur.com/zGseik8.jpg)
接上傳輸線以及訊號線，開始測試。
![](https://i.imgur.com/3BWslhD.jpg)
開始有訊號進來了，不過我們可以進去設定頁面的地方看到更詳細的資訊。
![](https://i.imgur.com/tsJQVzN.jpg)
這邊可以看到 L6 的廣播訊號的原始資料。
![](https://i.imgur.com/XyO308V.png)
這邊展示了整體訊號強度以及受到干擾的程度。
![](https://i.imgur.com/o79tbWO.png)
收到的衛星狀態，上空兩顆衛星都有收到。
![](https://i.imgur.com/qEDRC7Y.png)
## 後記
由於我的定位模組明後天才會到來，所以今天的測試就只能先到這邊了。
