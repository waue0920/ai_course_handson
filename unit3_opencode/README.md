# Unit 3 - Opencode

> 夾敘夾議 70-105 分，教材 15 + 教師 Demo 20，MacBook Pro 展示，學生觀看

## 教材重點
1. **Opencode 是什麼**：開源 AI Coding Agent，會讀寫檔、跑指令、改 bug，非單純問答
2. **特色**：自然語言即程式、多檔協作、人話迭代、本地可控(接 NCHC RAP)、可部署
3. **與他人區別**：ChatGPT/Chatbox(單段code)、NotebookLM(不寫碼)、Cursor(需IDE) vs Opencode(零到網站全自動)
4. **學生怎麼用**：課業儀表板、社團報名/抽籤、求職履歷站、創業 MVP

## Demo
- **題目**：延續 Unit 2 銷售表 `sales_month.csv` 30MB 做儀表板
- **Prompt**：三數值卡 P90/P75/P50 + 直方圖三線 + 5按鈕切換A-E + 下載 + 分塊載入
- **環境**：MacBook Pro + `sk-Zjax...OUg` (10,000額度) + starter + 30MB，100MB留課後

## 資料夾用途
- `starter/` - 零環境啟動包（含 `opencode.json` 範本）
- `sources/` - 銷售表月報/季報 (LFS + Release v0.2.0)
- `handout/` - 教材講義、Prompt 範本、故障排除卡

## 注意
- 含 Key 的 `opencode.json` / `.env` 請勿提交，已在 .gitignore 排除
