---
title: "Mobilinkd APRS 數據機開箱心得"
date: 2024-06-13T23:02:28+08:00
draft: false
toc: false
images: [(https://yakumotw.s3.ap-northeast-1.amazonaws.com/b5a08b332731f4b80149139f3b461d7b2b75cd3578575245fc9e996fc1ff1341.jpg]
tags:
  - 業餘無線電
  - APRS
  - 開箱
---
## 前言
在上次[介紹完 APRS A3 的產品](https://yakumo.tw/posts/2024/06/aprsa3/)後，這次的文章我將來介紹，我去年底買的 APRS 數據機。這邊列出官網上面敘述的規格。
### 規格
>* 支援藍牙 4.2 （雙模 EDR/LE）可在 iOS 上使用。
>* USB序列埠，可以連接電腦進行 AX.25 的傳輸。
>* DCD 和 TX LED 指示燈。
>* 內建 DSP 和數據機。
>* 高動態範圍 ADC 和 DAC。
>* 緩衝輸入和輸出。
>* 輸入放大器可改善更廣泛無線電範圍內的輸入電平匹配。
>* 針對分組無線電和 M17 資料模式進行了最佳化
>* 900mAh 充電電池可持續使用 2 天
>* TNC4 使用 USB-C 連接器進行充電和 USB 序列埠連接，支援 M17 資料模式，並使用 TCXO 來改進符號定時。
>* 支援 1200/9600 位元率的 KISS TNC。它能夠進行 AFSK、GFSK 和 4-FSK 調變。
>* 續航力可連續使用 48 小時。 
>* TNC 尺寸為 80x42x15mm ，重量 48g 。

這款數據機售價 149.95 美金(不含運)，價格其實有點高，另外連接手持機的纜線價格是另外計的，當初我也是想了好久，但最後還是剁手買了下去。

A3 價格僅需 500 台幣。

## 開箱
包裹的樣子，為了節省運費我把貨寄到一路發美國轉運倉，然後再寄回台灣。
![圖 4](https://yakumotw.s3.ap-northeast-1.amazonaws.com/a531bc07b67392970929fbfa672bda731fad0db214c0a7300213d40a3ec5d463.jpg)  

商品的本體，除此之外我還有購買連接到手持機的音訊纜線。
![圖 5](https://yakumotw.s3.ap-northeast-1.amazonaws.com/92a355284eda7ef6a098d8da627218062298e6a3b66b9a6e4494a9543d0a40aa.jpg)  

其實音訊纜線上面買很不划算，但是礙於我不會 DIY 加上回國時間短，所以就直接敗下去。
![圖 2](https://yakumotw.s3.ap-northeast-1.amazonaws.com/f2ef324680fc61c7ede68c559bf94a7b84aafb83e583acfc7107037375f0bfa7.jpg) 

打開盒子，數據機本體就長這樣，十分的小巧方便。
![圖 1](https://yakumotw.s3.ap-northeast-1.amazonaws.com/b5a08b332731f4b80149139f3b461d7b2b75cd3578575245fc9e996fc1ff1341.jpg) 

來張正面特寫。
![圖 3](https://yakumotw.s3.ap-northeast-1.amazonaws.com/66e33df7c5507361c54b52a261ff75500523da79d6e97f06829ad6cfb6f973fd.jpg)  

這數據機外表是最大的敗筆，尤其是接頭的地方。
![圖 0](https://yakumotw.s3.ap-northeast-1.amazonaws.com/f7c6a730aa4e5f3ade7d3a19951f99edeb4ae3f75779a16df7ce449f98e37754.jpg) 

把數據機接上手持機的樣子。
![圖 11](https://yakumotw.s3.ap-northeast-1.amazonaws.com/8d29b281a9f21e1e4d32dd16bd8f662bd589dce36953336f91de669d54e99cb5.jpg)  

## 開始使用
由於它只負透過藍芽接收 KISS 包然後把封包調變成 AFSK 的音訊並控制 PTT 發射，因此需要與手機做搭配；可以搭配的 APP 在不同平台有所不同，以我主力手機 ios 系統下我覺得最好用的 APP 是 APRS.FI 這個付費 APP ，在下文將會有 APP 的介面的截圖。
### 設定部分
這個數據機可以透過該廠商發行的 APP 設定數據機的參數，例如：收發音量大小、 AFSK 速率(台灣用 1200 bps )以及觀看電池剩餘電量；那麼要透過它來發送 APRS 封包，就需要像是 APRS.FI 的APP 來進行發射。

打開 APP 即可看到你的裝置。
![圖 15](https://yakumotw.s3.ap-northeast-1.amazonaws.com/e337e96aea12b9f2b9adbc35dfa19781a723ed78ad8ef87ffceea427d8d5e714.jpg) 

設定裡面的介面。
![圖 16](https://yakumotw.s3.ap-northeast-1.amazonaws.com/6418d622a2898d1d324bdc6c6a6a3a27b808c96e901f79a86d24ae853fd186c9.jpg)

電池剩餘電量。
![圖 17](https://yakumotw.s3.ap-northeast-1.amazonaws.com/b100742c85f05421c29158645463cf7d564fe74a2871dcfc8070a46a52100973.jpg) 

可以調整上述提到的參數，原則上就保持預設即可。
![圖 18](https://yakumotw.s3.ap-northeast-1.amazonaws.com/1371f5808140de58cc6cbcd84938ebe5f5cc69625512510539a4e36016d14db7.jpg) 

這個數據機除了支援傳統的 AFSK 外還支援 9600 bps 的規格以及新興數位模式 M17 但是我們暫時用不到，所以也保持預設。
![圖 19](https://yakumotw.s3.ap-northeast-1.amazonaws.com/edff1e61585c12c798183d447f7e511edddd18f8709bdb5dd4ed27844d16566d.jpg)  

### 開始使用
要開始使用，裝好 APP 外下一步就是，用藍芽跟數據機做配對，配對的方法為打開上述的 APP 然後進入 TNC 設定的地方，打開你的數據機後，手機便會找到然後就可以按下去配對，成功後把數據機如下圖接上手持機，就可以了。
***
與 A3 不同，作為一個數據機它是雙向的，因此可以解碼手持機傳進來的訊號，如果想要作為雙向使用，可以把 SQL 關掉然後透過前文敘述的設定 APP 確認輸入進來的音量是否會過大過小；如果音量大小沒有調整好，會影響接收的效果，所以要特別注意。
## 帶去登山啦
筆者收到設備後的隔天，便帶去爬山。
![圖 12](https://yakumotw.s3.ap-northeast-1.amazonaws.com/f8dfe022315c01ea8674da1fa494582270361919060589fc96cf8c393594b18f.jpg) 

把設備放在背包側邊的樣子。
![圖 13](https://yakumotw.s3.ap-northeast-1.amazonaws.com/b648a164e10587294ae084f88adff0b87840a9fb755c804cf7de1b136b9b27b9.jpg) 

由於我行走的山徑屬於高點，加上有其他站台轉發，因此在地圖上出現了在平地的其他玩家的位置。
![圖 14](https://yakumotw.s3.ap-northeast-1.amazonaws.com/7bcf718f768314f500f205984d94e8344dc7e56e9b620dbf429fa23109f7e6ce.jpg)  

與此同時我移動的時候，位置也有持續的被站台給收到，並且轉發到網路上。

## 心得
經過使用這款數據機以及 TMMARC 開發的 A3 (韌體由泰國愛好所開發)，其實兩者產品各有優缺點，這個數據機雖然連接手機很方便，但也會產生手機沒電就無法使用的問題，以及價格十分的高昂；但優點是接線十分簡潔，而且數據機本體內建電池，因此不需要多出一條電線來供電。
***
A3 最大的優點是便宜，一組不包含手持機的 A3 追蹤版僅需 500 元台幣即可入手，並且完全獨立運作，不需要依賴手機提供位置，但相對的要連接的線路比較多，以及沒有內建電池所以還需要而外額外供電。除此之外還要外接一條 GNSS 定位模組的纜線，因此線路會比較繁雜不優雅。
***
但總體個人的觀點是， 雖然本次開箱的數據機功能性比 A3 來的多，但是 A3 價格的優勢可以想玩 APRS 的玩家輕鬆入手，因此如果您預算足夠，可以考慮買本文介紹的數據機，相反的 A3 也是一個不錯的選擇。


