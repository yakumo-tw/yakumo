---
title: "airspy hf+ discovery 踩雷記"
date: 2023-10-08T14:49:53+09:00
draft: false
toc: false
images: [https://yakumotw.s3.ap-northeast-1.amazonaws.com/b6ae4d37c7741bfd1949b3df726fc0197bbc641cb3458b4d45f97800b5192595.jpg]
tags:
  - 業餘無線電
  - 短波
  - SDR
---
## 前言
去年我去日本的時候，我在日本買了 airspy hf+ discovery 的 SDR 來使用，這款 SDR 涵蓋範圍有從高頻來到甚高頻，並且擁有高動態範圍的設計，我拿到貨後使用上也十分的滿意，因為它接收短波的性能十分的良好，不會因為過強的訊號而導致過載。
![picture 3](https://yakumotw.s3.ap-northeast-1.amazonaws.com/b6ae4d37c7741bfd1949b3df726fc0197bbc641cb3458b4d45f97800b5192595.jpg)  

## 故障
然而在一次我長期掛機後，卻發現有時候它會失去訊號，然後搖動一下訊號線又會恢復收訊，起初我以為是訊號線接觸不良但直到有一天它就完全收不到訊號了，無論我怎麼搞它就是完全收不到訊號，所以此時我想可能是硬體哪邊出問題了，所以我就把設備帶回台灣給 Neo_Chen 做檢查。

經過檢查基本上排除軟體上的問題，於是 Neo_Chen 把設備的殼拆開，來尋找硬體層面的問題，經過了一番檢查以及相關人士的指導， Neo_Chen 發現了是訊號線脫焊了，而 Neo_Chen 的好幾位朋友都有遇到一樣的問題，最後判定是硬體故障。

## 維修
知道故障的點在哪邊後， Neo_Chen 著手開始維修，首先去電子材料行購買細小的漆包線回來並且開始維修，首先先拿漆包線然後把線的其中一小小小段給切斷做為等下重新連接的素材，再來打開 SDR 設備的保護殼然後把內部的遮蔽金屬片給取下，然後開始用鑷子夾著電線並且焊接，在焊接的過程中需要十分的精密的穿過遮蔽層，不能讓遮蔽層與傳輸訊號的漆包線導通；最後經過一番的焊接以及使用電錶量測後確定沒有問題， Neo_Chen 才把殼裝回去並且重新接上電腦做測試。
![picture 0](https://yakumotw.s3.ap-northeast-1.amazonaws.com/32d76a07ec6d6dfe3b56031c49bce68f8a6095b4c36b352e13394868f3ecb9b6.jpg) 

![picture 1](https://yakumotw.s3.ap-northeast-1.amazonaws.com/72acf9802908737519a502e717880e4868b59d5c6d34b7ff66e5609cba896c21.jpg)  

![picture 2](https://yakumotw.s3.ap-northeast-1.amazonaws.com/1d21703d9df1f7a83bd142432434d37c12cf87e4b728022a4c31f7bd80f848e4.jpg)  

![picture 4](https://yakumotw.s3.ap-northeast-1.amazonaws.com/dabe0dcff08b6569822d8e68fe6844f45d59814cb5a9bb4ddb5715906def7622.jpg)  

![picture 5](https://yakumotw.s3.ap-northeast-1.amazonaws.com/937da9e8e30e76917abb1da19d27643b2730702384227dadb8262aa889ae7eaf.jpg)  

## 成功
接上電腦後測試，剛開始原本以為沒有收到訊號，但後來經過調整電腦接收軟體後就收到了訊號確定了修復成功， SDR 也恢復原本的性能了。
***
## 心得
雖然這款設備的短波接收能力十分的良好，但是有這個設計上的缺陷實在十分的可惜；如果不是 Neo_Chen 幫我修復的話，官方的維修服務則要 50 美金價格十分的高昂。所以有意透過 SDR 來接收短波的愛好者，要購買此型號的設備建議還是要三思。
