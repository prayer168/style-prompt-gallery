# 風格提示詞圖庫 Style Prompt Gallery

一個 NotebookLM / Banana AI 風格的圖像提示詞縮圖庫。點擊卡片即可複製提示詞，拿去生圖工具產生對應風格的圖片。

**🔗 線上版：** https://prayer168.github.io/style-prompt-gallery/

收錄 **64 種圖像風格**，分 10 大類，採四欄表格（縮圖｜英文提示詞｜中文提示詞｜圖片說明），內建管理模式可逐列上傳縮圖、手動新增/匯出。

## 特色

- **離線 / 線上皆可用** — 直接雙擊 `index.html` 就能開，也能掛在 GitHub Pages。
- **四欄表格** — 縮圖、英文提示詞、中文提示詞、圖片說明並列。
- **中英雙提示詞，一鍵複製** — 英文欄、中文欄各有「複製」按鈕，貼到 NotebookLM / Banana AI 等工具生圖。
- **管理模式逐列上傳縮圖** — 右下角「管理模式」開啟後，每列縮圖欄出現上傳按鈕，選圖即時顯示（暫存 localStorage）。
- **縮圖預設留空** — 尚未上傳時顯示空狀態提示，不使用任何自動生成的佔位圖。
- **匯出永久版** — 「匯出 styles.js」會把自訂風格與已上傳縮圖一併烤進新的 `styles.js`。
- **零框架、零建置** — 純 HTML + CSS + 原生 JS。

## 檔案結構

| 檔案 | 說明 |
|------|------|
| `index.html` | 單頁應用，渲染卡片、複製、後台面板、匯出 |
| `styles.js` | 唯一的資料檔（`window.STYLES` 64 筆、`window.CATEGORIES` 10 類） |
| `風格提示詞對照表.md` | 全部 64 組提示詞清單 |

每筆風格的欄位：`id, cat, nameEn, nameZh, thumb(預設空字串), promptEn, promptZh, desc`。

## 縮圖製作流程

1. 打開 [`風格提示詞對照表.md`](風格提示詞對照表.md)，照清單把每組 Prompt 餵給生圖工具，產生自己的縮圖。
2. 開啟「管理模式」，在對應那列的「縮圖」欄點上傳，選入生成好的圖，前端即時顯示。
3. 想永久保存就按「匯出 styles.js」下載新檔，覆蓋專案中的 `styles.js`，再推上 GitHub Pages。

> 建議尺寸：16:9（1280×720 或 640×360）、PNG。縮圖以 data URI 內嵌於 `styles.js`。

## 新增風格

開啟「管理模式」面板 → 填英文名/中文名/分類/英文提示詞/中文提示詞/圖片說明、上傳縮圖 → 加入風格 → 「匯出 styles.js」下載合併後的檔案，覆蓋原 `styles.js`。

也可直接編輯 `styles.js`，仿照既有物件格式新增一筆：

```js
{ id: 65, cat: "藝術設計", nameEn: "Your Style", nameZh: "你的風格",
  thumb: "", promptEn: "your english prompt here",
  promptZh: "你的中文提示詞", desc: "圖片說明" }
```

## 更新與部署

於 `notebook_style_web/` 目錄下：

```bash
git add -A
git commit -m "update thumbnails"
git push
```

推送後約 1 分鐘，GitHub Pages 會自動重建上線。

## 提示詞與圖片來源聲明

本站所有縮圖皆為自行生成，提示詞皆為自行撰寫／修訂，未抓取網路圖片或複製外部提示詞；網路資料僅作為「有哪些風格類型」的靈感參考。
