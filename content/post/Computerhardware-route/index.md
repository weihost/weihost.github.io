+++
title = '電腦硬體裝修乙級-路由設定'
date = 2024-12-07T03:51:43+08:00
draft = false
image = 'abc.jpg'
categories = [
    "windows",
    "電腦硬體裝修乙級",
]
tags = [
    "school",
    "電腦硬體裝修乙級",
]
+++


## 前言
此篇windwos server 2012 r2 part-2 (路由設定)。<br>[👆檢查筆記👆](https://hackmd.io/@james87575/HyzeYKxVkl)<br> [👆評分表👆](https://hackmd.io/@james87575/SyNPaJfEkx) 




## 設定路由

選擇介於兩個私人網路的安全連線-->不要撥號-->完成✅

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/route.mp4" >}}

---

## 查看路由表

可以對靜態路由右鍵選擇查看。
或是透過command輸入route print查詢。

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/check.mp4" >}}

---



## DHCP設定

新增DHCP領域

- 設定 ``IP範圍(評分表規定)``
- 預設閘道 ``192.168.140.100``(Server)
- DNS設定 ``192.168.140.100``(Server)


{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/DHCP.mp4" >}}



## 測試

把win10的固定ip改成自動獲取看看能不能拿的到ip。