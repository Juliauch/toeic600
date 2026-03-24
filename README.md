# toeic600

## 📘 專案概述

這個專案是一個 TOEIC 核心單字學習網站，包含：

- `index.html`：最終學習頁面，載入 `const DATA` 物件顯示 Lesson、核心單字、衍生詞家族與例句，並提供語音播放。
- `tool/converter.html`：單字資料產生工具，可上傳兩份 XLSX（核心單字 + 衍生詞）並產生符合 `index.html` 的 `DATA` JSON，
  可直接複製貼上或下載完整可獨立執行 HTML。

## 🗂 檔案說明

- `index.html`
  - 內容為學習系統的 UI 與資料來源（`const DATA`）。
  - 內建樣式與互動功能（切換 Lesson / 發音 / 管理面板）。

- `tool/converter.html`
  - 上傳兩個 Excel / xlsx 檔：
    1. 核心單字總表（欄位：Lesson、Vocabulary、Chinese Definition、Example Sentence）
    2. 衍生詞家族總表（欄位：Lesson、Core Word / Core Word (EN/ZH)、Verb、Noun、Adjective、Adverb、Example Sentence）
  - 解析後生成：
    - JS 物件輸出（直接複製替換 `index.html` 中 `const DATA`）
    - 完整 HTML 下載（`toeic600.html`）

## 🚀 更新流程（推薦）

1. 用 Excel 或 Google Sheets 準備好兩個資料檔，遵從上述欄位名稱。
2. 開啟 `tool/converter.html`，依序上傳「核心單字」與「衍生詞家族」。
3. 點「解析資料」，檢查 `Lesson`、單字、筆數是否正常。
4. 方案 A：點「複製」，貼到 `index.html` 中 `const DATA = {...};` 的位置，儲存後重新整理瀏覽器。
5. 方案 B：下載 `toeic600.html`，直接開啟已包含資料的獨立網站。

## 🛠 注意事項

- `converter.html` 支援常見欄位映射（`Core Word (EN/ZH)` / `Core Word` / `CoreWord`），但建議照原欄位命名保持穩定。
- 若出現解析錯誤，確認欄位名稱無空白、標點正確、lesson 不為空。

## ✅ 快速測試

- 直接開啟 `index.html` 觀察目前硬編在 `DATA` 的 25 Lesson 資料是否正常。
- `tool/converter.html` 有預覽與統計資訊可驗證資料完整性。