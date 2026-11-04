---
marp: true
theme: default
paginate: true
header: "AI 實作課程｜資管系 不用寫程式｜2hr 夾敘夾議"
footer: "NCHC AI RAP × Chatbox × Opencode"
style: |
  section { font-family: 'Noto Sans TC', sans-serif; }
  h1 { color: #1a73e8; }
  h2 { color: #202124; border-bottom: 2px solid #1a73e8; padding-bottom: 6px; }
  blockquote { border-left: 4px solid #1a73e8; background: #f8f9fa; padding: 8px 16px; }
  code { background: #f1f3f4; }
---

# AI 實作課程
## 不用寫程式，也能駕馭 AI

資管大學生專班｜**2 小時** 夾敘夾議
講師：陳威宇｜NCHC｜MacBook Pro Demo

> 1hr 講解 + 1hr Demo/實作，邊講邊做

---

## 120 分鐘地圖（參考節奏）

| Unit | 主題 | 形式 | 內容 |
|---|---|---|---|
| 00-05 | 開場 | 講解 | 課程地圖 + 一把 Key 打通全場 |
| Unit 1 | **NotebookLM** | 教材 + 實作 | 看完就忘？一鍵做筆記 |
| Unit 2 | **Chatbox** | 教材 + 實作 | BYOK 突破月費，本地生碼解大檔 |
| Unit 3 | **Opencode** | 教材 + Demo | 用說的做銷售儀表板 |
| 105-120 | 總結 | 講解 | 回顧 + QA |

> 💡 Unit 1 & 2 學生跟做，Unit 3 老師用 MacBook Pro 完整展示

---

## 共同約定：不用寫程式

*   全程不要求寫程式碼，用自然語言下指令
*   成果可視化、可分享
*   重點是 **判斷力** 而非語法

> AI 負責做，你負責想清楚要什麼 + 驗證對不對

---

## 前置準備｜一把 Key 打通全場

**NCHC AI RAP 統一試用 Key（已準備，無需申請）**

*   主機：`https://portal.genai.nchc.org.tw/api/v1`
*   金鑰：`sk-ZjaxxxxxxxxxxxxxxxxOUg`（教材佔位符，課前更新為正式 Key）
*   額度：10,000 點，Chatbox + Opencode 共用
*   規格：相容 OpenAI API

*   NotebookLM：免 Key（用 Google 帳號）
*   Chatbox：**學生實作用**，貼上即連
*   Opencode：**教師 Demo 用**，同一把 Key

> ⚠️ 正式 Key 課堂發放，請勿外流、勿推上 GitHub，已在 `.gitignore` 排除

---

## 為何 Opencode 只有 Demo？

*   Opencode 原生偏 Linux / 終端機環境
*   現場學生非 Linux，`npm` / 埠號 / 權限 容易卡關
*   2 小時內要全員跑起來風險高

**解法：** 老師用 MacBook Pro 完整走一次 `plan → build → 預覽`，學生看懂流程、回家再玩

> 目標：看懂「用嘴巴外包」比現場手忙腳亂重要

---

# Unit 1 - NotebookLM
## 教材 + 實作：看完就忘？用 NotebookLM 做筆記

---

## 教材1：NotebookLM 是什麼？

**一句話：** Google 的 AI 筆記助理，吃 PDF/YouTube 幫你做可查證的筆記

*   直接貼 arXiv PDF + YouTube 連結，不用手抄逐字稿
*   一鍵吐：摘要 / 心智圖 / 語音摘要 / 時間軸 / 測驗
*   每句回答都帶來源章節，可點回原文

> 你負責丟資料，它負責變筆記

---

## 教材2：特色

*   **多來源整合：** PDF + 影片 + 網頁同筆記本對比
*   **引用可追溯：** 不是幻覺，每點都有 `[PDF p.3]` `[00:03:21]`
*   **Studio 自動化：** 摘要/心智圖/語音一鍵生，省手作
*   **專注研讀：** 限定只用你給的資料回答，不亂上網

---

## 教材3：跟別人有何不同？

| 工具 | 定位 | 差異 |
|---|---|---|
| ChatGPT 單問 | 萬能問答 | 無引用，易幻覺，做完就忘 |
| Chatbox | 多模型擂台 + 本地生碼 | 無心智圖/語音，適合分析非研讀 |
| 人工筆記 | 手寫整理 | 耗時，難結構化 |
| **NotebookLM** | 研讀筆記 | **有來源、可複習、可轉測驗** |

---

## 教材4：學生可以怎麼用？（不用寫程式）

*   **論文：** 丟 2601.20245，秒出架構圖 + 中文摘要
*   **考前：** 丟課本 PDF，生成心智圖 + 模擬考題
*   **影片：** 19分鐘訪談貼連結，轉 5分鐘語音複習
*   **專題：** 多份訪談逐字稿同筆記本，找共通點

> 關鍵：先丟再讀，比先讀再記快

---

## 實作｜5 分鐘自學 + 抽點 + Demo

**教材來源：** `2601.20245_How_AI_Impacts_Skill_Formation.pdf` + https://arxiv.org/abs/2601.20245 + 影片 https://www.youtube.com/watch?v=KqCHcPYbqPI

---

### 實作 Step 1：5 分鐘自學 + 抽點

**任務卡：**

```
用任何 AI 幫你讀這篇 PDF，只看 Abstract + Figure 1 + Conclusion
回答：實驗發現什麼？什麼是「交互稅」？
```

*   計時 5 分，抽 2 組各 30 秒，不評對錯只問：AI 省什麼漏什麼
*   效果：現場體感「完全外包」

---

### 實作 Step 2：Demo 影片→筆記一鍵搞定

**痛點：** 19:34《程序员如何不被AI玩废》看完就忘

**解法：**

1.  新建筆記本 `AI工作坊_組別_Vibe陷阱`
2.  貼 YouTube 連結 + 同一份 PDF 雙來源
3.  一鍵生成摘要/心智圖/語音，對比剛剛 AI 摘要多出的「引用」

> 備援：`unit1_notebooklm/sources/KqCHcPYbqPI_transcript.txt`

---

## Unit 1 小結

*   單問 AI：快但淺
*   NotebookLM 筆記：有結構、可查核、可複習
*   帶走：下次看長影片，先丟 NotebookLM 再看

---

# Unit 2 - Chatbox
## 教材 + 實作：BYOK 突破月費，本地生碼解大檔

---

## 教材1：Chatbox 是什麼？

**一句話：** 帶著自己 Key 的多模型桌面客戶端，檔不離機

*   自帶 API Key，自由切換 GPT/Claude/Gemini
*   吃 PDF/Word/圖片/CSV 本地解析，非上傳雲端
*   Prompt 庫一鍵重用，非每次重打

> 你的 AI 百寶箱

---

## 教材2：特色

*   **BYOK：** `sk-Zjax...OUg` 一把打通多家，額度 10,000，免各付月費
*   **多模型擂台：** 同題並排看差異，選最會算的
*   **本地生碼：** 100MB 銷售表不傳雲，叫 AI 寫 `pandas` 本地跑
*   **隱私：** 履歷/財報在地端解析

---

## 教材3：跟別人有何不同？

| 工具 | 定位 | 差異 |
|---|---|---|
| ChatGPT 網頁 | 單家月費限量 | 大檔 >25MB 拒收，無擂台 |
| NotebookLM | 研讀筆記 | 不會生程式、無多模型 |
| **Chatbox** | BYOK 百寶箱 | **多模型 + 本地生碼 + Prompt 庫** |

---

## 教材4：學生可以怎麼用？（不用寫程式）

*   **課業：** 丟 `sales_month.csv` 算 P90/P75/P50 + 畫圖
*   **求職：** 履歷 PDF 丟本地，三模型各修一版
*   **社團：** 活動企劃一句話生預算表/文案
*   **研究：** 多份財報本地對比，無外流風險

> 關鍵：會選模型比會寫 prompt 重要

---

## 實作｜本地生碼分析

**題目：** 老闆丟 `sales_month.csv` 30MB / `sales_quarter.csv` 100MB，5欄各 50~50000，取第3欄(產品C)算 P90/P75/P50 並畫直方圖

*   ChatGPT：太大拒收
*   Chatbox：不傳檔，只生碼本地執行，分級 Demo 30MB → 練習 100MB

---

### 實作 Step 1：BYOK 連上 RAP (8分)

1.  安裝 Chatbox (chatboxai.app)
2.  設定 → 模型供應商 → 新增 `AI RAP` → 類型 `相容 OpenAI API`
3.  主機：`https://portal.genai.nchc.org.tw/api/v1`
4.  金鑰：`sk-ZjaxxxxxxxxxxxxxxxxOUg`
5.  獲取模型 → 選 `gpt-4o-mini` → 測試

> 404=相容沒勾，401=Key 空白

---

### 實作 Step 2：生碼 → 跑碼 → 出圖 (12分)

**Prompt：**

```
角色：資管系數據助教
任務：寫 Python 讀 sales_month.csv 取第三欄算 P90/P75/P50
限制：pandas+matplotlib 輸出 chart.png 標三線
格式：可執行碼 + 逐行中文註解
```

1.  生碼存 `analyze.py`
2.  `python analyze.py` (需 pandas/matplotlib)
3.  驗收：終端機數值 + `chart.png`

**繳交：** `chart.png` + 50字心得

---

# Unit 3 - Opencode
## 教材 + Demo：用說的做銷售儀表板

> 本 Unit 教師 Demo，學生觀看帶回

---

## 教材1：Opencode 是什麼？

**一句話：** 開源 AI Coding Agent，聽懂人話幫你寫完整專案

*   不是聊天框，是會動手的工程師：讀檔、寫檔、跑指令、看報錯、重改
*   跑在你 Mac 終端機，程式碼留在本地，可上 GitHub
*   你說中文，它出 `index.html` + `app.py` + `README`

> 資管新技能：把需求說清楚，比會寫語法重要

---

## 教材2：特色

*   **自然語言即程式：** `幫我用 sales_month.csv 做儀表板` 一句成型
*   **多檔協作：** 一次建 HTML/CSS/JS，不只單段 code
*   **人話迭代：** `把顏色改溫暖 / 加下載按鈕` 持續微調
*   **本地可控：** 接 NCHC RAP 同一把 `sk-Zjax...OUg`，資料不離機
*   **可部署：** 一鍵預覽，帶回可上雲

---

## 教材3：跟別人有何不同？

| 工具 | 定位 | 差異 |
|---|---|---|
| ChatGPT / Chatbox | 問答、生單段 code | 不會幫你建專案、跑測試 |
| NotebookLM | 讀懂、做筆記 | 不會寫程式 |
| Cursor / Windsurf | 編輯器內 AI 助手 | 需會用 IDE |
| **Opencode** | 終端機 Agent | **從零到可跑網站，全自動** |

---

## 教材4：學生可以怎麼用？（不用寫程式）

*   **課業：** 銷售儀表板、問卷分析頁、作品集一頁式
*   **社團：** 報名表 + 抽籤轉盤 + 成果頁
*   **求職：** 履歷網站，帶專案連結
*   **創業：** MVP 原型，一天一版

> 關鍵：先求有，再求好；人負責想，AI 負責做

---

## 流程：想法 → 預覽

```
想法 → 自然語言 → AI 規劃 → AI 實作 → 瀏覽器預覽 → 人話微調
```

*   Plan：先規劃，不動檔
*   Build：直接做

全程老師 MacBook Pro 操作，學生不用開程式碼

---

## Demo 環境

*   講師 MacBook Pro + NCHC RAP Key `sk-Zjax...OUg` (10,000 額度)
*   已備 `starter` 專案，含 `opencode.json` (host: `portal.genai.nchc.org.tw/api/v1`)
*   模型：`gpt-4o` / `claude-3.5` / `deepseek-v3`（需支援 tool calling）
*   數據：`sales_month.csv` 30MB (100萬列)，`sales_quarter.csv` 100MB 課後練

> 若現場網路卡頓，切預錄影片，不中斷

---

## Demo 題目：銷售數據儀表板

銜接 Unit 2 同一份數據：

> 幫我用 sales_month.csv 做銷售儀表板，首頁顯示第3欄 P90/P75/P50 三張數值卡，
> 下方直方圖標三條百分位線，上方 5 按鈕切換 產品A-E，支援下載 chart.png，
> 用分塊載入避免大檔卡頓，風格清新

你會看到：

1.  貼上指令 → Opencode 建 `index.html` + 樣式 + 腳本
2.  瀏覽器即時預覽，按按鈕切換產品
3.  補一句：`幫我加暗色模式 / 手機也要好看`，重刷即生效

---

## 加碼微調

*   `把顏色改溫暖一點`
*   `加匯出篩選後 CSV 按鈕`
*   `修手機版跑版`

每改一次重新整理，看 AI 如何聽懂人話

---

## 回家再玩

*   `starter` 包會後提供，含 `opencode.json` 範本 + 30MB 範例
*   換 RAP Key 為自己的即可，想練再抓 100MB 季報
*   三選一：履歷網站 / 抽籤轉盤 / 銷售儀表板

> 含 Key 檔案勿推 GitHub，已排除

---

## 常見卡關（給回家用）

*   選錯模型 → 不會動，換支援 function calling 的
*   埠號被佔 → 換 3001 / 5174
*   轉圈太久 → 縮小需求，先求有

---

## 評量（100分）

| 項 | 分 | 標準 |
|---|---|---|
| NotebookLM 查核 | 40 | 摘要有引用 + 人工查核 2 項 |
| Chatbox 正確 | 40 | 問答有引用 + 截圖心得 |
| 參與 | 20 | 準時繳交兩份成果 |

> Opencode 不列入評分，看懂流程即可

---

## 回顧

```
NotebookLM 讀懂 → Chatbox 分析 → Opencode 創造
     資料            指標            系統
```

帶走：

*   會查證的提問力
*   會選模型的工具力
*   會說需求的創造力

---

## 延伸

*   跨工具排版：Canva / Gamma 美化
*   數據進階：`Optional_Summary_Data.csv` 畫圖
*   維運：記住 `provider 主機` + `API Key`

智能自由，從這把 Key 開始

---

## 附錄 A：RAP Key 說明

1.  本課程統一使用試用 Key：`sk-ZjaxxxxxxxxxxxxxxxxOUg`（佔位符）
2.  額度 10,000 點，Chatbox + Opencode 共用，無需學生個別申請
3.  課前更新為正式 Key，並透過課堂紙本/ LMS 發放
4.  來源：https://portal.genai.nchc.org.tw/login → 多模型 API

---

## 附錄 B：故障排除

*   PDF 讀不到 → 改 TXT
*   引用沒有 → 縮小到單一來源+章節
*   Studio 太慢 → 交文字大綱
*   Chatbox 404/401 → 檢查相容勾選與空白
*   權限問題 → 先交成果單

---

## 下一步

*   `main_material.md` → Marp 匯出 PPTX/PDF
*   材料分流到 `unit1_notebooklm/` `unit2_chatbox/` `unit3_opencode/`
*   課前一天：教師 Key + MacBook 預演

歡迎提問
