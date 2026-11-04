# Unit 2 - Chatbox

> 夾敘夾議 35-70 分，講解 15 + 實作 20，學生跟做

## 核心設定
- NCHC AI RAP 統一試用 Key：`https://portal.genai.nchc.org.tw/api/v1` + `sk-ZjaxxxxxxxxxxxxxxxxOUg`（佔位符，課前更新）
- 額度 10,000，無需學生申請，課堂發放
- Chatbox 新增供應商：「相容 OpenAI API」→ BYOK 突破 OpenAI 月費
- 一把 Key 同時給 Unit 2 & Unit 3 使用（Unit 3 僅教師 Demo）

## 實作任務
銷售表大檔本地分析（ChatGPT 拒收，Chatbox 生碼解）
- **題目**：取第3欄(產品C)算 P90/P75/P50 並畫直方圖
- **素材**：
  - `sources/sales_month.csv` 30MB (1.05M列) - Demo用，LFS + Release v0.2.0
  - `sources/sales_quarter.csv` 100MB (3.5M列) - 練習用，LFS + Release v0.2.0
- **檢查點1 (8分)**：BYOK 連上 RAP，會對話
- **檢查點2 (12分)**：生碼 → `python analyze.py` → 出 `chart.png` + 數值

## Prompt 範本
```
角色：資管系數據助教
任務：寫 Python 讀 sales_month.csv，取第三欄算 P90/P75/P50
限制：pandas+matplotlib，輸出 chart.png 標三條線
格式：完整可執行碼 + 逐行中文註解
```

## 資料夾用途
- `sources/` - 銷售表 CSV (LFS) + 範例程式碼
- `handout/` - 安裝手冊、BYOK 圖文、故障排除卡
- `config/` - 範例 `chatbox-config.json`（含 Key 檔勿提交，見 .gitignore）

## 教材來源
- 根目錄備份 PDF P10-P15 設定截圖為基礎，已轉譯為 BYOK 版
