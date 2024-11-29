---
title: 前端學習筆記part3
copyright_author: Vincent
copyright_author_href: https://21389081.github.io/index.html
copyright_info: 此文章版權歸 VincentChen 所有，如有轉載，請註明來自原作者
date: 2024-11-26 04:11:42
cover: https://www.oxfordwebstudio.com/user/pages/06.da-li-znate/sta-je-html/sta-je-html.jpg
tags:
  -  Html
  -  程式
  -  筆記
---

# CSS基礎
層疊樣式表(CSS)，用來美化網頁的，做到結構(HTML)與表現(CSS)分離，方便維護。

## CSS的使用
使用CSS可以讓結構(HTML)與表現(CSS)分離，方便維護。

## 基本語法
CSS語法有三個部分組成:選擇器、屬性、屬性值。
```css
selector {
  property: value;
}
```
- selector選擇器通常是需要改變樣式的HTML元素。
- 每條聲明由一個屬性(property)和一個屬性值(value)組成。
- 屬性和屬性值之間用冒號(:)隔開。
- 屬性(property)是希望設置的樣式屬性(style attribute)。每個屬性有一個屬性值(value)。

## CSS的四種引用方式
在html樣式中有四種引用css的方式:行間樣式、內部樣式、外部樣式、導入外部樣式。

- 行間樣式:直接在標籤上書寫樣式。
- 內部樣式:在文件的內部書寫樣式。
- 外部樣式:
  1. 先創建一個CSS文件
  2. 再用link標籤引入這個文件
- 導入外部樣式:
  1. 先創建一個CSS文件
  2. 在style標籤中用import引入這個文件
以上四種CSS引用方式的區別:
- 行間樣式:只作用於當前標籤。
- 內部樣式:只作用於當前文件。
- 外部樣式:可以被多個HTML文件引用。

在實際項目開發中，最多使用外部樣式，外部樣式分為link引入和@import引入方式，兩種方式的區別在:
- link是XHTML標籤，除了加載CSS外，還可以定義RSS等其他事務，@import是CSS語法，只有加載CSS。
- link引用CSS時，在頁面載入時同時加載，@import需要頁面網頁完全載入後加載。
- link是XHTML標籤，無兼容問題，@import是在CSS2.1提出的，低版本瀏覽器並不支持。
- link支持使用javascript控制DOM去改變樣式，而@import不支持。

## CSS選擇器分類
- *:匹配html中所有元素(注意:*的性能比較差，因為他要匹配所有元素，所以在開發時不建議使用)
- 標籤選擇器:用來匹配對應的標籤
- 類別選擇器:用來匹配class命名的標籤
- ID選擇器:用來匹配id命名的標籤
- 派出選擇器:根據上下文來確定選擇的標籤

範例:
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS選擇器</title>
    <style>
        /* 1.* */
        /* *{
            color: red;
        } */

        /* 2.標籤選擇器 */
        span {
            display:block;
            margin-right: 10px;
            border: 1px solid gray;
        }

        /* 3.類別選擇器 */
        .wrapper{
            color: red;
        }

        /* 4.ID選擇器 */
        #content{
            color: blue;
        }

        /* 5.派出選擇器 */
        .box2 li {
            color: green;
        }
    </style>
</head>
<body>
    <p>這是P標籤</p>
    <strong>這是strong標籤</strong>

    <span>這是span標籤</span>
    <div>這是div標籤</div>

    <div class="wrapper">這是div標籤</div>
    <p class="wrapper">這是div標籤</p>

    <p id="content">這是p標籤</p>

    <ui class="box1">
        <li>li001</li>
        <li>li002</li>
        <li>li003</li>
    </ui>
    <ui class="box2">
        <li>li001</li>
        <li>li002</li>
        <li>li003
            <ul>
                <li>subli1</li>
                <li>subli2</li>
            </ul>
        </li>
    </ui>
    
</body>
```
