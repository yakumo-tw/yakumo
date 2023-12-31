---
title: "基於數位模式短波 APRS 座標傳輸實驗"
date: 2023-09-08T22:28:17+09:00
draft: false
toc: false
images:
tags:
  - 業餘無線電
  - APRS
---
## 計畫內容
採用HF波段來進行 APRS 的發送，以便實驗透過短波發送自身座標的實用性。

* 動機： VARA 是一款西班牙 OM 所開發的高性能軟體數據機。從我接觸了 VarAC軟體後，這款軟體，隨著版本的發展 VARA 支援了 KISS AX.25 的資料模式，這樣的支援使得透過 VARA 進行 HF APRS 的應用得以實現。在幾個月之前我與 BX2AI 進行合作試驗，初步的試驗結果非常的成功但是還有幾點事項要做進行一步的試驗。因為 BX2AI 實驗的條件是屬於效率較高的 HF 車天線，加上有良好的車體接地所以通訊效果非常好，有可能是天線系統良好才達成的，本次 3/18 放假回台試驗，將使用長度不到兩米的「M哥」車天線進行試驗。

* 目的：進行這個短波 APRS 的實驗，並非要取代現有的 APRS 系統，而是增加整體生態的多樣性。我的想法如果可以透過車用 HF 天線，進行 NVIS 通訊這樣可以用少數的 HF 接收站台進行全台大範圍的訊號涵蓋，形成一個國內 HF APRS 通訊網。

* 實驗設計： BX2AI 位於北部的站台啟動接收，我這端採用「M哥」車線，接地的部分，則採用透過磁貼片地網進行接地。無線電設備則採用中國製的協谷 G90S ，並且使用 20W 的功率進行發射，除此之外還需要使用筆電執行 VARA 數據機軟體與手機 APRS軟體最後配使用 G90S 專用的數據介面盒進行無線電的控制。

* 備用計畫：由於筆者於 3/18 回國，在到家放好行李整理好設備 (IC-7300) 後便會前往 BU4AK 的住所進行設備交接，接著我會透過拿到的 G90S 後，開去郊區進行電腦控制電台的測試，萬一遇到 G90S 介面盒異常無法正常運作，我將改用 IC-7300 進行計畫的備案，止步過採用的車天線無法以 100W 進行發射，根據「M哥」賣家提供的資訊，天線的耐入力不能超過 40W ，所以保險起見如果使用 IC-7300 發射將會把功率限制在 30W

### 
## 實作方法
要實作數據模式的發送，需要有數據機軟體，以下將簡單介紹兩種數據模式方案。
這項實驗的成敗，除了電腦是否能正常地控制電台外，電離層的傳播也是很重要的事情，因為如果再沒有 NVIS 的傳播狀態的情況下出去做發射的試驗，將只是進行無謂的行為，所以這時候本次實驗會打算參考 WSPR 的信標接收站所回報的訊號強度，來實測重台北信標站打到筆者台中的接收站所需的 SNR 大約需要多少。在40米有傳播的狀態下，我將會開車出門，距離大概會去郊區，以及再有機會的時候進入市區，看看在都市複雜的建築環境中，訊號能否正常傳出去。
### VARA HF
由西班牙火腿開發，有 KISS TNC 的功能，可以控制收發機(CAT)收發。

