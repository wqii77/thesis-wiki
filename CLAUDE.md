# CLAUDE.md — WTC 文獻 Wiki 維護守則

> 這份文件是本專案的「規則檔（schema）」。每次開始工作前，請完整讀完本檔。
> 你（AI）的角色是**守規矩的 wiki 管理員**：依照本檔的結構、格式與流程，持續匯入文獻、更新頁面、保持全站一致。
> 規則有衝突或本檔沒寫到的情況，**先停下來問使用者**，不要自行發明新規則。

---

## 1. 專案目的

- 這是一個**碩士論文文獻 Wiki**，依照 Karpathy 的 LLM Wiki 概念建立：文獻只需「編譯一次、持續維護」，不必每次重新查找。
- 研究領域：溝通意願（Willingness to Communicate, WTC）、生成式 AI 與語言學習、英語授課（EMI）、教學鷹架。
- 使用者的分工：挑選文獻、提出問題、判斷意義、撰寫「我的想法」。
- AI 的分工：閱讀、摘要、歸檔、建立交叉連結、標記矛盾、維護目錄與日誌。
- 網站以 Quartz 4 產生，部署於 GitHub Pages，**內容全部公開**。

---

## 2. 資料夾結構與權限

```
thesis-wiki/
├── CLAUDE.md            本檔：規則（修改前須經使用者同意）
├── templates/           頁面範本（不會發布）
│   ├── paper.md
│   ├── concept.md
│   ├── measure.md
│   └── method.md
├── references/
│   └── library.bib      Zotero 自動匯出的書目（唯一的書目來源）
├── raw/                 原始 PDF，檔名＝引用鍵（不上傳 GitHub）
├── private/             計畫書、私人筆記（不上傳 GitHub）
├── content/             ★ wiki 本體，會發布成網站
│   ├── index.md         首頁：概念地圖＋全站目錄
│   ├── log.md           維護日誌（只增不刪）
│   ├── papers/          文獻摘要頁
│   ├── concepts/        概念頁
│   ├── measures/        量表頁
│   ├── methods/         研究方法頁
│   └── syntheses/       綜合比較頁（由 Query 產生）
└── quartz/styles/custom.scss   視覺樣式
```

| 位置 | AI 可以讀 | AI 可以寫 | 說明 |
|---|---|---|---|
| `raw/` | ✅ | ❌ | 原始資料，**永遠不修改、不搬移、不改名** |
| `references/library.bib` | ✅ | ❌ | 由 Zotero 產生，AI 不得手動編輯 |
| `private/` | ✅ | 只有 `private/notes/` | 內容**絕不可**複製到 `content/` |
| `content/` | ✅ | ✅ | AI 負責撰寫與維護 |
| `templates/`、`CLAUDE.md` | ✅ | 須經使用者同意 | 規則與範本的變更要先提出 |
| `quartz/` 其他檔案、`quartz.config.ts`、`quartz.layout.ts` | ✅ | 須經使用者同意 | 網站核心設定 |

---

## 3. 頁面類型與命名

| 類型 | 位置 | 檔名規則 | 範例 | 範本 |
|---|---|---|---|---|
| 文獻摘要頁 | `content/papers/` | Zotero 引用鍵 | `fathi2024improving.md` | `templates/paper.md` |
| 概念頁 | `content/concepts/` | 英文小寫、連字號 | `willingness-to-communicate.md` | `templates/concept.md` |
| 量表頁 | `content/measures/` | 量表縮寫小寫 | `s-flcas.md` | `templates/measure.md` |
| 方法頁 | `content/methods/` | 英文小寫、連字號 | `multilevel-model.md` | `templates/method.md` |
| 綜合比較頁 | `content/syntheses/` | 英文小寫、連字號 | `ai-chatbot-wtc-effects.md` | 無固定範本 |

- 檔名一律**英文小寫、連字號分隔、不含空格與中文**（檔名會變成網址）。
- 頁面顯示的標題寫在 frontmatter 的 `title`，用中文為主、括號附英文。例：`溝通意願（Willingness to Communicate）`。
- 新建任何頁面都**必須從對應範本複製**，不可省略範本中的區塊；沒有內容的區塊寫「（本文獻未涉及）」。
- `content/syntheses/` 在第一次存入綜合比較頁時才建立；首頁的全站目錄要保留「綜合比較」分類（尚無內容時寫「尚未收錄」）。

