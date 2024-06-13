---
title: 'APRS A3 追蹤器開箱'
date : 2024-06-04T19:59:34+08:00
draft: false
toc: false
images: [https://yakumotw.s3.ap-northeast-1.amazonaws.com/2cd1a9f8844dcd7f0464f5027713da07c43942f2fa6710d58ef531fee490b706.jpg]
tags:
  - 業餘無線電
  - APRS
---
## 前言
在[這篇文章](https://yakumo.tw/posts/2023/10/vhfaprs/)中，我展示了 TMMARC 所開發TMMARC 團隊出了一個 APRS 追蹤器，在經過一段時間後， TMMARC 開發出了更小巧的 APRS 追蹤器板子，名為： A3 。

>板子是由 TMMARC 所設計，但是 MCU 微控制器內部的韌體為泰國 APRS Indy 所開發設計。
 https://sites.google.com/view/aprs-indy/circuitfirmware
## 介紹
開箱後打開會看到這塊小小的板子，它就是 A3 的本體，採用 Type C 供電，並且使用 3.5 mm 規格的方式來連接 GNSS 定位模組以及無線電，此外 A3 採用 ESP 單晶片控制板作為解決方案，並且韌體搭配支援可以透過 WI-FI 進行各種 APRS 的設定以及 OTA 升級。

![圖 4](https://yakumotw.s3.ap-northeast-1.amazonaws.com/0df084cd73f208189afa264d0c32e1083941db0078a82e4893a71d0ac5878d50.jpg) 
本體在出貨的時候， OLED 螢幕不是焊死的，所以可以依需求把螢幕給移除掉。

![圖 7](https://yakumotw.s3.ap-northeast-1.amazonaws.com/94419204deef64a2ed01e0e71b720fe086b85b10652289cc85b226c6f10ee268.jpg) 

板子 I/O 的樣子。
![圖 8](https://yakumotw.s3.ap-northeast-1.amazonaws.com/3515b01580e04b0eed07f818950ed11fd37bb79b65f7082ad36ca135b212b5b2.jpg)

箱子內包含的纜線： 3.5 mm 轉 K 頭與 GNSS 接收模組的連接線。
![圖 10](https://yakumotw.s3.ap-northeast-1.amazonaws.com/d1edaa0c04277a19cf287eb1895ab9e48ad0bdbe67b73aea542111061cd0d224.jpg)

在簡單介紹完外觀後，我們接上所有需要的纜線。
![圖 9](https://yakumotw.s3.ap-northeast-1.amazonaws.com/281e8f232d1cebc3bb5903d174829741e7be2b06223a88cecc52eb251ec23cb2.jpg) 

供電後所出現的介面，進度條顯示了載入的過程。
![圖 11](https://yakumotw.s3.ap-northeast-1.amazonaws.com/eaed208db1351f4c70050319dc7cc765d92d961231b41e855f11727c21ab77f2.jpg)

這邊顯示的 AP ON 就是剛剛提到的可以透過 WI-FI 連線進去做設定的功能。
![圖 12](https://yakumotw.s3.ap-northeast-1.amazonaws.com/5139b15957267982948f4a6c08073f807d4a389f895579a2a219cd04cfa37781.jpg)

此圖顯示了我的呼號以及該韌體的版本。
![圖 13](https://yakumotw.s3.ap-northeast-1.amazonaws.com/12391031d252db4ff84e6d2e873f9d97293afcded4999b559ba27b5fdcf0f05d.jpg)

主介面等待定位的畫面，基本上線有接好， GNSS 模組很快就會抓到您所在的位置。  
![圖 16](https://yakumotw.s3.ap-northeast-1.amazonaws.com/79857fd1eade0945d13623738ba0f5506d5b73d94a5d4b658202c251f61e8df5.jpg) 

原則上我們在出貨的時候就會幫您設定好所需的資訊，但是您可以連接 WI-FI 後輸入 192.168.4.1 
進入設定的網頁中進行調整。

![圖 19](https://yakumotw.s3.ap-northeast-1.amazonaws.com/a822300c07eeef4d0f8116036eb2c0e1ff604e290b77d5946f59122787abbc1d.jpg)

此韌體除了支援智慧信標的功能，也有支援 MIC-E 壓縮格式透過壓縮技術把封包縮的更小，來減少發射時間。
智慧信標的發射頻率，基本上已經調整到最佳值，除非有特別必要否則發射頻率不宜過高以免造成當地 APRS 頻率壅塞。
![圖 23](https://yakumotw.s3.ap-northeast-1.amazonaws.com/eb183a71175e09cee1f7dce8ebd1b174031442f4e23f5076b348023e0f232cb2.jpg)

![圖 18](https://yakumotw.s3.ap-northeast-1.amazonaws.com/3c3734a739d0206d0f40f4af202ec7564a3b36a97b39773b4a63f37ba8fa9393.jpg)  
  
![圖 20](https://yakumotw.s3.ap-northeast-1.amazonaws.com/b972a89fb23120ed09a6333d2827e21a147f2b7dbc45769eba5bc6ab3b8b5ce9.jpg) 
 
![圖 21](https://yakumotw.s3.ap-northeast-1.amazonaws.com/127118276fec630f798f6be62428c61dc1bbc165ee194165ce7ef50bbc3c5d81.jpg)  

![圖 22](https://yakumotw.s3.ap-northeast-1.amazonaws.com/3c3734a739d0206d0f40f4af202ec7564a3b36a97b39773b4a63f37ba8fa9393.jpg)  
最後接上 UV5R 等等支援 K 頭介面的無線電，即可開始使用。 

![圖 24](https://yakumotw.s3.ap-northeast-1.amazonaws.com/c10c651dceaf17a93e0a6c902fcc3a2fdf4e39a12aa20f1853943ae0af2b71ca.jpg)  

## 上路實測
路測時所記錄下的軌跡。
![圖 25](https://yakumotw.s3.ap-northeast-1.amazonaws.com/d267b010a89eb9da6f8e57f56d1ef77b200026c27cef8e762b98dd7584dd1dc6.jpg)

在封包的資訊欄內，可以顯示電壓、抓到的衛星數等等。
MIC-E 字樣代表封包有壓縮。
![圖 26](https://yakumotw.s3.ap-northeast-1.amazonaws.com/88bb5e5b9de696f3073d8e0ed1613b5363b17429f7be22d534c6fd948c3b4e62.jpg)  

## 購買與售價
目前 A3 的售價是 500 元，有興趣可以進一步諮詢，在 TMMARC 在官方網站上有 LINE 或是透過電子郵件 bu2ge@tmmarc.org 聯絡相關人員。
