+++
title = '使用pve安裝TP-Link Omada SDN Controller'
date = 2024-08-15T15:42:24+08:00
draft = false
image = 'omada.png'
categories = [
    "linux"
]
tags = [
    "linux",
]
+++




## 前言 ##
Tp-link omada SDN目前只有兩種型號(OC200、OC300)，也可以透過官方提供的docker文件來架設
本篇使用pve建立容器並執行。
> ### 優點
>  - 省錢
>  - 省電
>  - 功能齊全
> ### 缺點
>  - 依照你的機器決定穩不穩定
>  - 較耗電

---

## 開始安裝
選擇你的容器

![](2977505022.png)

## 選擇CT範本

![](1463456439.png)

## 下載ubuntu 20

![](2771580123.png)

## 建立CT

![](1249306897.png)

## 填入主機名稱、用戶密碼

![](3626822659.png)

## 選擇剛剛下載好的範本

![](1403199924.png)

## 設定核心數和記憶體(建議2核2G)

![](3108756623.png)![](2245777137.png)

## 設定網路
把防火牆的選項取消勾選，根據自己路由器配置主機ip位置

![](2701942538.png)

## 確認
確認好機器配置沒有錯

![](222653563.png)

## 開機

![](2869932260.png)
## 登入主機
{{< highlight html >}}
帳號:root
密碼:<剛剛設定的>
{{< /highlight >}}

![](3153885331.png)
## 更新套件庫
{{< highlight html >}}
sudo apt-get update
sudo apt-get upgrade
{{< /highlight >}}
## 安裝必要套件
{{< highlight html >}}
sudo apt-get install mongodb jsvc openjdk-8-jdk gdebi-core -y
{{< /highlight >}}
## 設定java預設執行版本
{{< highlight html >}}
sudo update-alternatives --config java
{{< /highlight >}}
## 下載Tp-link執行腳本
{{< highlight html >}}
wget https://static.tp-link.com/upload/software/2023/202303/20230321/Omada_SDN_Controller_v5.9.31_Linux_x64.deb
{{< /highlight >}}
## 安裝Tp-link執行腳本

{{< highlight html >}}
    gdebi Omada_SDN_Controller_v5.9.31_Linux_x64.deb
{{< /highlight >}}

![](374940178.png)
## 進入設定網頁
**安裝完成後進入**
`http://<你的ip>:8088`
進入後網頁如果顯示不安全選擇進階-->繼續前往網站

![](630431433.png)

## 開始設定
**輸入基本資訊就大功告成拉~**

![](648252104.png)

---
## 懶人包指令

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install mongodb jsvc openjdk-8-jdk gdebi-core -y
    sudo update-alternatives --config java
    wget https://static.tp-link.com/upload/software/2023/202303/20230321/Omada_SDN_Controller_v5.9.31_Linux_x64.deb
    gdebi Omada_SDN_Controller_v5.9.31_Linux_x64.deb
---
<br>

## 參考影片

{{< youtube e86G-B-nT6U >}}

<br>


