+++
title = '如何在Ubuntu上修復「apt-key」棄用警告'
date = 2024-08-20T06:01:50+08:00
draft = false
image = 'title.png'
categories = [
    "linux"
]
tags = [
    "linux",
    "錯誤修復"
]
+++


## 前言
最近，我在更新我的linux系統時遇到了一些問題，再更新系統時會警告我下面這串，雖然這 **不會影響到我執行更新** ，但我看著這行警告心會癢癢，我們應該如何解決 GPG 金鑰的問題？

    W: https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu/dists/jammy/InRelease: Key is stored in legacy trusted.gpg keyring (/etc/apt/trusted.gpg), see the DEPRECATION section in apt-key(8) for details.

如果您在Ubuntu上運行`apt update`時看到`apt-key`已棄用的警告，那麼您來對地方了。

參考文章 : [傳送門](https://askubuntu.com/questions/1398344/apt-key-deprecation-warning-when-updating-system-key-is-stored-in-legacy-trust)

---
## 方法一
> 執行這行指令看有現在有哪些key。
{{< highlight html >}}
sudo apt-key list
{{< /highlight >}}

根據你的警告內容查找相關的key，如下方這串

    pub   rsa4096 2017-02-22 [SCEA]
    9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
    uid  [ unknown] Docker Release (CE deb) <docker@docker.com>
    sub   rsa4096 2017-02-22 [S]

    /etc/apt/trusted.gpg.d/ubuntu-keyring-2012-cdimage.gpg



複製第二行的最後 8 個字，並使用下面的命令將其轉換為檔案。

> 記得`刪除8個字中間的空格`，然後幫你的檔案命名。
<br>
> 在我的示例中，我需要運行：
{{< highlight html >}}
sudo apt-key export 0EBFCD88 | sudo gpg --dearmour -o /etc/apt/trusted.gpg.d/docker.gpg
{{< /highlight >}}

下次運行更新指令時，就**不會再顯示已棄用的錯誤**（如果影響其他存儲庫，就需要對每個存儲庫重複上述步驟）。

---
## 方法二
在 Ubuntu 上修復 apt 棄用錯誤的 **推薦** 方法是上面的方法。但是有一個 **更快速** 的解決方法。

你的情況可能會不同，這有可能不是解決此問題最好的方法，因為根據系統中的舊密鑰，`它可能會危及系統的安全性`。

>執行下方指令
{{< highlight html >}}
cd /etc/apt
sudo cp trusted.gpg trusted.gpg.d
{{< /highlight >}}

在次運行`apt update`就不會再看到那行錯誤。

---