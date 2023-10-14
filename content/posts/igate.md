---
title: "APRS igate 架設記"
date: 2023-10-14T21:07:16+09:00
draft: false
toc: false
images: [https://yakumotw.s3.ap-northeast-1.amazonaws.com/9ceef1faaf52419f59980483cb4db0ee1ea742a2d46b4e918d31c2a5753f6aff.jpg]
tags:
  - 業餘無線電
  - APRS
---
## 前言
前幾天我收到了 TMMARC 的設備套裝這個套裝是要用來安裝 APRS igate 的所以就來開箱，希望可以幫忙增加大台中地區的 APRS 涵蓋。
## 開箱
收到包裹開箱的照片，裡面除了 igate 的套件外，也因為筆者的要求給了[這篇文章]()的追蹤器。

![picture 0](https://yakumotw.s3.ap-northeast-1.amazonaws.com/9ceef1faaf52419f59980483cb4db0ee1ea742a2d46b4e918d31c2a5753f6aff.jpg)  

igate 硬體的構成不會太複雜，因為我們採用軟體 TNC 解決方案進行解碼，採用軟體式 TNC 的好處是調整的彈性高且解碼能力強目前長期使用下來也沒有解出亂碼的問題，但缺點是與硬體 TNC 相比解碼速度會慢一些些並且建構的成本會高一點。

這個套件包主要有：
1. 電視盒：負責跑軟體 TNC 我們採用 DireWolf 這套開源解決方案。
2. 車機。
![picture 2](https://yakumotw.s3.ap-northeast-1.amazonaws.com/200bc1df73376bc802be6bc2eee73b7112a63fe349f7dd55a3d7fc5d5441f829.jpg)  

3. 音效介面卡
![picture 3](https://yakumotw.s3.ap-northeast-1.amazonaws.com/3b7d965ee3b06a99ac2f1c22a92f1a47521a0036b614540a8b56d7a8d0658c15.jpg)  

4. 轉接頭。
***
而佈署設備基本上十分的簡單，因為我們在出廠時就會幫您搞定一切的設定，你唯一需要準備的就是良好的天線與饋線以及一台電源供應器；而佈署的過程則是：
1. 拿出車機。
2. 把盒子內附贈的音效介面卡插到車機的背面。
3. 用箱子附的纜線把音效卡與電視盒做連接。
4. 電視盒接上網路線。
5. 開啟電源。

以上就是基本的佈署步驟，如果一切順利很快您將會在 APRS 的地圖上看到您站台的圖標。
## 實測
在撰寫這篇文章之前，我架設好設備後便拿著[這篇文章](https://yakumo.tw/posts/2023/10/vhfaprs/)介紹的追蹤器出門趴趴走來測試我站台的涵蓋率，下圖便式我測試出來的結果。

![picture 4](https://yakumotw.s3.ap-northeast-1.amazonaws.com/e27a52438d3d6ad630d1332b3271727a98aaf3f974a2629c513beadac98a1b83.jpg)  

這樣的結果再搭配台中其他火腿站台的貢獻，讓台中市的涵蓋又更上一層樓。


