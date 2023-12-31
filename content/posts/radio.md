---
title: "APRS over LoRa 系統介紹"
date: 2023-09-08T22:28:13+09:00
draft: false
toc: false
images:
tags:
  - 業餘無線電
  - APRS
---
## 概要
這個專案是我們引用sh123 的[開源 LoRa 專案] (https://github.com/sh123/esp32_loraprs)
進行改寫的部分，在這個倉庫中裡面的版本，有些是移除掉藍芽功能純跑 iGate 的程式碼，由於藍芽佔的程式體積過於龐大，所以我把它給移除，並且加進去了 OTA 的功能，以利遠端維護程式碼。
## 簡介
傳統的封包無線電中，我們在 FM 上使用 AFSK (Bell 202) 調變傳輸 AX.25 訊框；不過到了 2020 年配合物聯網使用的低成本無線通訊模組變得常見，其中 LoRa 協定特別適合使用於業餘無線電中(有現成的，能運作在 UHF 業餘頻段的模組)，於是我們構想透過 LoRa 來進行 APRS 封包的傳輸。
LoRa是一個低功率遠距離的傳輸協定，它可以透過展頻來增強在弱信號狀況下的解碼能力，且對 CW (Continuous Wave) 干擾有一定的免疫能力。
經歷了很久的發展，我們的板子到了第三代，雖然我們的專案停滯了一段時間，但最近我們重啟了這項專案。
<!--more-->
## 專案特色
* 相容性高：我們只有把實體層的傳輸協定改成 LoRa 其他層協定皆與傳統 APRS 無異，因此可以相容現有 APRS 的軟體。
* 成本低廉：追蹤器成本標配目前價格為 725 元，需搭配安卓手機使用。
* 開源免費：我們的電路圖以及程式碼皆以 GPL 3.0 開源條款授權，您可以自由地使用這個專案。
* 通用性：除了可用我們設計的板子之外，還可以使用TTGO T-Beam 、 T-Echo 的現成開發版來發射(但是比較不建議)
## 價格表
### 三代
* 標配版本 725 元。
* GNSS模駔 +500 元。
* 充電版 +100 元。
* OLED +125 元。
* 電池 尚未採購。
### 四代
* 標配版本 等待報價中。
* GNSS模駔 +500 元。
* 充電版 +100 元。
* OLED +125 元。

* 目前三代版沒有現貨，而一次訂購需要做五片，大約需要兩千多元的成本，所以有興趣購買者可以聯絡我，我會盡快安排。


## 實際運作
我們採用了國外開源作者 sh123 的[開源LoRa專案](https://github.com/sh123/esp32_loraprs)進行使用，而這個倉庫是存放我們修改過的程式碼，這個專案蠻符合我們的需求，所以就採用這個作者的開源作品，大家有興趣可以進去專案的頁面點個星星鼓勵作者。
sh123 的程式可以不使用 GNSS 定位模組，透過手機藍芽連接 ESP32 ，然後丟資料給 ESP32 之後再透過 LoRa 模組進行發射。
另外原本基於 ESP32 的 TNC 接收到封包後還必須透過 USB 序列傳輸到電腦的 APRS 軟體內，最後再上傳到 aprs.fi 上，但是 sh123 的專案的解決方案，為直接使用 ESP32 的網路功能進行封包的上傳，這樣架設接收站台，就不需要依賴電腦或樹梅派了。
在某些需求下有可能會使用 GNSS 模組例如：認為依賴手機不便者或是說使用 ios 的使用者，這個時候可以考慮選配版子的 GNSS 模組進行改裝，再搭配 BX4ACV 寫的程式碼來進行燒綠。
如果沒有版子但是有 TTGO T-Beam 、 T-Echo的版子，最近我成功移植到這兩個平台，不過功能還在測試中，使用時可能會遇到一些問題。 
## 待完成的坑(軟體方面)
* 雖然 sh123 的專案很讚，但仍有一些缺點，例如：它的 BLE 功能有問題，無法正常運作，這樣導致 ios 的使用者透過 APP 進行連線時功能無法正常的運作。
* DIGI 功能有潛在的問題，尚在研究中。
### 空中 AX.25 訊框格式
與標準 AX.25 相同，有使用 CRC 來檢查封包是否毀損，如果毀損就丟棄。
## 材料/零件
### 追蹤器
如果你想要自己訂製 LoRa 板子可以到板子作者 BV5DJ 的[專案頁面](https://oshwlab.com/GabeH/esp32-lora-aprs)存取，板子的電路圖，並且送訂單給嘉利創製造板子，當然這也是開源的，所以你也可以自己重新設計自己喜歡的樣式。
或是可以在淘寶自行購買 TTGO T-Beam 的 LoRa 開發版來使用，
## 通訊距離
我們使用發射端運作在 UHF 頻率，以我的基地台 (iGate) 使用 106cm 的車天線，移動端的部分採用 40cm 的手機天線在車車外發射，目前極限距離最遠來到 7Xkm (北屯到梅山鄉瑞峰附近)，在市區的話以台中為例：東半部基本上可以涵蓋，由於我的基地位於北屯，所以台中西邊的區域效果可能會比較差，但經過以放大器增加功率，並把手持機天線吸在汽車引擎蓋上，在台中西側發射仍可以收到封包。
至於東側部分，目前測試到太平那邊都是可以收到的(如下圖)
![](https://i.imgur.com/mjEsOoi.png)
![](https://i.imgur.com/3BtYAFu.jpg)
![](https://i.imgur.com/b3jXKll.jpg)
神雅潭自行車道測試( 400mW 40CM 手持機天線)
![](https://i.imgur.com/n1fLJiH.png)

新竹外婆家測試，我接收端使用 40cm 手持機天線，然後發射端使用長度很短的普通 433Mhz 通訊天線。以下是測試的結果。
![](https://i.imgur.com/AN6cF3s.jpg)
![](https://i.imgur.com/OGKoSRt.jpg)
![](https://i.imgur.com/yfxdXKi.jpg)
新竹後來安裝車天線試跑的結果圖

## 涵蓋範圍
目前實測涵蓋範圍。條件 40cm 手持機天線 2.6W 發射。
台中站： 106CM 車天線。
新竹站： 11XCM 車天線。
雲嘉站： 200木瓜。 
### 台中
1. 北屯區。
2. 新社區(部分)
3. 太平區。
4. 霧峰區。
5. 西屯區。
### 彰化
1. 八卦山-彰化段。
2. 北斗
### 南投
1. 八卦山-南投段。
2. 國道三號南投路段。
### 雲林 
* 開車經過有被接收到，實際涵蓋仍需測試。
![](https://i.imgur.com/Y4b8RPA.png)
1. 古坑。
2. 斗六。
3. 斗南。
4. 土庫。
5. 東勢。
6. 台西。
7. 麥寮。
8. 嘉義快速道路沿途。
9. 西濱沿途等地方。
10. 國道一號西螺服務區以南，台南鹽水區以北。
## 專案連結
https://github.com/sh123/esp32_loraprs

### 專案依賴的函式庫
依照 sh123 作者的實作，以下是您需要安裝的函式庫。
1. Arduino ESP32 (ESP32的開發環境)。
2. RadioLib (控制LoRa晶片用的，我們採用SX1268晶片)。
3. Arduino Timer。
4. CircularBuffer。
5. DebugLog。
## 通訊參數
頻率： `430.64Mhz`。
頻寬： `125kHz`。
SF： `12`。
CR： `8`。
CRC： `2`。
LORA_EXPLICIT：`false `。
SYNC： `0x12`。
PWR： `22`
## 討論社群
如果您有興趣想要購買板子來玩或是您遇到問題想要詢問，可以透過以下管道連絡到我們。
1. 我們的 Telegram 社群 https://t.me/NeoNetworkHamRadio 。
2. 加我的 LINE ID：pepetoad
## Q&A
### Q：相比傳統的 FM AFSK 傳輸方式 LoRa APRS 有什麼優勢？
LoRa 具有低功率遠距離的優勢，如前文涵蓋範圍的 Demo 我們僅使用不到 3W 的功率(模組本身 1W )就達到了廣大涵蓋範圍，雖然傳輸速度僅僅 18Xbps 但是對於座標的傳送已經十分足夠。
### Q：為何你們要採用 E22-400M30S 這款模組？
當初在選購模組時，主要會採用有兩點：
1. 模組有一瓦的輸出功率。許多 LoRa 模組僅僅幾百毫瓦，我們認為瓦數過低。(加上功率放大器可以來到 2W 但是模組不能全功率輸出，不然長期下來模組的功率會衰退)。
2. 該模組採用最新一代的 SX1268 晶片，相比上一代的 SX1278 晶片，新一代的晶片具有更低的功耗以及更強的接收能力，再加上該模組有 LNA 的設計，讓接收的靈敏度最低可達 -14Xdbm 比依據公式計算出來的靈敏度還要更高。
### Q：為何你們不要使用現成的 LoRa32 晶片的開發版( TTGO系列 )來當追蹤器就好？
其實我們有購買TTGO T-Beam 的產品來做實驗，但發現了幾個缺點：
1. 採用上一代晶片。
2. 輸出功率僅 100mW
3. 內建的 GNSS 定位模組過於老舊，性能不佳。(新的 T-Beam 改採用較新的晶片，可以考慮購買)
以上這些因素所以我們自己設計板子，並且使用 E22-400M30S 這款模組，根據我們在國外 LoRa APRS 的社群中觀察發現，已經有人採用這款模組了。
但是 TTGO T-Beam 的優勢是成本比我們自己製作的來的低，對於預算有限的參予者可以考慮這個選項。
* 目前藍芽版本的韌體(sh123)以及使用 TTGO T-Beam 內建的 GNSS 定位模組發射皆可以使用， ios 使用者請安裝使用內建 GNSS 的韌體。
### Q：我對此專案有興趣，可以索取版子來玩嗎？要收費嗎？有什麼必須條件？
如果您的 QTH 位於台中、雲林、嘉義、新竹，這些地區目前有站台涵蓋，如果沒有架設站台意願的人，可以僅索取追蹤器。
目前三代版，不含 GNSS 定位模組等等附件，**價格725元**。收費是為了專案的永續經營，如果不想付費可以自己送PCB板子去製作，或者是購買價格較低的 TTGO T-Beam 來使用，程式碼的部分已經放在該專案的 GitHub 的倉庫之中。
### Q：我覺得選配的零件太貴了，我可以自己買零件來 DIY 嗎？
可以喔，板子是您自己的，你想怎麼改都行，也歡迎分享改裝心得。
### Q：前面有聽你提到放大器，這個再購買板子時會附嗎？
根據目前試驗下來的結果，如果不是在都市叢林內，其實 1W 基本上就可以通很遠了，但如果您希望功率可以更大的話可以[點我](https://item.taobao.com/item.htm?id=572168568304)購買放大器。
**請注意：**
如果您使用放大器，LoRa 模組不得超過 316 mW 否則長期使用下來模組的發射功率會衰減。(調整方式請聯絡我)
### Q：我有動手做的能力，我發現板子上有預留一些電路接頭可以來改造它嗎？
可以的。我們的專案是全面開源的，而且版子是您自己的，您可以在本頁面找到電路圖等等資訊，在符合 GNU GPLv3 的條件下都可以自由改裝。
## 拿到套件該注意的事項
### 開機時請一定要接上天線
這樣做是確保在不確定模組何時發射時，不會因為駐波過高而損毀模組，所以請開機後一定要接上天線。
### 可以接放大器，但.....
請注意放大器的最高功率耐入力，輸入過高的功率給放大器，除了會造成模組的發射晶體功率衰退外，長期使用下來放大器會燒掉(親身經歷)。
### 架設iGate注意事項
在iGate模式下，當發送信標時，除了會向網路送封包以外，射頻部份也會發射，所以千萬要注意您的天線系統是可以發射的。
### 架設站點周圍有強訊號
如果您架設站台周遭會有過強的訊號，你必須買帶通濾波器來過濾強訊號。
![](https://i.imgur.com/LmuoAmr.jpg)

## 關於以及程式碼授權
此專案所有文檔以及程式碼均以 GNU GPLv3 或更新版本釋出  
程式作者：BX4ACV（交流電）(一代、二代板子的程式碼)、sh123 (三代板子採用)。
PCB電路板開發：BV5DJ
程式研究與改良：BX2AHP
站台場地架設、程式研究：BM2OBM https://www.tmmarc.org
感謝以上同好的努力與付出，沒有你們就不會有這個專案。
專案贊助推廣：BX4ACP（蜜蜂）  
***
# 更多精彩文章[請點我](https://yakumo.tw/posts/2023/09/)

