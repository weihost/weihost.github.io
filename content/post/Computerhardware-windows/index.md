+++
title = '電腦硬體裝修乙級-windows設定'
date = 2024-12-07T02:45:32+08:00
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
此篇windwos 10 設定。<br>[👆檢查筆記👆](https://hackmd.io/@james87575/HyzeYKxVkl)<br> [👆評分表👆](https://hackmd.io/@james87575/SyNPaJfEkx) 


## 確認硬碟
容量設定在評分表上會寫。
灌好系統第一件事就是 ``確認C槽和D槽容量``是否正確。

![](https://cloud.jameshost.org/p/video/CCC.png)

---

## 新增使用者
``master``、``user1``、``user2``。

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/newsuer.mp4" >}}

---

## 提高master權限


{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/up.mp4" >}}

---

## 關閉防火牆

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/turnoff.mp4" >}}

---


## 設定網路

IP 設定為 ``172.16.140.1XX`` (工作崗位號碼)

遮罩設為 ``255.255.255.0``

閘道設為 ``172.16.140.100`` (Server IP)

DNS 設定為 ``192.168.140.100``

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/ipset.mp4" >}}

---


## 結尾

Cliant 端設定完成後就可以去設定Server，設定完後記得 [測試](https://blog.jameshost.org/p/電腦硬體裝修乙級part-2/#測試設定內容)👆 。


