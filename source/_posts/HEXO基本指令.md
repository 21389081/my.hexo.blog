---
title: HEXO基本指令與檔案結構總攬
copyright_author: Vincent
copyright_author_href: https://21389081.github.io/index.html
copyright_info: 此文章版權歸 VincentChen 所有，如有轉載，請註明來自原作者
date: 2024-10-17 00:53:51
tags:
  -  Hexo
  -  程式
  -  Blog
cover: https://summer10920.github.io/assets/images/khVSx9I.png
---

Hexo是一款快速、簡單且功能豐富的框架，通常用於架設部落格或個人網站，此篇文章涵蓋了絕大部分使用hexo架設個人網站時，常用的指令、功能，工作流程，以及各個資料夾所代表的含義。

# 安裝 Hexo

請先確保已經安裝了 Node.js 和 Git。接著，你可以使用以下指令安裝 Hexo：

```bash
npm install -g hexo-cli
```

# 建立新專案

使用 Hexo 建立一個新的專案目錄：

```bash
hexo init my-blog
```

這個指令會在 `my-blog` 資料夾內建立一個新的 Hexo 專案。接著進入該目錄並安裝所需的依賴：

```bash
cd my-blog
npm install
```

# 本地伺服器預覽

要在本地啟動伺服器以預覽你的網站，可使用以下指令：

```bash
hexo server
```

這在預設情況下會於 `http://localhost:4000` 啟動一個伺服器，並讓你可以在瀏覽器中查看你的網站。

# 建立新文章

要新增一篇文章，可以使用以下指令：

```bash
hexo new post "文章標題"
```

這會在 `source/_posts` 資料夾中建立一個新的 Markdown 檔案，讓你可以編輯並撰寫內容。

# 部署網站

可以將其部署到 GitHub Pages 或其他服務器。確保你已經配置好 `_config.yml` 中的相關設定，然後使用以下指令：

```bash
hexo deploy
```

# 清理快取&hexo g產生的檔案

當你對內容做了改動，需要重新執行hexo g指令前，可以使用以下指令，刪除相關內容以避免錯誤：

```bash
hexo clean
```

這個指令會移除 Hexo 生成的暫存檔案，以確保之後的編譯過程不會受到先前快取的影響。

# Hexo 各個資料夾介紹

在 Hexo 專案中，主要的資料夾結構如下：

- **source**：存放網站的原始內容。`_posts` 資料夾是文章的存放位置，你的文章 Markdown 檔案都會在這裡。
- **themes**：存放網站的佈景主題。你可以在這裡自訂或更換主題，以改變網站的外觀。
- **scaffolds**：存放模板，用於建立新文章時的預設內容。你可以修改這些內容，以設定新文章、頁面或草稿的初始內容。
- **public**：存放 Hexo 生成的靜態檔案，這些檔案會被部署到伺服器上。
- **_config.yml**：Hexo 的全域配置檔案，用於設定網站的各種參數，包括標題、部署設定等。

這些資料夾幫助你有效地管理網站的各個部分，讓你可以根據需求自訂內容、主題與結構。

# 常見 Hexo 工作流程

1. **建立新文章：** 使用 `hexo new post "文章標題"`指令。
2. **撰寫與編輯內容：** 在 `source/_posts` 中找到新文章並開始撰寫。
3. **預覽：** 使用 `hexo server` 在本地查看網站。
4. **清理舊的靜態檔案：** 使用 `hexo clean` 刪除快取&暫存檔案。
5. **生成靜態檔案：** 使用 `hexo generate` 生成網站靜態檔案。
6. **部署網站：** 使用 `hexo deploy` 將網站部署到指定伺服器。

# 結論

以上是我在使用hexo架設網站時，有用到的指令、功能，若你想了解更多指令或自訂功能，可以參考 [Hexo 官方文檔](https://hexo.io/docs/)。

希望這篇文章對你有幫助，快開始打造屬於你自己的網站吧！
