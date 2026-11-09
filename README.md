# WTC 文獻 Wiki

這是一個碩士論文文獻 wiki，研究領域包含溝通意願（Willingness to Communicate, WTC）、生成式 AI 與語言學習、英語授課（English-Medium Instruction, EMI）和教學鷹架。

本專案依照 Karpathy 的 LLM Wiki 概念建立：文獻只需「編譯一次、持續維護」，不必每次重新查找。使用者負責挑選文獻、提出問題、判斷意義，AI 負責閱讀、摘要、歸檔、建立交叉連結與維護目錄。

網站以 [Quartz 4](https://quartz.jzhao.xyz/) 建置，部署於 GitHub Pages，內容全部公開。

## 資料夾結構

```
thesis-wiki/
├── CLAUDE.md            完整的維護規則
├── templates/           頁面範本（不會發布）
├── references/
│   └── library.bib      Zotero 匯出的書目（唯一的書目來源）
├── raw/                 原始 PDF，檔名＝引用鍵（不上傳 GitHub）
├── private/             私人筆記與文件（不上傳 GitHub）
├── content/             wiki 本體，會發布成網站
│   ├── index.md         首頁：概念地圖與全站目錄
│   ├── log.md           維護日誌（只增不刪）
│   ├── papers/          文獻摘要頁
│   ├── concepts/        概念頁
│   ├── measures/        量表頁
│   ├── methods/         研究方法頁
│   └── syntheses/       綜合比較頁（第一次存入時才建立）
└── quartz/              Quartz 網站程式與樣式
```

## 新增文獻

先在 Zotero 匯出書目到 `references/library.bib`，再把 PDF 放到 `raw/{引用鍵}.pdf`，然後告訴 AI：

```
匯入 {引用鍵}
```

AI 會先回報重點和預計異動的頁面，等你確認後才寫入。

## 健康檢查

告訴 AI：

```
健檢
```

AI 會檢查孤兒頁、失效連結、缺少的頁碼、沒有標記的矛盾等項目，先產出報告，等你同意後才修改。

## 本機預覽

```bash
npx quartz build --serve
```

網址是 `http://localhost:8080`。

## 完整規則

頁面格式、引用方式、隱私規定和工作流程，都寫在 [CLAUDE.md](CLAUDE.md)。
