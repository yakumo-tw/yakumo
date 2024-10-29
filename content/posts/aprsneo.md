---
title: "TMMARC APRS Nano-Pi NEO 專案"
date: 2024-10-28T23:04:33+08:00
draft: false
toc: false
images: [https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/1ae63aafba2a3729bba57193766facd5.png]
tags:
  - 業餘無線電
  - APRS
---
## 前言
APRS (全名為： **Automatic Packet Report System** ) 中文稱為自動位置封包回報系統。玩家透過該系統然後經由無線電訊號傳輸來回報自身的位置。在台灣有許多志願者架設 APRS 的接收站台可以接收你報告的位置，並上傳到 aprs.fi 的地圖上。

無論你是使用 [A3 追蹤器](https://yakumo.tw/posts/2024/06/aprsa3/)還是使用[手機連接](https://yakumo.tw/posts/2023/09/aprsphone/)無線電來發射 RF 訊號，皆必須由愛好者所架設 [iGate](https://yakumo.tw/posts/2023/10/igate/) 給接收或 DIGI 轉發；經過幾年的努力，台灣除苗栗、東部外，大多數地點皆能成功回傳座標。

這張地圖藍色的涵蓋範圍，是我們採用 Direwolf TNC 站點進行解碼的效果。
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/c71361aa8b3c302bcdc4f6977945c914.JPG)

[Direwolf](https://github.com/wb2osz/direwolf)是火腿 WB2OSZ 開發的解碼軟體，有著開放原始碼以及跨平台運作的能力，由於解碼能力十分的優秀，因此我們的專案採用它來當 TNC 。

在之前的[文章](https://yakumo.tw/posts/2023/10/igate/)，TMMARC 團隊使用基於電視盒運作的 Direwolf iGate 作為解決方案，但隨著專案持續的進化，電視盒的穩定度以及效能的擴充性受到了嚴峻的挑戰，此次 TMMARC 改用了執行 Linux 的 Nano PI 並進行介面板的開發。

## 展示
與電視盒方案一樣，採用了 Linux 方案的作業系統並且執行開放原始碼的 Direwolf 解碼軟體，由於 Nano PI 有 GPIO 擴充口，所以我們設計了一個擴充板疊在 Nano PI 上面並且透過 3D 列印機設計了一個外殼。

我們設計的 OLED 螢幕會顯示以下資訊：
1. 接收封包的呼號。
2. 接收封包音量。
3. PR 封包類型
4. 經緯度與時速。
5. 與自身站台的方位角。

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/1ae63aafba2a3729bba57193766facd5.png)

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/9750915df23df04d43889fb154de3b37.jpg)

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/4f130a1fd73cd4b884450c29b30d7be4.jpg)

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/7d2c806a4eda941f11b7b60fb31e0ec8.jpg)

側面有一個 USB 與乙太網路的介面可以使用，這樣的設計大大增加了佈署設備的彈性。

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/a57114ae618ed16a08143269ab2cf39f.jpg)

擴充板設有可以接 OLED 的螢幕以及溫溼度感測器模組的介面。

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/ae94be358c1ff070512ddf67b4cb305d.jpg)

組裝起來後與車機的 DATA 孔進行連接。 OLED 上面會顯示 Direwolf 即時解碼的封包資訊。

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/70271d16e1f303fc20a95a384e8d0995.jpg)

底部做了散熱孔。

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/cc9e0b67f23346ab293a84633aad345c.jpg)

耗電量僅 1 W 。
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/9cc2e8085a7b84f6dd55ffa3c3a315e0.jpg)

接上感應器一週後的統計圖。
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/10/87da144413f4f6fb024f0bfd308eebb3.JPG)

## 我們專案的特色
* 採用開源的 Direwolf 解碼可靠強大。透過設定檔可以切換 iGate 與 DIGI 模式
* 標準的 DATA 連接器可以支援有數據模式的車機。
* 板上開關可以在 1200 bps 與 9600 bps 之間做切換。
* 耗電量低適合用在太陽能的場景。
* 執行 Linux 系統，可彈性調整需求。
* 板上預留 I2C 介面可擴充感測器或其他設備。
* 板上預留 TNC 介面，可使用支援 APRS KISS 協定的設備控制。
*	音量可以用板載的精密可調電阻調整。
## 聯絡方式
有興趣可以進一步諮詢，請洽Line：nelson1214 。

官方網站：https://www.tmmarc.org