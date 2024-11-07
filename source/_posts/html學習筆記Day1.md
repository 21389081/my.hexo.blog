---
layout: posts
title: 前端學習筆記Day1
date: 2024-11-07 15:37:17
cover: https://www.oxfordwebstudio.com/user/pages/06.da-li-znate/sta-je-html/sta-je-html.jpg
tags:
  -  Html
  -  程式
  -  筆記
---
整理我在自學前端的課程內容、筆記，以及一些實作的內容，不僅方便複習，也順道可以練習markdown語法的使用，期許可以幫助到更多的人。

# HTML概述

- HTML:超文本標記語言，是一種標誌性的語言，非編程語言，不能使用邏輯運算。通過標籤將網路上的文檔格式進行統一，使分散網路資源連結為一個邏輯整體。
  - 超文本，是一種組織信息的方法，通過超連結將多種媒介關聯起來。
  - 標籤:用<>包裹的具有一定含義的內容，比如:
    ```html
    <strong>...</strong>
    ```
  此為一組標籤。

# HTML功能
  - 展示在線的文檔，其中包含標題、文本、表格、列表以及照片等內容
  - 通過超連結檢索在線的信息。
  - 為獲取遠程服務而設計表單，可用於檢索信息、訂購產品等。
  - 在文檔中直接包含電子表格，影片剪輯，聲音剪輯以及其他的一些應用。

# 動態網頁與靜態網頁
  - **靜態網頁** :HTML代碼和內容書寫完畢後，頁面的內容和顯示效果舊基本上不會發生變化了── **除非你修改頁面程式碼**
  - **動態網頁** :頁面程式碼雖然沒有變，但顯示的內容可以 **隨著時間、環境或者數據庫操作的結果而發生改變的。**

**注意** :請勿將動態網頁和頁面內容是否有動畫效果混為一談，比如網頁中的投影片效果，文字滾動效果，如果內容本身沒有變化，那麼也屬於靜態網頁。

# HTML標籤

## HTML基本結構

```html
 <!DOCTYPE html><!--!:表申明的意思。這行程式碼意思為:下面的文檔標籤將以html5規範去解析 -->
<html>
  <!--1.頭部，主要用來完成一個網頁的相關設置。-->
  <head>
    <meta charset="utf-8"><!--漢字編碼--><!--meta:元，主要用來完成對應設置的。-->
    <meta name="keywords" content=""><!--設置網站的搜尋關鍵字-->
    <meta name="description" content=""><!--網站的描述內容-->
    <title>標題</title><!--標題-->
    <!--設定網站圖標-->
    <link rel="shortcut icon" href="圖像連結" type="image/x-icon">
    <link rel="stylesheet" href="style.css"><!--引入外部樣式文件-->
    <script type="text/javascript" src="index.js"></script>
    <style>
      /*書寫樣式的地方*/
    </style>
  </head>
  <!--2.主體部分-->
  <body>
    <p>這是一個段落</p>
  </body>
  <script>
    // 放腳本代碼的地方
  </script>
</html>
```
## 基本標籤

