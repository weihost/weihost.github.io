+++
title = '電腦硬體裝修乙級part-2'
date = 2024-12-07T01:27:57+08:00
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


# 前言
此篇windwos server 2012 r2 part-2 (服務架設)。<br>[👆檢查筆記👆](https://hackmd.io/@james87575/HyzeYKxVkl)<br> [👆評分表👆](https://hackmd.io/@james87575/SyNPaJfEkx) 
---


## 新增角色規則
**分別啟用下列6個角色**
- DHCP伺服器
- DNS伺服器
- 列印和文件服務
- 網頁伺服器IIS
- 網路原則與存取服務
- 遠端存取



{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/enable.mp4" >}}

---

## 啟用FTP服務、遠端存取的路由


{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/ftp.mp4" >}}

---


## 編輯網站首頁
在 ``C:\public``裡面新增文字文件並打上html程式碼 ``(冒號要是全形文字)``，另存新檔把檔案格式改成htm，編碼要改成 ``UTF-8``，最後記得要把原本新增的 ``純文字檔刪除``。

{{< highlight html >}}
<html>
<body>
<h3><font color="blue">
工作崗位號碼：01</p>
檢定日期：2024/12/7</p>
應檢人姓名：阿威</p>
</font>
</body>
</html>
{{< /highlight >}}
<br>
{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/newindex.mp4" >}}

---


## 設定IIS網站服務

在Default Web Site右鍵``新增虛擬目錄``，名稱為 ``master``路徑為 ``C:\public``，
最後再做 ``自我測試``。
{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/iis.mp4" >}}

---


## 新增FTP站台

- 站台名稱為 ``AAA``。
- 路徑為 ``C:\public``。
- IP設定 ``192.168.140.100``。
- 選擇 ``沒有SSL證書``。
- 驗證選擇 ``基本``，給所有使用者 ``讀取和寫入``權限，最後按下完成。

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/FTPservice.mp4" >}}

---

## 設定FTP權限

停用權限繼承，🛑``先按關閉後在次對AAA站台按右鍵編輯權限``🛑，如果沒有重開後面會很麻煩。

新增權限給下列5位使用者，``Adminisrator``和 ``master``要 ``所有權限``，其他保持默認。
- Administrator ``所有權限``
- Authenticated Users
- IIS_IUSRS
- master        ``所有權限``
- test

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/jichen.mp4" >}}

---

## 設定DNS

網域名稱根據 ``當天考試評分表``決定，新增 ``起始授權``、``名稱伺服器``記得最後記得``要加後綴``。
預設名稱伺服器IP位置指向Server端。

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/DNS.mp4" >}}

---

## 設定AAAA紀錄

新增WWW、FTP前綴名稱域名。 ``(考試當天評分表決定)``

{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/AAAA.mp4" >}}

---



## 確認FTP、DNS是否設定成功

在```Cliant端(win10)```使用剛剛設定好的DNS，訪問FTP，並測試權限。

權限請參考[這裡](https://blog.jameshost.org/p/%E9%9B%BB%E8%85%A6%E7%A1%AC%E9%AB%94%E8%A3%9D%E4%BF%AE%E4%B9%99%E7%B4%9Apart-1/#%E8%A8%AD%E5%AE%9A%E8%B3%87%E6%96%99%E5%A4%BE%E6%AC%8A%E9%99%90)。
{{< video autoplay="false" loop="true" src="https://cloud.jameshost.org/p/video/ftptest.mp4" >}}


## Q&A


> Q: 在檔案總管輸入網域沒有跳出FTP登入視窗。<br><br>A: 可以先ping看看網址有沒有回應，如果沒有回應就檢查網路設定。


> Q: 訪問IIS網頁出現503錯誤，怎麼辦?<br><br>A: Public資料夾權限設定錯誤，把資料夾刪除重新設定一次，如果刪除不了就把資料夾改名，然後再創一個新的。


<!-- ## 結尾

**啟用下列6個角色**
- DHCP伺服器
- DNS伺服器
- 列印和文件服務
- 網頁伺服器IIS
- 網路原則與存取服務
- 遠端存取

**設定IIS**
**設定FTP**
**設定DNS**

- [ ] 5.設定網路 -->