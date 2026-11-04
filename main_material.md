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

## 120 分鐘地圖

| 時間 | 區塊 | 形式 | 內容 |
|---|---|---|---|
| 00-05 | 開場 | 講解 | 課程地圖 + 一把 Key 打通全場 |
| 05-35 | **NotebookLM** | 講解 5 + 自學 5 + Demo 20 | 一篇 PDF 自學 → 抽點 → 影片筆記法 |
| 35-70 | **Chatbox** | 講解 15 + 實作 20 | BYOK 突破月費 + 本地生碼分析 80~100MB 銷售表 |
| 70-105 | **Opencode** | 講解 10 + **教師 Demo 25** | 用說的做 App (僅 Demo) |
| 105-120 | 總結 | 講解 | 回顧 + QA |

> 💡 NB & Chatbox 學生跟做，Opencode 老師用 MacBook Pro 完整展示

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

# Block 1 - NotebookLM (05-35)
## 看完就忘？用 NotebookLM 做筆記

講解 5 分｜自學 5 分｜Demo 20 分

---

## 05-10 講解｜一篇 PDF 的震撼

**教材：** `2601.20245_How_AI_Impacts_Skill_Formation.pdf` + arXiv 連結

> https://arxiv.org/abs/2601.20245

Anthropic 2026/01 隨機對照實驗：50+ Python 工程師學 Trio，AI 組分數低 17%，耗時 23 vs 24.7 分無差異

一句話：**Vibe Coding 快樂但無知，交互稅與屎山正在偷走你的能力**

發 PDF，宣布：用任何 AI 工具自學，5 分鐘後抽點

---

## 10-15 實作｜5 分鐘自學 + 抽點

**任務卡（印在講義上）：**

```
用 AI 幫你讀這篇 PDF，只看 Abstract + Figure 1 + Conclusion
回答：實驗發現什麼？什麼是「交互稅」？
```

*   工具：Chatbox / ChatGPT / Gemini 皆可
*   計時 5 分鐘，時間到抽 2 組各 30 秒分享
*   不評對錯，只問：AI 幫你省了什麼？漏了什麼？

> 老師效果：製造「完全外包」的現場體感

---

## 15-20 抽點回饋

*   抽點 2 組，投影片停在 Figure 1
*   點出：AI 給的摘要常漏「無效率差異」與「6 種互動模式」
*   鋪墊：影片講得更好，但看完也會忘，怎麼留住？

---

## 20-35 Demo｜影片→筆記，一鍵搞定

**痛點：** 19:34 影片《程序员如何不被AI玩废》講得不錯，看完就忘

**解法：NotebookLM**

1.  新建筆記本 `AI工作坊_組別_Vibe陷阱`
2.  貼 YouTube 連結：`https://www.youtube.com/watch?v=KqCHcPYbqPI`
3.  同筆記本再匯入同一份 PDF（雙來源對比）
4.  一鍵生成：摘要 / 心智圖 / 語音摘要 / 時間軸
5.  對比剛剛學生 AI 摘要，現場標出 NotebookLM 多出的「引用可追溯」

> 備援：`unit1_notebooklm/sources/KqCHcPYbqPI_transcript.txt` 若 YouTube 載入慢，改貼 TXT

---

## Block 1 小結

*   PDF 自學：快但淺
*   NotebookLM 筆記：有結構、可查核、可複習
*   帶走：下次看 20 分鐘影片，先丟 NotebookLM 再看

來源已備：`unit1_notebooklm/sources/` 含 PDF + 逐字稿 TXT

---

# Block 2 - Chatbox (35-70)
## BYOK 突破月費，本地生碼解大檔

講解 15 分｜實作 20 分｜學生跟做

---

## 講解 35-42｜為何不用網頁版就好？

| 網頁版 | Chatbox + BYOK |
|---|---|
| 月費 $20/月仍限量，多家各付各的 | **NCHC RAP 一把 Key `sk-Zjax...OUg` 打通 GPT/Claude/Gemini**，額度 10,000 |
| 大檔 >25MB 拒收 | 本地生碼，100MB 銷售表不離機 |
| Prompt 每次重打 | Prompt 庫 + 角色模板 |

> 對資管人：選對模型 + 省下訂閱 = 競爭力

---

## Chatbox 是什麼？

桌面 AI 客戶端（Win/Mac/Linux）

*   自帶 API Key，自由切換供應商
*   支援 PDF / Word / 圖片 / CSV 本地解析
*   本地知識庫，隱私不外流

> 本課程只用 **NCHC RAP** 一個供應商，降低複雜度

---

## BYOK 核心：帶自己的 Key

**Before：** 學生各付 OpenAI Plus $20，仍限量
**After：** 老師發 RAP 試用 Key，Chatbox 新增供應商

