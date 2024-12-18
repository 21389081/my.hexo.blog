---
title: 前端學習筆記part2
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
- 通用屬性:所有標籤都具有的屬性(除 \<br/> 標籤外)。
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
在Html中 **\<table>** 標籤表示一個表格，每個表格均有若干行(由 **\<tr>** 標籤定義)，每行被分割為若干單元格(由 **\<td>** 標籤定義)，主要用於呈現格式化數據，撰寫時必須為先行後列，列在行包裹之下。
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
一個完整table表格，一般包含 **\<caption>** 、 **\<thead>** 、 **\<tbody>** 和 **\<tfoot>** 元素結合，用來規定表格的各個部分(表頭、主體、表尾)。

- **\<caption>:** 表格標題(非必要)。
- **\<thead>:** 標籤用於組合HTML表格的表頭內容。
- **\<tbody>:** 標籤用於組合HTML表格的主體內容。
- **\<tfoot>:** 標籤用於組合HTML表格的表尾內容。

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
## form表單標籤
是所有標籤中最核心的標籤之一，它是用來實現前後端交互的一個重要標籤。

**常用屬性**
- **name** :表單名稱
- **method** :前端提交數據到後端的方法(主要有:get/post，默認的是get。)
- **action** :表單數據提交的地方(通常是一個後台文件名(.jsp/.php/.aspx/.py等)，或網址)，如果是#，表示提交到當前文件下。

### 表單元素
#### input
> input類主要用於輸入、選擇或發出指令。
**type: text,password,radio,checkbox,file,button,image,submit,reset**

- text
單行文本輸入框(enter換行不適用)，type="text"可以不寫，默認值。
  - 屬性:
    - **placeholder** :提示
    - **name** :命名
    - **minlength和maxlength** :最少/多輸入的字符個數
    - **readonly** :只讀
    - **disabled** :禁用
    - **value** :預設值
    - **pattern** :正則表達式
- password:密碼輸入框，屬性和text類一樣。
- radio:單選按鈕，通常是兩項以上。
  - 屬性:
    - **name** :命名(必須要有)
    - **value** :預設值
    - **checked** :選中
    - **disabled** :禁用
    - **readonly** :只讀
- checkbox:複選框，可以用來選擇0項、1項或多項，屬性同上。
- file:文件上傳按鈕，屬性同上。
- button:普通按鈕，通常用來調用腳本程式碼。
  - 屬性:
    - **value** :按鈕的標題
    - **disabled** :禁用
- image:圖片按鈕，用法與button一樣，有一個特殊屬性:src(用來加載提示圖片，用它替換了value屬性)。
  > 它有提交功能，和submit功能一樣。
- submit:提交按鈕，用來將表單數據提交到後端，常用屬性同button。
- reset:重置按鈕，將表單所有組件輸入的內容全部清空，還原為初始狀態，常用屬性同button。

#### textarea
文本域(也可以叫多行文本框)，主要用於輸入大批量的文本內容。
  - 屬性:
    - **name** :命名
    - **placeholder** :提示
    - **rows** :行數
    - **cols** :列數
    - **readonly** :只讀
    - **disabled** :禁用
    - **required** :必填
    - **minlength和maxlength** :最少/多輸入的字符個數
    - **value** :可獲取其文本內容

#### select
下拉選單，默認用於選擇單一項目，用option標籤呈現每個選項。
  - 屬性:
    - **name** :命名
    - **multiple** :表示可以多選，這時的下拉列表框變成了列表框。
    - **required** :必填
    - **size** :顯示的行數
**範例:**
```html
    <!-- label中for的內容要和select的id相同，才能產生關聯。 -->
    <!-- form是塊級元素，select、input是行級元素 -->
    <form action="">
        <label for="sex">性別:</label>
        <select name="" id="sex">
            <option value="male">男</option>
            <option value="female">女</option>
        </select>
        <br/>

        <label for="course" >選課:</label>
        <!-- multiple是多選 -->
        <!-- size是顯示的選項數量 -->
        <select name="" id="course" multiple="multiple" size="2">
            <option value="國文">國文</option>
            <option value="英文">英文</option>
            <option value="數學">數學</option>
            <option value="自然">自然</option>
        </select>
    </form>
```

#### button
普通按鈕，具有提交功能，可以單獨使用，不寫在form元素中。若寫在form中，則有提交功能，功能與input中的submit一樣。
```html
    <!-- 這裡的button主要用來調用js程式碼 -->
    <button id="btnOk">確認</button>
    <form action="test.aspx">
        <input type="text" name="info">
        <!-- 這裡的button的功能與input中的submit一樣 -->
        <button>提交</button>
    </form>
```
### iframe框架標籤
框架集，是用來將多個網頁文件組合成一個文件。
- 常用屬性:
  - **name** :框架名
  - **src** :引入的外部html文件
  - **scrolling** :滾動條(yes/no/auto)
  - **width** :寬度(%/px)
  - **height** :高度(%/px)
  - **frameborder** :是否有邊框(1/0)
  - **marginwidth** :框架離左右的距離(%/px)
  - **marginheight** :框架離頂部和底端的距離(%/px)

**範例:**
```html
<body>
    <!-- banner -->
    <iframe src="iframe/banner.html" frameborder="0" scrolling="no" width="100%"></iframe>
    <!-- nav(導覽列) -->
    <iframe src="iframe/nav.html" frameborder="0" scrolling="auto" width="20%" height="300px"></iframe>
    <!-- content(核心內容區) -->
    <iframe src="iframe/content1.html" name="main" frameborder="0" scrolling="no" width="70%" height="300px"></iframe>
</body>
```

**注意:**
在實際開發中，盡量減少使用iframe，因為他破壞了前進和後退功能，且不利於SEO。
