---
title: "APRS 超入門 智慧型手機篇"
date: 2023-09-28T21:54:33+09:00
draft: false
toc: false
images: [https://yakumotw.s3.ap-northeast-1.amazonaws.com/8be261e0b0ae07632c17a41976ec0ee12a3067b8bc05e7a31e7523eb95ed1bea.png]
tags:
  - 業餘無線電
  - APRS
  - 入門
---
## 前言
昨天的[這篇文章](https://yakumo.tw/posts/2023/09/aprsstart/)介紹了使用專門的追蹤器硬體然後搭配手持機進行發射，今天本文則是要介紹透過智慧型手機以及藉由手持機的 VOX 功能進行 PTT 的觸發，進而達到發射的目的。
> APRS 需要有三等呼號方能使用，如果你還沒有呼號請看[這篇文章](https://yakumo.tw/posts/2023/09/hamtest/) 
## 原理
許多手持機的麥克風都是使用 3.5 mm 的孔，我們可以透過 VOX 功能、3.5 mm 音源線以及手機 APP 來進行發射，原理是這樣的：
1. 手機接收到衛星訊號，丟給 APP 做處理。
2. APP 產生 APRS 的封包並且調變成聲音。
3. 透過 3.5 mm 的音源線把聲音送到手持機。
4. 聲音觸發手持機的 VOX 進而打開 PTT 進行發射。
## 實戰操作

> 以下教學這邊就使用 APRSdroid APP 進行示範。
由於現在主流的新手機，已經沒有 3.5 mm 音效孔，所以要開始之前，你必須去手機配件行買一個 USB 轉 3.5 mm 的轉接線。

1. 造訪 https://aprsdroid.org/ 進行 APP 的下載與安裝。
![picture 0](https://yakumotw.s3.ap-northeast-1.amazonaws.com/f18ca3705bf258a2ac84f5648f844cbaaa66ad0908dfc8f78718dda32b516e50.png)  

2. 打開 APP 後先進入設定中。
![picture 1](https://yakumotw.s3.ap-northeast-1.amazonaws.com/80a3809f729e1a4b32615fe4d3beb5855e188ed8db414fcbe32cd5b044397d81.jpg)  

3. 第一個選項輸入自身的呼號。
4. SSID 通常選 5 。
5. 點進去 APRS 設定。

![picture 2](https://yakumotw.s3.ap-northeast-1.amazonaws.com/be4a59aa6a63c0ffbc1f746f3ac49a0c60401b54eace9994d0392cadd9e82a58.jpg)

6. 模式選擇 AFSK 。
![picture 3](https://yakumotw.s3.ap-northeast-1.amazonaws.com/e880199da628587f8955beff1d9f1f9b26d87b15c0efe9267a37e51021a6d42f.jpg)  

![picture 4](https://yakumotw.s3.ap-northeast-1.amazonaws.com/7fcad161dd179a9669bcea070cbd72fe0d0e5836abc3c5fbc59c01979b48f4dd.jpg)  

7. 設定完成之後，返回首頁。 
8. 手持機打開 VOX 功能並連接你的智慧型手機。
9. 把手持機轉到 **144.64 Mhz** 並且點擊右下按鈕，開始發射訊號。
![picture 5](https://yakumotw.s3.ap-northeast-1.amazonaws.com/21cef2ebf22123accb781e756304950da9ad968ea7cefc346e2a61946bfa575b.jpg) 
10. 帶著手持機與你的手機上樓發射，並且開啟 [aprs.fi](https://aprs.fi) ，看看是否能被周遭的站台給收到，如果有被收到，你將會在地圖上看到自己的圖標與呼號。

以上是 APRSdroid APP 進行最簡單的設定與操作，這個 APP 功能很多讀者們可以進行摸索
> 如果發現手機無法觸發 PTT 那麼請將音量調整到可以完整觸發的大小以及手持機 VOX 靈敏度調到最高。
## 相關文章
[APRS 操作守則](https://yakumo.tw/posts/2023/09/radio3/)

[透過專門硬體發射](https://yakumo.tw/posts/2023/09/aprsstart/)
***
**[我網站的其他文章](https://yakumo.tw/posts/)**
