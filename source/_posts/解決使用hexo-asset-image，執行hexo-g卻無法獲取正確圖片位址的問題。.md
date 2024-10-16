---
title: 解決使用hexo-asset-image，執行hexo-g卻無法獲取正確圖片位址的問題。
copyright_author: Vincent
copyright_author_href: https://21389081.github.io/index.html
copyright_info: 此文章版權歸 VincentChen 所有，如有轉載，請註明來自原作者
date: 2024-10-16 04:02:35
tags:
  -  Hexo
  -  程式
  -  Blog
  -  問題解決
cover: https://summer10920.github.io/assets/images/khVSx9I.png
---

相信很多架設hexo部落格的新手們，都曾經碰到這種狀況，在跟著各大教學資源使用hexo-asset-image後，執行hexo g卻無法獲取正確圖片位址，總是會輸出錯誤圖片位址，無法正確顯示圖片，所以我整理了幾種方法，希望能夠提供一點幫助，讓新手們不要重蹈覆轍(笑)。

# 問題概況
執行hexo g後，轉換為以下錯誤的圖片位址:
```html
<p><img src="/.io//example.jpg" alt="img"></p>
```
# 解決方法
修改node_modules/hexo-asset-image/index.js的內容:
```javascript
    // 其餘內容不變
    if(/.*\/index\.html$/.test(link)) {
      // when permalink is end with index.html, for example 2019/02/20/xxtitle/index.html
      // image in xxtitle/ will go to xxtitle/index/
      appendLink = 'index/';
      var endPos = link.lastIndexOf('/');
    }
    else {
      var endPos = link.length-1; // 修改為這樣
    }
    link = link.substring(beginPos, endPos) + '/' + appendLink;
    // 其餘內容不變
```
# node_modules位址
node_modules位址通常在專案資料夾中，由於檔案繁多，可以使用搜尋功能。

# 結語
目前這個問題好像只能靠手動更改index.js的內容來解決，雖然有人更新了github上的內容，但使用npm安裝的版本好像依然是舊版。

# 相關連結
[hexo-asset-image的github頁面](https://github.com/xcodebuild/hexo-asset-image)
[域名是xxx.io的情况下，图片路径会从原本/xxx.jpg变成 /.io/xxx.jpg](https://github.com/xcodebuild/hexo-asset-image/issues/47)
[图片插入问题](https://github.com/hexojs/hexo/issues/4492)

