---
title: Markdown 語法
date: 2024-08-23 02:55:00
updated: 2024-08-23 02:55:00
cover: https://img.technews.tw/wp-content/uploads/2020/03/20114613/640px-Markdown-mark.jpg
tags: 
  -  Markdown
  -  Blog
copyright_author: Vincent
copyright_author_href: https://21389081.github.io/index.html
copyright_info: 此文章版權歸 VincentChen 所有，如有轉載，請註明來自原作者
---
# **markdown語法**
---

## 標題
```markdown
# h1   //一級標題
## h2   //二級標題
### h3  //三級標題
...以次類推
``` 
# 一級標題
## 二級標題
### 三級標題

# 分隔線
```markdown
--- 或 ***
```
# 粗體和斜體
```markdown
**粗體文字**
*斜體文字*
***粗斜體文字***
```
**粗體文字**
*斜體文字*
***粗斜體文字***

# 列表
```markdown
- 無序列表項目1
- 無序列表項目2
  - 子項目A
  - 子項目B

1. 有序列表項目1
2. 有序列表項目2
   1. 子項目A
   2. 子項目B
```
- 無序列表項目1
- 無序列表項目2
  - 子項目A
  - 子項目B

1. 有序列表項目1
2. 有序列表項目2
   1. 子項目A
   2. 子項目B

# 連結
```markdown
[連結文字](https://www.example.com)
```
[連結文字](https://www.example.com)

## 圖片
```markdown
![圖片替代文字](https://img.technews.tw/wp-content/uploads/2020/03/20114613/640px-Markdown-mark.jpg)
```
![圖片替代文字](https://img.technews.tw/wp-content/uploads/2020/03/20114613/640px-Markdown-mark.jpg)

# 引用
```markdown
> 對可以掌控的事樂觀，對不可掌控之事謹慎。
> 悲觀者正確，樂觀者前行。
```
> 對可以掌控的事樂觀，對不可掌控之事謹慎。
> 悲觀者正確，樂觀者前行。

# 程式碼
```markdown
```(指定程式語言)程式碼```
```
```python
print("Hello, World!")
```


# 表格
```markdown
| 欄位1 | 欄位2 | 欄位3 |
|-------|-------|-------|
| 內容1 | 內容2 | 內容3 |
| 內容4 | 內容5 | 內容6 |
```
| 欄位1 | 欄位2 | 欄位3 |
|-------|-------|-------|
| 內容1 | 內容2 | 內容3 |
| 內容4 | 內容5 | 內容6 |

# 任務列表
```markdown
- [x] 已完成
- [ ] 未完成
```
- [x] 已完成
- [ ] 未完成

# 刪除線
```markdown
~~刪除的文字~~
```
~~刪除的文字~~
