---
title: "APRS 超入門 追蹤器篇"
date: 2023-09-28T21:37:46+09:00
draft: false
toc: false
images: [https://yakumotw.s3.ap-northeast-1.amazonaws.com/34311234a0c27e379579ddde05a976820b87a9093ff90769be5ff5366ebf07d7.jpg]
tags:
  - 業餘無線電
  - APRS
  - 入門
---
## 前言
APRS (全名為： **Automatic Packet Report System** ) 中文稱為自動位置封包回報系統。玩家透過該系統然後經由無線電訊號傳輸來回報自身的位置。在台灣有許多志願者架設 APRS 的接收站台可以接收你報告的位置，然後上傳到 aprs.fi 這個網站並且顯示在地圖上。

台灣使用的頻率為： 144.64 Mhz 

智慧型手機可以使用的軟體：
* aprsdroid (安卓)
* PluseModem A ( IOS )

雖然可以透過智慧型手機連接手持機，但是因為設定較為複雜，所以這邊就先帶過。
## 用專門的追蹤器連接手持機。
透過獨立追蹤器方案的優點是不需要智慧型手機，且能夠透過特製的電纜線控制手持機的 PTT 這樣比較不會「切掉」聲音；目前友站團體 TMMARC (台灣多模式業餘無線電俱樂部)，有訂製少量的追蹤器板子。

**這邊要提醒一下，雖然板子是由 TMMARC 所設計，但是 MCU 微控制器內部的韌體為泰國 [APRS Indy](https://project.aprsindy.org/) 所開發設計。**

有興趣可以進一步諮詢 [TMMARC](https://so.tmmarc.org/RwNOUL) 在官方網站上有 LINE 或是透過電子郵件 bu2ge@tmmarc.org 聯絡相關人員。

下面是板子成品的圖片
![picture 12](https://yakumotw.s3.ap-northeast-1.amazonaws.com/34311234a0c27e379579ddde05a976820b87a9093ff90769be5ff5366ebf07d7.jpg) 

![picture 6](https://yakumotw.s3.ap-northeast-1.amazonaws.com/ce341b6816375f97c324f970df6e52e8043d2c3ad701bc334a7bad55363aa6de.jpg)  

![picture 7](https://yakumotw.s3.ap-northeast-1.amazonaws.com/59395b6381a0a7d44874ebb0c9363c0ea4298ce533347814a1b775e124562ccb.jpg)

![picture 14](https://yakumotw.s3.ap-northeast-1.amazonaws.com/de44b432123ee227b2cfc7e1da6b187a42a44e5618f7d7665ad1add10eb065cd.jpg)  
呈現在 aprs.fi 的樣子
## 相關文章
[APRS 操作守則](https://yakumo.tw/posts/2023/09/radio3/)
***
**[我網站的其他文章](https://yakumo.tw/posts/)**
