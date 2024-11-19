---
title: 前端學習筆記day2
copyright_author: Vincent
copyright_author_href: https://21389081.github.io/index.html
copyright_info: 此文章版權歸 VincentChen 所有，如有轉載，請註明來自原作者
date: 2024-11-18 16:14:42
cover: https://www.oxfordwebstudio.com/user/pages/06.da-li-znate/sta-je-html/sta-je-html.jpg
tags:
  -  Html
  -  程式
  -  筆記
---
整理我在自學前端的課程內容、筆記，以及一些實作的內容，不僅方便複習，也順道可以練習markdown語法的使用，期許可以幫助到更多的人。
# HTML標籤屬性
HTML除了基本的佈局標籤以外，還有部分標籤具有強大的交互功能，比如表單標籤，可以實現基本的登陸註冊操作。再者，各種標籤通過設置不同的屬性，也可以實現一些交互效果。

- 標籤由標簽名、標籤屬性和文本內容三部分組成(注意:單標籤沒有文本內容)。
- 標籤屬性是對標籤的一種描述方式。
- 標籤屬性分為:通用、自有和自定義屬性。
- 通用屬性:所有標籤都具有的屬性。
  - 通用屬性有:
    - id:用來給標籤取一個唯一的名稱，在一個網頁中必須是唯一。
    - class:用來給標籤取一個類名。
    - style:用來設置該標籤的行內樣式。
    - title:當游標移動到該標籤上時，所顯示的提示內容。
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>標籤通用屬性</title>
</head>
<body>
    <!-- id:給標籤取一個標示名 -->
    <!-- id名必須是唯一 -->
    <p id="p1">段落1</p>
    <p id="p2">段落2</p>

    <!-- class:給一組標籤取一個類名 -->
    <!-- class標籤不需為唯一 -->
    <div class="test">div</div>
    <p class="test"></p>

    <!-- style:用來設置當前標籤的樣式，也稱為行內樣式 -->
    <p style="color: red; width: 200px; border: 1px solid#00f;">這是一次測試</p>

    <!-- title:給當前標籤一個提示文本 -->
    <p title="您好">How are you?</p>
</body>
</html>
```

## 標籤自定義屬性
通常用來傳值，或用於圖片的延遲載入等方面。
> **格式: data-(自定義內容)**
```html
<img src="圖片名" alt="提示文字" /> - 一般加載圖片
<img data-src="圖片名" alt="提示文字" /> - 配合java實現延遲載入
<p data-id="goodsid">...</p> - 傳值
```

## 表格標籤
### table表格
在Html中 **\<table>** 標籤表示一個表格，每個表格均有若干行(由 **\<tr>** 標籤定義)，每行被分割為若干單元格(由 **\<td>** 標籤定義)，主要用於呈現格式化數據。
- 表格屬性
  - **border**:設置表格邊框，默認單位是像素。
  - **width**:設置表格寬度，默認單位是像素。
  - **align**:設置表格對齊方式(left(默認)/center/right)
  - **cellpadding**:單元格文本與邊框的距離。
  - **cellspacing**:單元格邊框間距。
- 格式
```html
<table>
  <tr>
    <th></th>
    <td></td>
    <td></td>
    ...
  </tr>
  ...
</table>
```
- 基本表格
```html
    <!-- table+tr*2>td{內容$}*3 -->
    <table border="1" width="400" cellspacing="0" cellpadding="10" align="center">
    <tr>
        <!-- th:表頭，主要對下面內容起說明作用，自動加粗，自動置中 -->
        <th>表頭</th> 
        <th>表頭</th> 
        <th>表頭</th> 
    </tr>
    <tr>
        <td>內容1</td>
        <td>內容2</td>
        <td>內容3</td>
    </tr>
    <tr>
        <td>內容1</td>
        <td>內容2</td>
        <td>內容3</td>
    </tr>
</table>
```
### td跨行/跨列屬性
主要用來繪製複雜表格。
- **rowspan**:跨行
- **colspan**:跨列

```html
    <!-- emmet語法 -->
    <!-- table[border=1][width=500][align=center] -->
    <!-- tr*3>td{內容區$$}*3 -->
    <table border="1" width="500" align="center">
    <tr>
        <!-- valign:垂直對齊(top/middle/bottom) -->
        <td rowspan="2" align="center" valign="middle">內容區01</td>
        <td>內容區02</td>
        <td rowspan="3">內容區03</td>
    </tr>
    <tr>
        <td>內容區02</td>
    </tr>
    <tr align="center">
        <td>內容區01</td>
        <td>內容區02</td>
    </tr>
</table>
```
### table完整表格
一個完整table表格，一般包含 **\<thead>** 、 **\<tbody>** 和 **\<tfoot>** 元素結合，用來規定表格的各個部分(表頭、主體、表尾)。

- **\<thead>** 標籤用於組合HTML表格的表頭內容。
- **\<tbody>** 標籤用於組合HTML表格的主體內容。
- **\<tfoot>** 標籤用於組合HTML表格的表尾內容。

```html
<!-- table[border=1 width=600 align=center]>(caption{})+(thead>tr>th*4)+(tbody>tr*3>td*4)+(tfoot>tr>td[colspan=4]) -->
<table border="1" width="600" align="center">
    <caption>學生信息表</caption> <!-- 標題 -->
    <thead> <!-- 表頭 -->
        <tr>
            <th>學號</th>
            <th>姓名</th>
            <th>家庭住址</th>
            <th>備註</th>
        </tr>
    </thead>
    <tbody> <!-- 表體 -->
        <tr>
            <td align="center">001</td> <!-- 內容置中 -->
            <td>tom*</td>
            <td>aaaaaaa</td>
            <td>該生為優等生</td>
        </tr>
        <tr>
            <td align="center">002</td> <!-- 內容置中 -->
            <td>micle</td>
            <td>bbbbbbb</td>
            <td></td>
        </tr>
        <tr>
            <td align="center">003</td> <!-- 內容置中 -->
            <td>mary</td>
            <td>ccccccc</td>
            <td>該生為劣等生</td>
        </tr>
    </tbody>
    <tfoot> <!-- 表尾 -->
        <tr>
            <td colspan="4">附註:*為優等生</td>
        </tr>
    </tfoot>
</table>
```
