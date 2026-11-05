# AI 資料實作課程｜課程材料包

不用手寫程式，也能完成 AI 資料專案。本課程以 NotebookLM、Chatbox 與 OpenCode，練習研讀來源、分析數字，以及製作互動儀表板。

## 課前準備

- 準備 Google 帳號，登入 [NotebookLM](https://notebooklm.google.com/)。
- 安裝 [Chatbox](https://chatboxai.app/)。
- 準備 Python 與 `pandas`、`matplotlib`，供 Unit 2 在本機執行分析。
- API 網址、試用 Key 與設定步驟，請見 [課程試用 API 設定（Issue #1）](https://github.com/waue0920/ai_course_handson/issues/1)。

## 材料下載

| 材料 | 用途 | 位置 |
|---|---|---|
| How AI Impacts Skill Formation | Unit 1 來源研讀 | [論文 PDF](unit1_notebooklm/sources/2601.20245_How_AI_Impacts_Skill_Formation.pdf) |
| `sales_month.csv` | Unit 2 實作、Unit 3 示範，約 30 MB | `unit2_chatbox/sources/` |
| `sales_quarter.csv` | 課後延伸練習，約 100 MB | `unit2_chatbox/sources/` |

兩份 CSV 透過 Git LFS 管理。使用 Git 下載時，請先安裝 [Git LFS](https://git-lfs.com/)，再執行：

```bash
git clone https://github.com/waue0920/ai_course_handson.git
cd ai_course_handson
git lfs pull
```

已有本機 repo 的同學，在 repo 目錄執行 `git lfs pull` 即可。如果 CSV 開頭是 `version https://git-lfs.github.com/spec/v1`，表示下載到的是指標檔，仍需取得實際資料。

## Unit 1｜NotebookLM：研讀來源

以課程提供的論文與課堂指定來源，練習匯入資料、提問、整理摘要與心智圖，並點回引用查看原文。

重點是確認來源是否支持回答，並用自己的話說明理解與限制。

## Unit 2｜Chatbox：本機資料分析

在 Chatbox 連上 NCHC AI RAP，請模型產生 Python 分析程式，再於自己的電腦執行。

- 資料：`sales_month.csv`，產品 A–E 的模擬銷售金額。
- 任務：分析「產品C」，採線性插值計算 P50、P75、P90。
- 輸出：統計結果與 `chart.png` 直方圖，標示三條百分位參考線。
- 查核：確認欄位、有效與缺失筆數、數值大小關係，以及圖表標籤。



## Unit 3｜OpenCode：製作互動儀表板

教師使用 [OpenCode](https://opencode.ai/) 示範，把 Unit 2 的月報資料做成本機儀表板：

- 切換產品 A–E。
- 顯示 P50、P75、P90 與直方圖。
- 下載目前產品的圖表。
- 核對產品 C 的統計結果是否與 Unit 2 一致。

練習把需求說清楚，觀察 Agent 如何規劃、修改檔案與執行，再以實際操作驗收成果。

