---
title: "電波上的即時通-VarAC"
date: 2023-10-14T15:14:38+09:00
draft: false
toc: false
images:
tags:
  - 業餘無線電
  - 短波
---
## 前言
有沒有想過在短波上面使用像 LINE 的方式跟對方聊天？今天我們要介紹的短波數據模式就是可以實現自由文字聊天。

像 JS8CALL 這類的軟體，雖然跟 VarAC 相似但是最大的差別是 JS8CALL 只能傳輸英文字母無法傳輸 UTF-8 的字符，這使的沒有額外再編碼是無法傳輸中文的。

## VARA HF 與 VarAC 的關係是？
在入門VarAC的玩家們可能會困惑說 VARA 與 VarAC 到底差在哪邊，其實很簡單就是作者不同而兩者軟體扮演的角色不同。

VARA是西班牙火腿所開發的數據協定，它除了可以應用在 VarAC 以外還能支援 AX.25 這也使的可以跟 APRS 做結合來透過它來發送短波 APRS ，詳細的資訊可以參考我寫的的[這篇文章](https://yakumo.tw/posts/2023/09/radio2/)以及[這個試驗](https://yakumo.tw/posts/2023/10/varahfaprs/)，除此之外它目前是短波電子郵件服務 Winlink 市佔率最高的協定，因為跟商用數據機相比， VARA 的完整版許可證遠比商用數據機便宜，所以受到許多人的青睞。

而 VarAC 的作者則是以色列人，根據他的自我介紹他從接觸業餘無線電後就很喜歡玩數據模式；在前年作者開始開發 VarAC 並且與西班牙的作者保持的聯繫，但是雙方互相不隸屬。

所以 VarAC 採用 VARA 通訊協定因此在開始使用 VarAC 的軟體時，必須先安裝 VARA 。
## VARA 到底要不要收費？
在你使用 VARA 數據機時如果你沒有花錢買許可證，它會跳出要求你付費的視窗原因是這樣的：因為 VARA 是共享軟體，它雖然也可以免費使用但是功能上會有些限制例如：傳輸速度、資料壓縮等功能，付費解鎖完整版需要 69 美金，但看是昂貴的價格，如果你跟專業的短波數據機相比 69 美金簡直是便宜到爆，至於要不要花錢解鎖我覺得要看個人；如果你是剛入門 VARA 生態系的新手，可以先觀望試用，如果真的覺得這個模式很實用在付費即可，目前付費機制是買斷制序號跟你的呼號做綁定。

這是 VARA 數據機的傳輸速度表， VarAC使用 500 Hz 的頻寬來進行文字的傳輸，而免費版本最高可以達到 177 bps 的速度。
![picture 12](https://yakumotw.s3.ap-northeast-1.amazonaws.com/559c5bb435bc378a70afb847697de6cffae5c0b2dffb3d2e82391e1164079c9c.jpg)  

以我付費購買使用的案例為例，通常文字傳輸最高速度就會跑到 270bps 左右。

而其中左側兩邊分別是戰術頻寬( 2750 Hz )以及寬頻( 2300 Hz )，這兩個頻寬通常是 WinLink 使用，而要跑到如此高速，除了你要買許可證以外，更重要的是 SNR 要夠高。

VARA 協定的傳輸速率就如同我們的手機通訊系統一樣，是採自動調整速率的，當訊號良好時數據機會自動切換到較高速的調變方式來進行傳輸；如當下訊號很微弱則會使用僅僅 18 bps 的 FSK 來進行通訊，以確保能有最大的通訊可靠性。
## 安裝
安裝過程主要分成以下的步驟：
1. 去 VARA 作者個[官網](https://rosmodem.wordpress.com/)下載  VARA HF 。
2. 下載完後解壓縮檔案，點選安裝檔進行安裝；路徑那些除非你有特別需求，不然就建議都預設就好。
3. 去 VarAC 的[官網](https://www.varac-hamradio.com/download)下載軟體，進到此頁面，往下滑輸入您的名字(就填學英文的名子吧XD)，以及 Email (他下載連結是放在 Email 內，如果覺得有隱私風險可以用個臨時信箱收或是聯絡筆者)。
4. 下載完畢後點選安裝檔也是同個步驟，沒什麼透別需求就照預設就好。

以上就是安裝的部分，接下來我們要開始設定軟體的部分。
1. 打開 VARA 然後 點選左上 Setting 的下拉式選單，選擇 Soundcard 進入裡面設定。
2. 進入後選擇你的無線電的音效卡。選擇完點 Close 。
3. 關閉 VARA ，打開 VarAC 此時你會發現 Vara 會自動執行，不要去關掉它。
![picture 0](https://yakumotw.s3.ap-northeast-1.amazonaws.com/8dbad943afd6f041103b6a2b0274a80386bcce09090ffbf886711de94e16d7f1.png)  

4. 點選左上方的下拉式選單，進入設定自身的呼號及座標位置。
![picture 1](https://yakumotw.s3.ap-northeast-1.amazonaws.com/e84bf84d689dc28e92cd17d9342820b05932337ee0f33e2791bdf8d3571e64ce.png)  

5. 在圖中的地方輸入你的呼號以及方格座標。以及可以填寫其他資訊，這要對方可以比較了解你的條件。設定完點選 SAVE AND NEXT 。
![picture 2](https://yakumotw.s3.ap-northeast-1.amazonaws.com/d55cc776cecf03f46e9c531b42fee8f113d9dc57cebc248d4d3a4164a508b35a.png) 
6. 接著點選 RIG Corntrol and VARA Configurations 進行序列埠的設定。
![picture 1](https://yakumotw.s3.ap-northeast-1.amazonaws.com/e84bf84d689dc28e92cd17d9342820b05932337ee0f33e2791bdf8d3571e64ce.png)
7. 這邊是我的序列埠設定，VarAC 支援了大多數市面上的無線電，以我使用 G90 為例，左上 PTT 控制就選擇使用 CAT 然後下拉式選單選擇 G90 。
下方的 CAT 埠口選擇你連接無線電的 COM 號碼，每個人的號碼都會不太一樣，這邊需要自行變通，無法全部都抄我的設定。

選擇完 COM 口號碼後下方的速率也要選擇這個也是取決於您的無線電設定。

接著右邊頻率控制也是一樣選擇 CAT 然後選擇你的無線電。
其他的設定可以等對於此軟體熟悉後再研究。
![picture 3](https://yakumotw.s3.ap-northeast-1.amazonaws.com/b3545799a73436c42aa54bc756fe1b5d13b2d9dcce9f61f3dfd54e5f3c0129f0.png)  
8. 設定完成後可以點擊 PTT ON 、 PTT OFF 與 TEST 看看機器又沒有正常被控制，如果一切正常就點選 SAVS AND EXIT 。
> 如果你有玩 FT8 然後你在這邊設定卡關，我會建議你打開 FT8 軟體的設定頁面來看參數然後 VarAC 這邊參數就跟 FT8 那邊一樣，這樣問題應該就能解決。

## 開始
在完成前述的設定並確定無線電一切正常後，就可以開始使用該軟體。
由於這個模式的使用者遠比 FT8 還要來的少，所以不要急著想要一設定好就想說能通聯到別人。

![picture 0](https://yakumotw.s3.ap-northeast-1.amazonaws.com/8dbad943afd6f041103b6a2b0274a80386bcce09090ffbf886711de94e16d7f1.png) 

本模式主要使用的呼叫頻率是 14105 USB 在確定好之後，現在開始介紹各種呼叫方式。

### 信標呼叫
點選 SEND BEACONS 來發射信標，信標每 15 分鐘會自動發射一次，好讓現上其他使用者發現你的存在。

> 在發射信標的時候，請確定你無線電的 ALC 不要超過 三分之一，因為 ALC 過載會使的波形失真，導致對方可能無法正確解碼。

> 檢查電腦預設音效卡不應該為無線電的音效卡，不然你電腦的聲音會隨著無線電發射時被發射出去造成干擾。


![picture 4](https://yakumotw.s3.ap-northeast-1.amazonaws.com/39d7fefbc19603ec5a9dfceb1264b36b10cb9fc9a51d1fd3259a54b1e888878d.png)  

之後就是像釣魚一樣就耐心的掛機，等待看看別人是否有收到你的信標並且回應你，或是你收到別人的信標你回應它。

發送完信標在軟體的介面會顯示上圖的文字。
![picture 15](https://yakumotw.s3.ap-northeast-1.amazonaws.com/bacb74a4be8ecd45f5ba8bceeb31e2249d63b9916fbd73cf16aa54035d03c793.png)  


左側兩邊分別是
### 回應別人的信標以及 CQ 
當你掛機時，如果軟體發出工合成的語音提醒收到信標(它會把呼號給唸出來)，那麼你可以連擊該呼號兩次，軟體就會開始嘗試開始與對方建立連線。
![picture 6](https://yakumotw.s3.ap-northeast-1.amazonaws.com/313744282bf5b1b1eb6fc2a5f430a2e2d17217c2661909a17a2d9f9be09a30c9.png)  

### 指定呼號呼叫
如果你已經知道某呼號在線上，你無須等待它的信標，可以在這個下拉式選單中直接輸入它的呼號，並且按下 CONNECT 即可進行呼叫。

![picture 5](https://yakumotw.s3.ap-northeast-1.amazonaws.com/20b07db683a51c1fdf59010e8b5cf28a4b2b2d643f6ed1c1bcba37e54b957cad.png)  

## 開始 QSO
這邊假設你收到了某一電台的信標然後連擊兩下開始呼叫對方，你會聽到你的無線電一會發射一會收接收這是很**正常**的現象，因為 VARA 協定是 ARQ 機制的協定，就如同 TCP 一樣，VARA 數據機會確定對方有回應 ACK 的信令才會進一步的交握當成功交握你會聽到軟體發出「叮咚」的聲音，然後此時軟體會開始自動交換雙方的訊號報告。

這時的你請務必馬上按下 QSY 的按鈕，因為 VarAC 設計 14105 是呼叫頻率，所以雙方呼叫到後必須迅速切換到其他頻率去，否則會因為超過一定的時間被強制斷開連線。

QSY的按鈕在軟體介面的左方，下、上以及 # 分別代表 下移 750 Hz 上移 750 Hz 以及自訂頻率。

至於要按哪一個，則要看當時的狀況假設你觀察到上一格，有人在使用那麼就點往下移或是 # 字號指定頻率。

> 使用 # 字號指定頻率時須注意移過去的頻率在對方國家是否能跑數據模式；筆者曾經有嘗試移到某個沒有干擾的頻率，結果被日本台說他們不能在這個頻率上跑數據模式，這點要多加注意。

![picture 7](https://yakumotw.s3.ap-northeast-1.amazonaws.com/32d88d7bf740c6e7fc54b53bd3850fd9337367bac3406356816b74532414fbd2.png)  

此圖為對方收到 QSY 請求後，電腦軟體這邊的回應，看到這邊正常情況下就直接，點選 QSY 即可。
![picture 8](https://yakumotw.s3.ap-northeast-1.amazonaws.com/28c9257c21e414ba4d263b6bd1420575f200205556243fafe26a578a11b0c3dc.png)  

QSY 後就可以如果收到 AWQ 的標籤則代表說對方不在座位前，此時的你除了可以選擇斷線離開外，也可以選擇使用 VMail 的功能留言給對方。
![picture 10](https://yakumotw.s3.ap-northeast-1.amazonaws.com/3dbf11eb24457a59ee810c7ca172328b75016cfa0bfebeed902b8106ac11fb40.png)  

通訊過程中數據機運作的樣子。
![picture 16](https://yakumotw.s3.ap-northeast-1.amazonaws.com/eae5d9132ec8ca274b30754863080b1421b6b60ceb46078d37e69a68b875ae90.png)  

Vmail 是 VarAC 的信件功能，它可以讓你寫信給不在座位上的電台，也有中轉的功能，讓你的信件可以經由第三方電台中轉，到目的地電台；不過這個功能由於亞洲玩得人還太少，所以暫時還用不太到加上這篇文章是以新手入門為導向，故在此先不介紹。

![picture 9](https://yakumotw.s3.ap-northeast-1.amazonaws.com/5e2ae260b848974a165c32cc28578385833810fcb77215b3cf37566d331dedc3.png)  

***
如果對方在線上的話，你應該會收到對方的回應這時候就可以開始與對方聊天；在此我會建議不要像 FT8 一樣跟對方交換完資訊就 73 因為有些玩家是真心希望可以好好慢慢地聊天而不是交換完資訊就閃人，所以在此你可以簡單自我介紹自己，好讓雙方互相了解以利進一步的對話。

> 筆者經驗分享，我在跟日本人通聯的時候，其實會有點緊張因為我有時候不太確定對方是否有無意願跟我繼續聊天，所以這個時候就要會「讀空氣」，在對方回應的言語間猜測對方是否還想跟你聊天。我的辨別方法(當然不是絕對)，當對方開始說謝謝時，就代表可能對方要離開了，這個時候就可以選擇收尾了。

## 結束 QSO 
如果雙方都說了 73 後則可以按下 DISCONNECT 按鈕來中斷連接，此時數據機會自動 QRT 並且 VarAC 會問你說是否要回到 14105 呼叫頻率，那原則上就是回到呼叫頻率讓軟體自動發射信標來等待下一個 QSO。

![picture 11](https://yakumotw.s3.ap-northeast-1.amazonaws.com/9f05dd8f94b348552da0a27a146e5ab678e92a40dc62519ef482ec06e981488b.png)  

## 廣播模式
剛剛以上介紹的模式，為一對一聊天模式，基於 VARA 協定的限制無法多方對話，因此作者透過了 VARA 數據機的 AX.25 模式來發送廣播封包，在這個發射方式下，只要有成功解碼訊號的電台，都能收到廣播的內容。

1. 點選軟體介面右側的 BROADCAST，然後會出現一個視窗。
![picture 13](https://yakumotw.s3.ap-northeast-1.amazonaws.com/d92cbe185a3f965af9359cbca68b4a22d44711a8bee32bcc46183d860e8f9b30.png)  
2. 然後可以介面內寫要廣播的資訊。
![picture 14](https://yakumotw.s3.ap-northeast-1.amazonaws.com/266ae771511cb92c738dc3172669061624e129e11277ab7a573aad1f85a388a2.png)  
3. 寫完要對線上友台要說的話後，點選 BROADCAST AND CLOSE 廣播並關閉視窗。

## VarAC 與 VARA 的缺點與限制
雖然這款專案十分的優良但凡事都會存在缺點的，首先這兩款軟體都是專有軟體，並未像競爭對手一樣開放原始碼；而軟體撰寫的語言關係，讓他們只能原生支援 windows 系統，至於其他作業系統則需要使用一些特殊方法才能執行；而 VARA 由於作者使用古老的 VB6 來開發這導致在現代的電腦作業系統上，雖然可以運作但是一些新的 CPU 指令集會無法使用到，導致效能會差一點點(其實也還好啦XD)。

***
好的以上就是本次 VarAC 的基礎教學，感謝大家的觀看。
[點選這邊](https://yakumo.tw/posts/)可以瀏覽我寫的其他文章。