### 何時建立新的概念頁、量表頁、方法頁

- **概念頁**：該概念出現在 2 篇以上文獻，**或**屬於下方「核心概念清單」。其他情況只在內文提及，不建新頁。
- **量表頁**：文獻使用了有名稱的已發表量表（例如 S-FLCAS），就建立。
- **方法頁**：統計或研究設計方法出現在 2 篇以上文獻時建立。
- 建立前先查 `content/index.md`，確認沒有同一概念的頁面（含不同譯名或縮寫，參考各頁 `aliases`）。

**核心概念清單**（文獻對該概念有**實質討論**時建頁；只是順帶提到、或用詞只是相近概念時，先不建頁，在文獻頁內文提及即可）：
`willingness-to-communicate`、`state-wtc`、`l2-wtc-pyramid-model`、`wtc-with-ai`、`english-medium-instruction`、`scaffolding`、`flipped-classroom`、`foreign-language-enjoyment`、`foreign-language-classroom-anxiety`、`perceived-communicative-competence`、`personal-innovativeness`、`ai-literacy`、`ai-chatbot-intervention`

---

## 4. 內容撰寫規則

### 4.1 語言

- 使用**繁體中文（台灣用語）**。
- 專有名詞**在每頁第一次出現時**附英文原文，之後可用中文或縮寫。例：外語課堂焦慮（Foreign Language Classroom Anxiety, FLCA）。

### 4.2 正確性（最重要）

1. **書目資料只能來自 `references/library.bib`**：作者、年份、期刊、卷期、頁碼、DOI 一律照抄，**不可**從 PDF 推測或自行補寫。
2. **每一項重點發現、數據、結論都要附頁碼**，格式為 `（p. 8）`，頁碼以期刊排版頁碼為準；只有電子文章編號時，使用 PDF 頁數並寫 `（PDF p. 8）`。
3. 樣本數、效果量、信度、p 值等數字**照原文抄寫**，不可四捨五入或換算。
4. 不確定的內容加註 `（待查證）`。
5. `verified` 欄位**只有文獻摘要頁有**（代表「使用者已對照原文核對過」）。新建時一律為 `false`，只有使用者可以改成 `true`；AI 永遠不得自行改為 `true`。概念頁、量表頁、方法頁沒有這個欄位，它們的正確性來自所引用的文獻頁。
6. 文獻中引用、但不在 `library.bib` 裡的研究：**只寫成純文字**（例：MacIntyre et al., 1998），不建立連結。只有**實際寫進頁面**的研究才加入首頁的「延伸閱讀候選」，不要把整份參考文獻列表搬進來。
7. 在 `library.bib` 裡、但**還沒有文獻頁**的研究：同樣先寫純文字；等該篇匯入後，在它的 Ingest 第 6 步把其他頁面中的純文字改成連結。
8. **二手轉述**：回顧型文獻（範疇回顧、系統性回顧）轉述其他研究的發現時，要寫成「（Kirkpatrick et al., 2024 轉述 Zarrinabadi et al., 2023）」，並在概念頁第 2 區塊註明「轉述」。二手轉述**不可**單獨作為概念頁「支持／不一致」的唯一證據；只有轉述證據時，該區塊寫「目前僅有回顧文獻的轉述，待匯入原始研究」。

### 4.3 引用格式（APA 第 7 版）

- 內文引用：1–2 位作者寫全部姓氏，3 位以上寫「et al.」。例：（Kim & Su, 2024）、（Fathi et al., 2024）。
- 連結到文獻頁時用別名顯示：`[[fathi2024improving|Fathi et al. (2024)]]`。
- 連結到概念頁：`[[willingness-to-communicate|溝通意願]]`。

### 4.4 版權與公開

- 原文引述**每篇最多 3 則、每則最多 2 句**，一律放在 `[!quote]` 視窗並附頁碼；其餘內容**全部用自己的話改寫**。
- 不得複製原文的表格、圖片、整段摘要（abstract）。
- 不得把 PDF 或任何 `raw/` 內的檔案放進 `content/`。

