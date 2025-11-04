---
title: "Meshtastic APRS 設定教學 (iOS)"
date: 2025-11-04T20:45:41+08:00
draft: false
toc: false
images: [https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/63e62fa9643ee5fac986cea9e29c301b.png]
tags:
  - Meshtastic
  - APRS
---

如果你有三等(含)以上的業餘無線電呼號，可以在筆者與朋友開發的平台註冊帳號，做完此部分的教學，您的位置就可以顯示在 [APRS.fi](https://aprs.fi/)上面。

以下教學適用於：
1. 持有呼號的使用者
2. 持有內建 GPS 模組的隨身節點
3. iOS 使用者

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/d19a16a65817a546dbbc92766d104d7e.png)

## 註冊平台帳號
首先請先點擊下方連結
平台網址：https://callmesh.tmmarc.org/

點擊「申請加入」
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/63e62fa9643ee5fac986cea9e29c301b.png)

輸入註冊的基本資訊與呼號，且同意使用者條款，點選「送出註冊」
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/a10bb6b95cd89839ae45ffb0412bc689.png)

註冊成功後輸入剛剛註冊的帳號密碼並「登入」
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/8be499c78f994f56ded2756d7d1acadd.png)

登入後介面如圖，此時請點選「Mesh Mapping」
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/d29ff3c9d9b31608970089cb3b82369a.png)
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/0a6f36e550cdbebdecfb4a502a6becd1.png)

進入後點選「新增 Mapping」
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/80a546689c41f3c5616eb8376b79cf8f.png)

複製您的「使用者ID」
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/97343bcfeb17a183a790a96a04f10e27.PNG)

填入「MESH ID」、「SSID」 任選一個、「Symbol 圖示」選擇一個想要的圖案
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/03d8edbfdf4e8c3aca0ff32d2cf71371.png)

點擊「建立」這樣即完成註冊裝置的動作
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/d952184a6f17b8e7b6331b1a6bb45306.png)

打開您的 APP 到聊天頻道的頁面，如果看到「0」號頻道的鎖頭為「紅色」的，那請繼續接下來的步驟
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/c3590d3fe2af0b780b9f80c8940f5e94.PNG)

進入「設定」，點擊「LoRa」頁面
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/7ac4d7920784a6ead9a7e4e851deac75.PNG)

請與教學圖片保持一致的設定
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/aed01dbc6bc37c720723718013abfac2.PNG)

接著上一頁回到「設定」，點選「定位」選項
這邊請依需求設定位置發送的速度
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/62f190d619b7bc1e53061d9da59da185.PNG)

保持一致的設定
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/6ef1a35de962b5db6341fd81cd826d48.PNG)

位置標記，建議都關閉以增加傳輸成功的機率
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2025/11/c51e4eb7866cf5e44059ebd99eee1c6c.PNG)

最後儲存設定讓裝置會重新開機。

## 如果鎖頭是黃色怎麼辦？

由於 iOS 開發者對隱私的堅持，如果你當初設定節點時，有用 iOS 版本的 APP 覆蓋網頁 QR Code 的設定，那麼您的位置精準度會受限制，此時請使用手機瀏覽器，點選[此連結](https://meshtastic.org/e/#CgsSAQEoATABOgIIIAo3EiCKwOEes2kk-UZfcYEkFfqSO4rspA2nhnQzs5MOmdfk3hoGTWVzaFRXJQEAAAAoATABOgIIIAo7EiDLUdyJWCmXkfOHTkolR7-6ZZQfxeEbdSNHWu9kd9QcVRoKU2lnbmFsVGVzdCUCAAAAKAEwAToCCCAKOxIgy2jnf86fTpf_4AFAf-mCwbzRoxpCV0P90dqJo0-w_SYaCkVtZXJnZW5jeSElAwAAACgBMAE6AgggEhEIARAEOAhABkgBUBZYAcgGAQ)

然後重新設定頻道資訊。

## 結語

完成以上的教學，您即可去頂樓或是街道走走；如果您的位置封包有被接收到，在 [https://aprs.fi](https://aprs.fi/) 即可看到您裝置的位置。

謝謝收看。