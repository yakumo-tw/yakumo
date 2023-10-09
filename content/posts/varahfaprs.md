---
title: "VARA HF APRS 第二次試驗"
date: 2023-10-09T14:46:13+09:00
draft: false
toc: false
images: [https://yakumotw.s3.ap-northeast-1.amazonaws.com/ee3b5e72d9b9e585ca516b500796e51aec7a981511388ac32c4259fa0b0f2b31.png]
tags:
  - 業餘無線電
  - 短波
  - APRS
---
## 前言
在今年的三月份的[這篇文章](https://yakumo.tw/posts/2023/09/radio2/)我與 BX2AI 合作進行了一次環島的 APRS 試驗，那次的試驗除了清晨一段時間幾乎沒有傳播外，其餘時間都成功的收到訊號。而本次回台的短短 8 天中，我又重新再做一次試驗。

短波 APRS 的最大優勢是透過 NVIS 原理來傳播訊號，所以訊號的傳輸比較不會受到建築物等等障礙物的影響(實測在周遭都是建物的小巷弄也能成功打出去)。

![picture 5](https://yakumotw.s3.ap-northeast-1.amazonaws.com/16764bcdf3c9ce11d85421703498190275a914a7b9926afa6566a2028f4b04d7.jpg)  

## 開始實驗
條件也一樣使用協谷 G90 搭配 M 哥的車用短波天線並且啟動天調，並且使用安卓手機開啟熱點，建立起一個區網然後讓我的 iphone 啟動 APRSFI 的控制 APP 最後打開筆電的 VARA 數據機，然後 ios 上的軟體透過區網連線到電腦的VARA ；無線電的 PTT 控制是由 VARA 進行的，但是有可能是軟體 BUG 的原因，常常開車開到一半， VARA 對 PTT 失去控制，導致發射時沒有觸發 PTT 進而導致封包沒有傳出去，所以後來我就改用 VOX 方案，在 G90 開啟 VOX 這樣當無線電偵測到 VARA 發出聲音時就會啟動 PTT 發射訊號，改成這樣的設定也讓穩定度大幅提升。
![picture 0](https://yakumotw.s3.ap-northeast-1.amazonaws.com/61fe33b360ee5d3355bce88d12eac274b745cf05e0d1454cb32912928f9b5d62.jpg)  

> G90 輸出最大功率是 20 W 在設定電腦餵給無線電的音量時要注意， ALC 是否過載，以 G90 為例當發射時螢幕上的 ALC 數字越接近 100 越好，根據 VARA 作者的建議，發射的 ALC 不要超過整體的三分之一否則很有可能 ALC 的關係導致訊號失真，造成解碼上的困難。 

## 成果
以下的圖片是我開車外出測試的結果，原則上大多數封包大約 78成都有被 BX2AI 北部的站台給接收到。所以畫出來的軌跡基本上都很完整(除非 PTT 失靈)
![picture 3](https://yakumotw.s3.ap-northeast-1.amazonaws.com/ee3b5e72d9b9e585ca516b500796e51aec7a981511388ac32c4259fa0b0f2b31.png)  
跑去四面環山的地方也能被接收到

![picture 4](https://yakumotw.s3.ap-northeast-1.amazonaws.com/13ee8ad1780ed57ac9db0b050c11776aa5bb96fba6321b338e33433c1ae65dcd.png)  
一路上的軌跡

![picture 2](https://yakumotw.s3.ap-northeast-1.amazonaws.com/b65189595667bd3ef0f9d1066954481faf5ab65a1740fff830476b2473298872.jpg)
全部的總軌跡  
## 缺點
VARA HF APRS 的缺點是由於數據機軟體閉源的加上是使用 VB6 這個古老的框架設計，所以導致難以移植到其他的裝置(要在 Linux 系統上執行需要額外步驟，導致使用的門檻會比較高)，目前不支援手機作業系統因此無法在手機上面執行這樣導致，要使用這個模式要嘛需要一台筆電或是樹梅派之類的小電腦。

另一方面因為工作頻率的物理特性，天線無法太小隻否則效率會變得極差，所以車天線有一公尺長，因為家人不願意再車上安裝固定式天線座，所以我必須使用磁鐵吸盤把天線吸在引擎蓋上面，即便如此也還是要注意限高的地方，是否會卡到天線。
> M 哥的車天線金屬彈性算很好，但是還是要盡量小心不要勾到東西以免發生危險。
***
更多精彩文章[請點我](https://yakumo.tw/posts/)
