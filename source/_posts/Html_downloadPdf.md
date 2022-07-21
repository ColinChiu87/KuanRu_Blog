---
title: 如何利用HTML直接下載pdf
date: 2021-07-28 17:57:28
tags: ["html", "download", "pdf"]
---
# 前言

今天在嘗試利用 html的`<a>`標籤做下載檔案的功能，發現了一件事情，其他檔案能正常下載
~除了pdf~

當你的程式是寫`<a href="test.pdf" />`，當點擊連結時，會使用在當前瀏覽器中打開該文件給予預覽。
這就會不符合我的需求，我希望的是直接給使用者下載，不需要再打開預覽文件。
<!--more-->
# HTML `<a>` download屬性

爬了一下文發現很簡單！只要在a標籤裡再加上一個download就好～
`<a href="yourfile.pdf" download="newFileName">下載檔案</a>`
這邊的newFileName是讓你可以指定使用者下載下來時的檔名，
如果留空，就會默認為伺服器端的名稱，
如下：
`<a href="test.pdf" download>click</a>`

# HTML `<a>` target屬性

既然都說到`<a>`標籤了，那就再加上一點補充～
利用a標籤的時候不外乎就是要開啟一個連結或是下載檔案，那我們在打開連接的方式就有分成幾種：

* 直接於所在的視窗中打開（_self）
* 另開一個視窗（_blank）
* 開啟於父層框架（_parent）