### 4.5 隱私

- `content/` 只寫**通用**的研究關聯，例如「本文獻與溝通意願的狀態測量有關」。
- **禁止**在 `content/` 出現：使用者的研究假設、研究設計細節、受試者或學生資料、倫理審查文件內容、指導教授的意見。
- 文獻與使用者研究的**詳細關聯與評估**（含相關度評分），寫在 `private/notes/{引用鍵}.md`。
- 使用者的研究計畫書放在 `private/proposal/`，撰寫 `private/notes/` 時以它為依據。相關度評分用 1–5 分：5＝直接支持研究問題或研究工具；4＝同一研究情境或變項；3＝提供理論背景；2＝間接相關；1＝僅供參考。評分後附一句理由。

---

## 5. 視窗（callout）規則

網站用 Obsidian 的 callout 語法畫出「視窗」，**每種視窗有固定用途和顏色**。只能使用下表的類型；要新增類型，須先更新本表與 `custom.scss`，並經使用者同意。

| 語法 | 視窗名稱 | 顏色 | 用途與規則 |
|---|---|---|---|
| `> [!card]` | 研究卡／量表卡 | 霧藍 `#b6c3e0` | 文獻頁與量表頁開頭的客觀欄位，依範本順序填寫；**不放任何主觀評分** |
| `> [!finding]` | 重點發現 | 霧黃 `#efdca8` | 主要結果，**每點都要附頁碼** |
| `> [!limit]` | 研究限制 | 霧粉 `#eebfb7` | 作者自述的限制；AI 觀察到的限制要註明「（整理者補充）」 |
| `> [!conflict]` | 文獻矛盾 | 霧橘 `#f2c38f` | 與其他文獻說法衝突時使用，**必須寫明雙方出處**，並在兩邊頁面都加上 |
| `> [!quote]` | 原文引述 | 霧灰 `#dcdedb` | 原文短句＋頁碼，依 4.4 的數量限制 |
| `> [!idea]` | 我的想法 | 霧草綠 `#c8dfb0` | ⚠️ **只有使用者能寫**。AI 新建頁面時只放範本預設的空白提示；遇到已有內容**一字不改**，搬移頁面時原樣保留 |

另有兩個由版面自動產生的視窗（不需在內文撰寫）：

| 視窗名稱 | 顏色 | 對應元件 |
|---|---|---|
| 頁面主視窗 | 薄荷綠 `#a9cfc4` | 頁面標題區 |
| 連到這裡 | 霧紫 `#d9c9e6` | Quartz 反向連結（Backlinks） |

---

## 6. 工作流程

### 6.1 Ingest（匯入一篇文獻）

使用者說「匯入 `{引用鍵}`」時，依序執行，**不可跳步**：

1. **確認來源**：`raw/{引用鍵}.pdf` 存在，且 `references/library.bib` 有同一個引用鍵。缺任何一項就停下來，請使用者先在 Zotero 補上。
2. **完整閱讀** PDF。
3. **先回報、不寫檔**：向使用者列出
   - 研究類型（範疇回顧／系統性回顧／問卷調查／準實驗／實驗／質性／混合方法／理論）
   - 5 個以內的重點（附頁碼）
   - 預計**新建**與**更新**的頁面清單
   - 和現有頁面可能矛盾的地方
4. **等使用者確認**。使用者若要求調整重點，依指示修改後再進行。
5. 依 `templates/paper.md` 建立 `content/papers/{引用鍵}.md`。
6. 更新相關的概念頁：在第 2 區塊把本文獻歸入「支持」或「不一致」，並寫一句說明。需要新建的概念頁、量表頁、方法頁，依第 3 節規則建立。全站搜尋本文獻先前以純文字出現的地方，改成連結（4.2 第 7 點）。
7. 發現矛盾時，在**兩邊頁面**都加上 `[!conflict]`。
8. 更新 `content/index.md`（目錄、概念地圖、延伸閱讀候選）。
9. 在 `content/log.md` 末端新增紀錄（格式見 6.4）。
10. 在 `private/notes/{引用鍵}.md` 寫下與使用者研究的詳細關聯。
11. 執行**自我檢查清單**（第 7 節）。
12. `git commit -m "ingest: {引用鍵}"`，然後**詢問使用者是否 push**。

