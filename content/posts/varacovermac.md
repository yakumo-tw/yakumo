---
title: "成功讓 VarAC 與 VARA 在最新的 MacOS 上面運作"
date: 2026-02-20T11:09:50+08:00
draft: false
toc: false
images: [https://yakumotw.s3.ap-northeast-1.amazonaws.com/2026/02/55a12869705348df6f7997151eb666e6.png]
tags:
  - 業餘無線電
  - 短波
  - 數據模式
---
## 前文
會生出這篇文章主要是最近換了 Mac Air 2025 的筆電，由於這兩款通訊軟體的作者沒有意願推出原生支援 MacOS 系統的版本，而使用虛擬機跑 Windows 11 又過於笨重，於是筆者採用了老牌開源軟體： wine 的強化版 Crossover 來嘗試執行這兩套軟體。
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2026/02/55a12869705348df6f7997151eb666e6.png)

雖然說是 wine 的強化版但是我在安裝的時候，還是踩了不少坑，尤其是使用 VB6 撰寫的 VARA 基本上安裝是無法直接運作的，因此筆者透過 AI 大神的幫助，補足了 VARA 依賴的檔案後才可以動起來，另外由於每個人的無線電控制方案都不同，因此我無法完整的教學(只能大致解說如何讓這軟體動起來)，其餘部分需要自行變通。
## 安裝方式
先去[這邊](https://www.codeweavers.com/crossover)安裝 crossover，這套軟體是要付費的，但是有提供 14 天的免費試用，讀者可以先不要急著付費，等確定軟體可以動之後購買

![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2026/02/e1c62b7ae0afb4abf5f57d14f1d2ec0d.png)

因為補足依賴的部分實在太複雜了，所以不想動手做的人可以用我的 Crossover 容器檔案，基於一些因素，需要的人請直接 email 我 **bee@yakumo.tw** 索取。

## 已知限制
雖然可以運作但還是有些小小的相容性問題，基本上不影響使用。
### 介面
* 原版介面按鈕會有顏色，但是在上面是單調白色。
* 字體顯示會跟原生版不一樣。
* 數據機軟體 cpu 使用率會無法正確顯示。
![](https://yakumotw.s3.ap-northeast-1.amazonaws.com/2026/02/4b9d30c3b2b39852765078d0b56288bb.png)