![](https://i.imgur.com/U5BiReG.png)

https://rosmodem.wordpress.com/

### JS8CALL
此方案是開源的，拿FT8協定進行修改，透過第三方軟體可以發送座標網格。
### 接收站
* 目前20米波接收站暫定為我東京宿舍這邊。使用的天線是有源小環天線。
* 台灣那邊的站台使用 EFHW-20 天線，電磁環境乾淨，接收效果良好。

### YAAC
YAAC 是一個由 JAVA 所撰寫的APRS軟體，它能在各個平台上運作，經測試能與VARA HF 配合良好。
![](https://i.imgur.com/GlWf3mL.png)
### 移動台的設定
首先要當移動台發送座標，必須有下面幾個條件
1. 無線電收發機。
3. USB傳輸線(老機器則是要搭配介面盒)
4. 短波車天線
5. 電腦(包含樹莓派)
6. GNSS接收器
7. YAAC軟體
汽車在移動的過程中，GNSS 會不斷的接收最新的座標訊息，透過序列埠傳輸到電腦之中，然後由 YAAC 解析訊息得到座標，之後 VARA 會以 4PSK 的調變方式發送 APRS 封包，無線電 PTT 的控制將由 VARA 數據機軟體負責。
![](https://i.imgur.com/L3BAJBY.png)
### 接收站台的設定
原則上接收站台需要有以下能力。
1. 有網路。
2. 與收發機連接的能力。
3. 安裝相關軟體。
4. 設定好站台資訊以便在地圖上顯示。
#### 不會佈署實驗環境該怎麼辦？
可以聯絡我，我會嘗試幫忙解決問題。
## 實驗時間
目前還在計畫規劃階段，所以具體實驗時間不確定，但如果計畫有開成，暫定為期一週的實驗，再這時間範圍內，可以嘗試發送封包。
## 實驗階段(一)
由於我3月11日尚未回台，所以無法實際以無線電進行傳輸實驗，但感謝 BU2GF 對此試驗感到興趣，加上又有 IC-705 所以得以進行實驗。

首先在這邊先感謝 BU2GF 的熱情協助，讓本次正式實驗開始前有機會做一個測試。
我們這次使用的設備是IC-705搭載第一電波工業的HF40FX天線以及地網貼片，根據 BU2GF 所發生的經驗，地網貼片在貼上車體表面之前由於可能有灰塵等等物體影響了接觸導致駐波不良，那後來解決的方法是，在車體吸附地網的地方先灑一點水沖掉灰塵，讓磁貼片能夠有效的發揮作用，最後駐波也降下來。最後再接上一顆 USB 的 GNSS 定位模組，在筆記型電腦上。
![](https://hackmd.io/_uploads/rkPBkoFC3.jpg)

軟體的部分則是採用 YAAC 以及 VARA 進行配合，在 YAAC 的設定中，分別設定了 KISS_TCP_TNC 以及 GPS 這兩個 Ports ，最後調整 VARA 中控制 IC-705 發射的 PTT 選項，來讓整體系統工作起來。

今天測試的地點在新北市的一處河濱公園的停車場內，以及實際開上路測試，這邊先來敘說在停車場的測試；在停車場測試時，當 GNSS 模組抓到衛星訊號後，就可以透過手動或是軟體時間到就自動發射的機制來發出封包，由於傳播的變化以及各種複雜的因素，我們剛開始定點實測時，最低有只用 3W 讓我台中的接收測試站台，給接收到，但後來隨著千變萬化的傳播狀態，使的那麼低的功率無法再被接收到，所以 BU2GF 便接上外部供應電源來讓 IC-705 可以以 10W 的功率進行發射，以求通訊的穩定。
![](https://hackmd.io/_uploads/BJmDkitR2.jpg)

在做完停車場的定點測試後，便開始了道路實測，在路上為了方便我監測 YAAC 是否正常運作的情況下，我們使用了遠端控制軟體，以方便我這邊進行，軟體設定上的調整，這樣 BU2GF 就能專心的開車。雖然軟體一切正常，但是我們遇到一個問題：軟體發射時間的間隔有點過於長，這導致了畫在地圖上面的點過於稀疏，最後目前是以調整「智慧信標」功能的參數來嘗試解決問題，詳細問題是否有解決要看接下來的測試。

而大家最關注的通訊傳播測試，目前測試起來雖然不是百分百封包都有解碼出來，但是整體效果還不錯，也有在一些看似對於短波通訊不利的地方，例如：周遭許多建物以及大樓的道路、高架橋底下等場所，發出訊號成功被接收到的案例，相反的也有在看似能好通聯的地方，然而卻沒被收到的狀況，這些情形都有，但我們兩個都還覺得效果還不錯。
## 實驗階段(二)
今天繼續跟 BU2GF 繼續實驗，不過今天發生了一個奇怪的插曲，原本昨天不會發生的共模電流干擾，今天竟然發生了，據 BU2GF 所表示，並未更動任何東西，最後暫時解決的方法是降低發射功率，來避免問題的發生，而最終的防範方法就還是裝上磁環。
![](https://hackmd.io/_uploads/ry4MJjt02.jpg)
經過昨天軟體設定的調整，目前發射的頻率是一分鐘一次，再加上有些封包訊號太微弱所以沒有解出來，所以點就比較稀疏。
## 實驗階段(三)
回到了台灣後，我進行 VARA HF APRS 的實驗，實驗蠻成功的，基本上，我發送出去的封包大約有6-7成有被 BX2AI 的站點給接收到，整體而言可以畫出一個大致的輪廓，有一定的實用性。
![](https://hackmd.io/_uploads/BkWXbiK03.jpg)

接下來我將經由南橫到達台東。
以下是我環島的實驗所產生的軌跡圖。
![](https://hackmd.io/_uploads/B1CnbjY0h.jpg)
![](https://hackmd.io/_uploads/r1jpbjFA2.jpg)
***
# 更多精彩文章[請點我](https://yakumo.tw/posts/2023/09/)
