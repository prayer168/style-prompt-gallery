# 風格提示詞圖庫 Style Prompt Gallery

一個 NotebookLM / Banana AI 風格的圖像提示詞縮圖庫。點擊卡片即可複製提示詞，拿去生圖工具產生對應風格的圖片。

**🔗 線上版：** https://prayer168.github.io/style-prompt-gallery/

收錄 **64 種圖像風格**，分 10 大類，中英並列卡片，內建後台可手動新增/匯出。

## 特色

- **離線 / 線上皆可用** — 直接雙擊 `index.html` 就能開，也能掛在 GitHub Pages。
- **中英並列** — 英文風格名為主標、中文為副標。
- **一鍵複製提示詞** — 卡片點下去即複製，貼到 NotebookLM / Banana AI 等工具生圖。
- **後台管理** — 右下角浮動按鈕開啟面板，可手動新增圖片＋提示詞（存 localStorage），並一鍵匯出成新的 `styles.js`。
- **缺圖自動佔位** — 縮圖還沒生成時，自動以分類色生成 SVG 佔位圖。
- **零框架、零建置** — 純 HTML + CSS + 原生 JS。

## 檔案結構

| 檔案 | 說明 |
|------|------|
| `index.html` | 單頁應用，渲染卡片、複製、後台面板、匯出 |
| `styles.js` | 唯一的資料檔（`window.STYLES` 64 筆、`window.CATEGORIES` 10 類） |
| `風格提示詞對照表.md` | 縮圖命名對照表 + 全部 64 組提示詞清單 |
| `thumbs/` | 縮圖資料夾，`thumb_01.png` … `thumb_64.png` |

## 縮圖製作流程

1. 打開 [`風格提示詞對照表.md`](風格提示詞對照表.md)，照清單把每組 Prompt 餵給生圖工具。
2. 將生成的圖存成對應檔名（如 `thumb_07.png`），放進 `thumbs/` 覆蓋佔位圖。
3. 不需改任何程式碼，網站會自動以真圖取代佔位圖。

> 建議尺寸：16:9（1280×720 或 640×360）、PNG。

## 新增風格（兩種方式）

**A. 後台面板（推薦）**
右下角 ➕ → 填寫英文名/中文名/分類/提示詞、上傳縮圖 → 新增 → 「匯出 styles.js」下載合併後的檔案，覆蓋原 `styles.js`。

**B. 直接編輯 `styles.js`**
仿照既有物件格式新增一筆：

```js
{ id: 65, cat: "藝術設計", nameEn: "Your Style", nameZh: "你的風格",
  thumb: "thumbs/thumb_65.png",
  prompt: "your image style prompt here" }
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