```
類型：相容 OpenAI API
主機：https://portal.genai.nchc.org.tw/api/v1
金鑰：sk-ZjaxxxxxxxxxxxxxxxxOUg
模型：gpt-4o-mini / gpt-4o
```

一鍵取得，多模型並排擂台，額度共用 10,000

---

## 題目：銷售表老闆考題

老闆丟來 `sales_month.csv` 30MB / `sales_quarter.csv` 100MB，5欄各 50~50000

> 請取第3欄 (產品C) 算 P90/P75/P50 並畫直方圖標線

*   ChatGPT：檔案太大拒收
*   Chatbox：不傳檔，只叫 AI 寫程式，本地執行

**分級：** Demo 30MB → 練習 100MB (LFS + Release 雙軌)

---

## Prompt 從爛到好

❌ `幫我分析這個銷售表`

✅

```
角色：資管系數據助教
任務：寫 Python 讀 sales_month.csv，取第三欄(索引2)算 P90/P75/P50
限制：用 pandas + matplotlib，輸出 chart.png，標出三條百分位線
格式：給完整可執行程式碼 + 逐行中文註解
```

> 存成 Prompt 庫，下次換檔名即用

---

## 實作 50-70｜本地生碼分析

**兩檢查點，20 分鐘**

*   ✅ 檢查點1 (8分)：BYOK 連上 RAP，會對話
*   ✅ 檢查點2 (12分)：生碼 → 跑碼 → 出圖

兩人一組，操作員 + 查證員

---

### 檢查點1：BYOK 連上 RAP (8分)

1.  安裝 Chatbox (chatboxai.app)
2.  設定 → 模型供應商 → 新增供應商 → 名稱 `AI RAP` → 類型 `相容 OpenAI API`
3.  主機：`https://portal.genai.nchc.org.tw/api/v1`
4.  金鑰：貼 `sk-ZjaxxxxxxxxxxxxxxxxOUg`（課堂發放版）
5.  獲取模型 → 選 `gpt-4o-mini` → 測試：`回一句話證明你通了`

> 卡住看 `unit2_chatbox/handout/故障排除卡.md`
> 404 = 相容沒勾，401 = Key 前後空白，模型空 = 未按獲取

---

### 檢查點2：生碼 → 跑碼 → 出圖 (12分)

1.  **生碼：** 貼上 prompt (上方範本)，Chatbox 回 `analyze.py`
2.  **跑碼：** 存檔與 CSV 同資料夾，終端機執行
    ```bash
    python analyze.py  # 或雙擊執行
    ```
    需 `pip install pandas matplotlib` (助教已預裝starter)
3.  **驗收：** 終端機印出 `P90/P75/P50` 數值，資料夾出現 `chart.png` 三條虛線

**範例輸出：**
```
P90: 45143
P75: 37485
P50: 24790
圖表已存 chart.png
```

**繳交：** `chart.png` + 50字心得：Chatbox 哪行碼幫你最多？

---

# Block 3 - Opencode (70-105)
## 用說的，就能做 App

講解 10 分｜教師 Demo 25 分｜學生觀看

> 本區塊 **不需學生操作**，專心看流程

---

## 概念翻轉

*   ChatGPT：你問，它答
*   **Opencode：你說，它做**

你說人話，它寫檔、跑測試、修 bug

> 資管新技能：把需求說清楚

---

## 流程：想法 → 預覽

```
想法 → 自然語言 → AI 規劃 → AI 實作 → 瀏覽器預覽 → 人話微調
```

*   Plan：先規劃，不動檔
*   Build：直接做

全程老師操作，學生不用開程式碼

---

## Demo 環境

*   講師 MacBook Pro + NCHC RAP Key
*   已備 `starter` 專案，含 `opencode.json`
*   模型：`gpt-4o` / `claude-3.5` / `deepseek-v3`（需支援 tool calling）

> 若現場網路卡頓，切預錄影片，不中斷

---

## Demo 題目：青禾午餐投票

一句話：

> 幫青禾做一個午餐投票網頁，三家店可投票，即時長條圖，風格清新

你會看到：

1.  貼上指令 → Opencode 建 `index.html` + 樣式 + 腳本
2.  瀏覽器即時預覽
3.  補一句：`幫我加暗色模式` / `手機也要好看`

---

## 加碼微調

*   `把顏色改溫暖一點`
*   `加匯出 CSV 按鈕`
*   `修手機版跑版`

每改一次重新整理，看 AI 如何聽懂人話

---

## 回家再玩

*   starter 包會後提供，含 `opencode.json` 範本
*   換 RAP Key 為自己的即可
*   三選一：履歷網站 / 抽籤轉盤 / 銷售儀表板（`sales.csv`）

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
NotebookLM 讀懂 → Chatbox 問答 → Opencode 創造
     資料            知識            系統
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
