---
title: Hexo-SEO Google Search Console
date: 2022-07-20 11:15:28
tags: [Hexo, SEO, Google Search Console]
---
# 前言
發布了自己的部落格後，是不是發現在 Google 搜尋引擎找不著自己的網站呀！
難道是自己已經邊緣到被全世界排擠了嗎...QAQ
雖然這也有可能是一個原因啦...(XD，不鬧了

# Google Search Console
它的前身叫做 Google Webmaster Tool，而它的作用就是專門管理你的網站在搜尋引擎的 SEO 表現，
如果你想知道你的網站熱門的關鍵字、曝光或點擊數量，那麼你一定要試試。

要讓搜尋引擎能找到自己的網站，我們要先進入 [Google Search Console](https://search.google.com/search-console/about) 註冊服務並進行一些設定。

# 實作
## 驗證網站
一開始必須先設定驗證你的網站（如下圖）。
{% asset_img gsc.jpg %}
有購買網域的話，就可以使用左邊的驗證；如果像我一樣是利用 Git Page 發布的，就選擇右邊“網址前置字元”，
輸入完你的網址後會要去驗證，我這邊使用的是 HTML 檔案，當然你可以選擇你喜歡的方式驗證。
1. 點擊按鈕**下載**檔案。
{% asset_img gsc1.jpg %}
2. 直接將檔案放進來你會發現驗證是失敗的，所以我們要先**編輯**一下這個檔案！
```js
---
layout: false
---

google-site-verification: googleb6bf13d6a5baaaaaaaaa.html
```
3. 將**檔案放到 hexo/ source 底下**。
{% asset_img gsc2.png %}

4. 不免俗的還是要提醒一下，請記得將 Hexo **部署**到 GitHub Pages。
5. 最後按下驗證的按鈕即可。

大概等待個兩三天 GSC 就會分析出你的網站有哪些關鍵字熱門、需要優化的地方，基本上你就照著他提供方向去做調整，網站的 SEO 就會大大到提升了。

## Sitemap
說到 Google Search Conosle 那就順便提一下 Sitemap 吧~
以往建立一個新的網站時，如果沒有強而有力的網站互聯(ㄏㄨㄟˋ)的話，就很難被爬蟲給爬到，所以這時就要給自己的 Hexo 安裝套件是專門幫忙生成 sitemap.xml ，而這檔案是提交給搜尋引擎爬蟲使用。
```
npm install hexo-generator-sitemap --save
```
在終端機輸入完指令後就可以部署上去。
接著來到 Google Search Console 上的 “Sitemap” 頁面，並在新增欄位輸入 sitemap.xml 提交就完成囉。
{% asset_img gsc3.png %}

都設定好了以後， Google 爬蟲只要定期去看 sitemap 檔案是否更新，就會去爬你的網站並做更新囉！
一般來說部落格要被搜尋引擎收錄大概會需要 7~14 天不等，當然也有更快的，就看運氣了😂

這篇就到這，我們下次見👋🏻