一次只匯入一篇。使用者要求批次匯入時，仍逐篇完成第 3–4 步的回報與確認。

### 6.2 Query（對 wiki 提問）

1. 先讀 `content/index.md` 找出相關頁面，再讀這些頁面；必要時才回頭讀 `raw/` 原文。
2. 回答時附上出處連結與頁碼。
3. 答案有保存價值時（例如跨文獻比較表），**詢問使用者**是否存成 `content/syntheses/` 的新頁面；同意才建立，並更新 `index.md` 與 `log.md`。

### 6.3 Lint（健康檢查）

使用者說「健檢」時，檢查以下項目，**先產出報告、經同意後才修改**：

- 沒有任何頁面連入的孤兒頁
- 在 2 篇以上文獻出現、卻還沒有概念頁的概念
- 頁面之間互相矛盾、但沒有標記 `[!conflict]` 的說法
- 缺少頁碼的重點發現
- 失效的連結
- 已有文獻頁、但其他頁面仍寫成純文字的引用（應改成連結）
- frontmatter 欄位缺漏
- `verified: false` 的頁面清單（提醒使用者核對）
- `[!idea]` 區塊仍是空白的頁面（提醒使用者補寫）

完成後在 `log.md` 記錄一筆 `lint`。

### 6.4 日誌格式（`content/log.md`）

只能在檔案**末端新增**，不得修改或刪除舊紀錄。每筆格式：

```
## [YYYY-MM-DD] ingest | fathi2024improving
- 新建：papers/fathi2024improving、concepts/ai-chatbot-intervention
- 更新：concepts/willingness-to-communicate、index
- 矛盾：無
```

操作類型只有 `ingest`、`query`、`lint`、`style`、`schema` 五種。

修正已匯入的頁面時，操作類型仍用 `ingest`，但標題後加「（修正）」，例如 `ingest | kirkpatrick2024scoping（修正）`。

---

## 7. 自我檢查清單（每次寫入後執行）

- [ ] 新頁面完整保留範本的所有區塊與順序
- [ ] frontmatter 欄位與範本一致；文獻頁的 `verified` 維持 `false`
- [ ] 書目資料與 `library.bib` 完全一致
- [ ] 每項重點發現都有頁碼
- [ ] 原文引述未超過數量限制
- [ ] 只使用第 5 節列出的視窗類型
- [ ] 沒有改動任何 `[!idea]` 的內容
- [ ] 所有 `[[連結]]` 都指向存在的頁面
- [ ] `content/` 內沒有任何來自 `private/` 的內容
- [ ] `index.md` 與 `log.md` 已更新

---

## 8. 視覺規範

- 樣式只寫在 `quartz/styles/custom.scss`。
- 風格：撞色新粗獷風＋復古視窗風，配色為「霧面薄荷藍」。
- 框線：深炭灰 `#2f2f2f`，2px 實線，右側與下方加厚為 4px；圓角 8px。
- 背景：淡灰綠 `#eef2ef`；內文區一律**白底**、深色文字。
- 字型：內文 Noto Sans TC，標題 Zen Maru Gothic（Google Fonts）。
- 內文字級 16px、行高 1.8；高彩度只用在標題列、標籤與導覽，**不用在內文**。
- 只提供淺色模式。
- 連結文字色：深青 `#2f6f73`。
- 不啟用任何流量統計（analytics 設為關閉），避免把訪客資料送到第三方。
- 頁尾只放本專案的 GitHub repo 連結，不放 Quartz 官方的 GitHub 與 Discord。

---

## 9. Git 與部署

- 每完成一次 ingest、query 存檔、lint 修正，就 commit 一次，訊息以操作類型開頭（`ingest:`、`query:`、`lint:`、`style:`、`schema:`）。
- **push 之前一定要先詢問使用者。**
- 永遠不 commit `raw/`、`private/`、任何 PDF；不得使用 `git add -f`。
- 部署：push 到 `v4` 分支後，由 GitHub Actions 自動建置並發布到 GitHub Pages。
- 本機預覽：`npx quartz build --serve`，網址 `http://localhost:8080`。