```html
<!--按!+tab或html:5+tab會自動生成文檔結構 -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!--移動端開發設置 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <!--1.div:用來佈局的，沒有具體含義。層 -->
    <!-- 每個div會單獨佔一行 -->
    <div>
        <p></p>
    
        abc
        <div>dbe</div><!--可嵌套 -->
    </div>
    <!-- 2.hx:標題，從1級到6級，1級標題最大，6級最小，會自動加粗，有默認字號 -->
     <h1>前端課程內容</h1>
     <h2>Java開發</h2>
     <h6>大前端開發</h6>

     <!-- 3.p:表示段落。相當於一個enter。 -->
     <p> 魔物獵人的存在，令我無法停止對他的思考。魔物獵人對我來說有著舉足輕重的地位，必須要嚴肅認真的看待。我們不妨可以這樣來想: 伊朗說過一句很有意思的話，大塊的石頭，是忠誠的標記，因為它不會使人跌倒。他會這麼說是有理由的。魔物獵人，發生了會如何，不發生又會如何。</p>
     <p> 魔物獵人的存在，令我無法停止對他的思考。魔物獵人對我來說有著舉足輕重的地位，必須要嚴肅認真的看待。我們不妨可以這樣來想: 伊朗說過一句很有意思的話，大塊的石頭，是忠誠的標記，因為它不會使人跌倒。他會這麼說是有理由的。</p>魔物獵人，發生了會如何，不發生又會如何。

     <!-- 4.br 換行符號，是一個單標籤，推薦使用<br />寫法。-->
     <p>魔物獵人的存在，令我無法停止對他的思考。魔物獵人對我來說有著舉足輕重的地位，必須要嚴肅認真的看待。我們不妨可以這樣來想: 伊朗說過一句很有意思的話，大塊的石頭，是忠誠的標記，因為它不會使人跌倒。他會這麼說是有理由的。<br />魔物獵人，發生了會如何，不發生又會如何。</p>

     <!-- 5.hr:生成一條水平線，主要起裝飾作用。單標籤 ，可進行樣式設定。-->
     <hr />
     <hr width="80%" align="center" color="red" height="2px" />

     <!-- 6.a:實現連結跳轉，路徑可指定為網址，也可指定為檔案。target:_blank/_self/_parent/_top -->
     <a href="網址" title="提示文字">顯示的連結名稱</a> 
     <a href="01 HTML 文檔結構.html" target="_blank">文檔結構</a><!--target="_blank"表示，總是在新分頁打開。 -->
     <a href="01 HTML 文檔結構.html" target="_self">文檔結構</a><!--target="_self"表示，總是在當前分頁打開，為默認設置。 -->

     <!-- 7.img:用來加載外部圖片、圖像。src:用來設定加載的圖片或圖像的路徑。alt:當圖像加載不成功時，將顯示奇內容，否則將不會顯示。title:游標移到圖上時，會顯示的提示文字。-->
     <!-- alt也屬於單標籤 -->
     <img src="連結" title="test" alt="商品" />
     <img src="連結" alt="商品" />

     <!-- 8.span:作用與div一樣，都是用來佈局的，不同的是，div會單獨佔一行，而span不會。span標籤用於行內布局 -->
     <div>div1</div>
     <div>div2</div>
     <span>span1</span>
     <span>span2</span>
    <!-- br*5 -->
     <br><br><br><br><br>

     <!-- 9.ul/ol:列表，前者是無序列表，後者是有序列表，他們的列表內容都用的是li標籤。 -->
     <!-- ul>li{li$}*3 -->
     <ul>
        <li>li1</li>
        <li>li2</li>
        <li>li3</li>
        <li>li3</li>
     </ul>
     <!-- 複製的快捷鍵:shift+alt+方向鍵下 -->
     <ol>
        <li>li1</li>
        <li>li2</li>
        <li>li3</li>
        <li>li3</li>
     </ol>
    <br><br><br><br><br>

    <!-- 註釋，內容不會被瀏覽器解析 -->
    <!-- 快捷鍵為ctrl+/ -->
</body>
</html>
```

## 標籤屬性
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>標籤屬性</title>
</head>
<body>
    <!-- 標籤屬性:
            1.通常由屬性名="屬性值"組成。
            2.起附加信息的作用。
            3.不是所有標籤都有屬性，比如br標籤 -->
    <p title="段落" class="content" id="content">這是一個測試段落</p>
</body>
</html>
```

## 文本格式化標籤
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>文本格式化標籤</title>
</head>
<body>
    <!-- 文本格式化標籤:就是通過標籤萊美化文本外觀。 -->
    <!-- 1.b和strong:都具有加粗作用，且都是行級標籤(不會自動換行)，但strong除了有加粗作用外還有強調作用。註:強調主要用於SEO時，便於提取對應的關鍵字。 -->
    <b>加粗</b>
    <strong>加粗且強調</strong>

    <!-- 2.i和em:使文字傾斜，em具有強調作用。如果只是簡單的傾斜效果，使用i標籤即可，比如添加圖標等。 -->
    <!-- 同樣都為行級標籤。 -->
    <i>文字傾斜</i>
    <em>文字傾斜且強調</em>

    <!-- 3.pre:預格式化文本，保留換行和空格及寬度。一般比較少用。文字的字號會小一號。為塊級標籤(瀏覽器中會獨佔一行)。 -->
    <pre>預格式化文本，保留
               換行和空格
        及寬度</pre>
    
    <!-- 4.small和big:分別讓文字縮小或放大一號，為行級標籤(不會獨佔一行，且不識別寬高)。 -->
    <!-- big元素在html5中淘汰，但沒有刪除。開發中盡量不要使用以淘汰的標籤。 -->
    <!-- 瀏覽器支持的最小字號為12px字，如果要顯示比12px還小的文字效果，需要做處理。 -->
    <p>我是正常大小的文字</p>
    <small>我是小一號的文字</small>
    <big>我是大一號的文字</big>

    <!-- 5.sub(下標)和sup(上標):設置文本為下標和上標，用來調整文本正常顯示的基線，且文本會小一號。 -->
    <p>正常顯示:X1+X2=Y</p>
    <p>下標:X<sub>1</sub>+X<sub>2</sub>=Y</p>
    <p>上標:X<sup>1</sup>+X<sup>2</sup>=Y</p>
</body>
</html>
```
