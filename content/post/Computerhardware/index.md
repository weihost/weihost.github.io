+++
title = '電腦硬體裝修乙級part-1'
date = 2024-12-06T23:24:58+08:00
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



---

# 前言
此篇只有windwos server 2012 r2 基本設定部分，服務架設請參考part-2。<br>[👆檢查筆記👆](https://hackmd.io/@james87575/HyzeYKxVkl)<br> [👆評分表👆](https://hackmd.io/@james87575/SyNPaJfEkx) 

---

## 更改密碼原則

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/password.mp4" >}}

---

## 更改電腦名稱為 ``Server``

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/name.mp4" >}}

---

## 新增使用者
``master``、``user1``、``user2``。

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/usercreate.mp4" >}}

---

## 提高master權限


{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/master.mp4" >}}

---

## 建立使用者群組
將``master``、``user1``、``user2``加入到test群組。
{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/group.mp4" >}}

---



## 設定網路
IP 設定為 ``192.168.140.1XX、172.16.140.100``

遮罩設為 ``255.255.255.0``

閘道設為 ``流空``

DNS 設定為 ``192.168.140.100``

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/network.mp4" >}}

---

## 關閉防火牆🧱

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/firewall.mp4" >}}


---

## 建立資料夾

在C槽目錄下建立``public、user1、user2``資料夾。

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/folder.mp4" >}}

## 設定資料夾權限
>- 權限照下表設定
>
>| 使用者      | master          | user1          | user2          |
>|-------------|-----------------|----------------|----------------|
>| public 資料夾 | 全部權限         | 僅讀取          | 僅讀取          |
>| user1 資料夾 | 不須設定         | 全部權限        | 無法設定        |
>| user2 資料夾 | 不須設定         | 無法設定        | 全部權限        |

---

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/promision.mp4" >}}





# 重新開機
到這邊先重新開機再繼續後面的步驟。

## 結尾
part-1 結束 part-2[👆點我👆](https://blog.jameshost.org/p/%E9%9B%BB%E8%85%A6%E7%A1%AC%E9%AB%94%E8%A3%9D%E4%BF%AE%E4%B9%99%E7%B4%9Apart-2/)



