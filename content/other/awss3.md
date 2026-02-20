---
title : 'AWS S3 圖床服務佈署筆記'
date : 2023-09-24T22:51:11+09:00
draft : false
tags :
- 資訊
- 雲端
description: 我原本使用一個網站的圖床服務，進行照片的代管但是畢竟是免費的服務有一些限制，例如：限一張圖 1 MB 等等。加上最近一直耳聞 S3 的服務因此好奇服務的我便開始了踩坑歷程。
---
## 動機
我原本使用一個網站的圖床服務，進行照片的代管但是畢竟是免費的服務有一些限制，例如：限一張圖 1 MB 等等。加上最近一直耳聞 S3 的服務因此好奇服務的我便開始了踩坑歷程。
## 需求
![picture 0](https://yakumotw.s3.ap-northeast-1.amazonaws.com/fd2edec943d0155d4e213e1ee0ceaa8b8f6b6da56b8872826ad48f809fbc5281.png)  

我的需求其實很簡單，就是希望在 VSCode 編輯文件時可以直接複製貼上，然後外掛自動上傳上去雲端，於是我開始尋找支援 S3 服務的外掛最後找到一個叫 Markdown Image 的開源專案，這個專案可以直接通過快速鍵的方式來把照片「貼上」到你的文章。
## 開始設定
外掛需要填入許多的資料對於 AWS 雲端服務一無所知的我陷入了困境，但隨著時間流逝我漸漸的搞懂設定的流程。
> 注意：這邊的設定流程僅僅是讓 S3 服務能動而已，詳細的權限設定請依自身需求額外設定。

1. 註冊完帳號。
當你辦好 AWS 帳號後便可以去 S3 的頁面，建立一個空間來放檔案，那建立空間的時候可以選擇資料中心，像我的話就選東京的資料中心因為我網站的讀者主要是台灣人，所以就選擇離台灣近的資料中心看看會不會速度快一些。
* 不同的資料中心價格會有些差異，請注意。
2. 建立好空間之後。
![picture 1](https://yakumotw.s3.ap-northeast-1.amazonaws.com/84f2ba3beefdd172bb742a63d465e55ab5430bac0c41d8da4c4c9f9014d06b9a.png)  

之後去 IAM 創一個使用者帳號，使用者的權限開 AmazonS3FullAccess，之後在網頁產生「存取金鑰」之後系統會給一個類似「帳號」、「密碼」的東西，一定要把它保管好，因為等一下外掛要設定使用。
3. 外掛設定
![picture 2](https://yakumotw.s3.ap-northeast-1.amazonaws.com/5aaed986f34fe1395c6ad38c860ea43129fbe1937b51ed8f4578ddd10f501a03.png)  

![picture 3](https://yakumotw.s3.ap-northeast-1.amazonaws.com/fefb7dfeeab14646ff9ca023aaf7afaf24f4cc147cd718377150ac7185b0249b.png)  

之後打開外掛並且進去設定，輸入 **Your S3 access key ID.**，這個東西就是剛剛敘述的存取金鑰的「帳號」、接著下一欄 **Your S3 bucket name.** 就請輸入你創空間時的名子、再來輸入 **Your S3 API endpoint obtained from bucket setting or dashboard. It should include protocol as well, e.g. http/https.** 的參數，這邊的話就要看你用哪個資料中心，假設你跟我一樣用東京資料中心、那麼便輸入 **https://s3.ap-northeast-1.amazonaws.com/** 快完成了接著 **Your S3 bucket region obtained from the bucket setting.** 以我的資料中心在東京為例請輸入：**ap-northeast-1** 、最後密鑰(密碼)的地方則是你剛剛在申請的「存取金鑰」的「密碼」把它複製貼上即可。
4. 進入創立的存檔空間。
進入後點選「許可」，往下滑會看到「儲存貯體政策」，請把下面的設定參數給貼進去。
`{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "MakeItPublic",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::<你的空間名稱>/*"
        }
    ]
}`
5. 測試上傳圖片
到檔案總管隨便選張照片點選複製，然後打開 VSCode 的文章介面按下【 Ctrl + Alt + V】 如果一切正常的話，圖片就會上傳並且能對外。
## 心得
綜合以上是筆者今天一整個下午踩了無數的坑得到的筆記，但是權限部分仍有非常大的改善空間，所以仍要持續研究。
