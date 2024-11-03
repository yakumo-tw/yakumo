---
title: "開源數位語音模式 FreeDV 安裝使用教學"
date: 2024-11-04T00:30:18+08:00
draft: false
toc: false
images: [https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/11/ab6cd7349aee5117813c915c7135f174.JPG]
tags:
  - 業餘無線電
  - SWL接收
  - 短波
---
## 前言
FreeDV 有別於 DMR 、 D-Star 與 P25 等數位語音模式，它是個開源免費的語音通訊模式，主要跑在短波上面，此專案發展了十年多在十月中下旬終於推出了，基於**機器學習**技術的新的編碼模式 RADE 。
在此之前筆者已經關注 FreeDV 已久，雖然在這十年中該專案推出了好幾款語音編碼模式，但是音質卻是不盡人意，因此筆者遲遲未介紹，然而今年的六月份，中國大陸的玩家傳給我官方部落格的 RADE 的 Demo 影片，音質與之前的編碼模式相比有大幅度的提升，這讓我感到驚艷；而到最近 RADE 終於千呼萬喚始出來，推出了 2.0 的預覽版供大家使用。
## FreeDV 的亮點
### 開源
如近年來很夯的 FT8 一樣，FreeDV 它 100 % 公開程式碼以及運作的原理；沒使用任何有專利的編碼技術，這意味著只要遵守它開源條款的情況下，可以自由地的使用散佈該程式。
這樣的特色，將來如果 FreeDV 持續地成熟起來，說不定未來會像 FT8 一樣，有廠商把該模式內建到無線電設備之中。
### 低 SNR 音質優於傳統 SSB
此次發表的 RADE 編碼技術，在 SSB 傳播複雜多變的短波環境下，可以盡可能地維持理想的音質；這要歸功於 RADE 除了使用傳統的 FEC 糾錯外更導入了**機器學習**的技術，讓整體通訊的可靠性變得更加穩固。
## 下載與安裝
要開始玩 FreeDV 要先準備好以下的東西：
1. 短波收發機或 SDR 。
2. 連接無線電的 USB 纜線。


接著去官方 Github 下載程式。[下載點](https://github.com/drowe67/freedv-gui/releases/tag/v2.0.0-20241018)


如果你的系統是 Windows 就下載 **FreeDV-2.0.0-devel-2024-10-18-b6d65bc2-windows-x86_64.exe** 。
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/11/fee4a1257e936144d3ebefc4a594d208.JPG)
下載完成後打開安裝檔進行安裝。 
> 在安裝的過程中會出現「黑底白字的文字視窗」，這是因為要安裝讓 RADE 正常運作所需的函式庫，因此**不要關閉它**，它跑完會自動關閉。

## 軟體初次設定

安裝完成後打開 FreeDV 的程式；第一次開啟會跳出設定的介面，我們需要進行一些設定才能讓你的無線電與 SDR 開始運作。

以筆者的 IC-7300 為例，因為該型號的設備有內建音效卡，所以只要驅動你有安裝，基本上接上 USB 纜線後，電腦就會抓到 IC-7300 的音效介面。

> 使用 SDR 做純接收的朋友，需要安裝 **虛擬音效卡** 來把聲音餵進軟體內；安裝完在 **Radio Device** 的地方就選擇 **虛擬音效卡** 的選項。

此時我們在名為 **Radio Device** 的下拉式選單中選擇你無線電的音效卡名稱。
接著在 **Decoded audio plays back through** 的下拉選單中，選擇你的電腦喇叭或是耳機的介面。最後 **Transmitted audio records through** 中選擇你**電腦**要來拿來說話的麥克風。


> SDR 玩家選擇 **NO PTT/CAT Control** 即可。
再來我們要設定 PTT 控制，選擇 **Hamlib CAT Control** 後，出現的下拉式選單意思如下：
* **RIG Model** ：你的無線電型號。
* **Serial Device** ：你無線電的序列埠號碼。
* **Radio Addres** ：這個似乎是 ICOM 的設備才會出現的，正常來說保持預設即可。
* **Serial Rate** ：你無線電的序列埠速率，請依照無線電主機的設定來調整。
* **PTT uses** ：選擇 **CAT** 即可。



為了讓我們上線時能被別人知道，我們可以啟用 **Enable Reporting** 功能，並且在呼號框以及網格座標框填入你的資訊。

都設定完後，點選 **OK** 完成設定。
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/11/0c02f0980732287ade3fe5b1b7f546f6.JPG)
進入到主畫面，在右側 **Mode** 的地方選擇 **RADE** 然後按下 **Start** 後軟體會正式啟動並開始解碼，此時我們就快要調整完畢了。
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/11/21ad9f090ab361ea6e80b0cbe3f50c0e.JPG)
接著要來調整無線電的 ALC ，以 IC-7300 為例，在無線電的操作面板中進入到 **METER** 後即可看到 ALC 狀態，此時我們按下軟體介面的 **PTT** 後觀察 ALC 大小，如果發現 ALC 有起錶，那麼就調整軟體中的 **TX Attenuation** 拉桿。直到 ALC 不起錶為止。
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/11/e74c9fc39fc1b16660dc438b47526f56.jpg)

## 開始使用
上面的設定都搞定後，我們就可以來測試，按下 **PTT** 後開始講話，如果麥克風設定正確的話，就會出現你講話的波形。

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/11/ab6cd7349aee5117813c915c7135f174.JPG)

> 此時可以點選去[這網站](https://qso.freedv.org/)看目前上線的友台所使用的頻率，如果對方是在守聽的狀態下，你就可以嘗試呼叫看看啦。

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2024/11/12cd20943ec1a7797d4c3555a960889a.JPG)

## 軟體未來的展望
目前開發團隊並未就此打住，除了解決其他潛在的 BUG 外，根據 [Github](https://github.com/drowe67/radae/issues/28)的頁面未來將會持續強化以下功能。

1. 把程式碼移植到 C 語言，讓運作的效率更佳，未來更有可能在崁入式裝置(例：ESP32等)運作。

2. 新增文字通道。

3. 進一步強化模型，讓性能更佳強大。

