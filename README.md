# AI 資料實作課程｜課程材料包

不用手寫程式，也能完成 AI 資料專案。本課程以 NotebookLM、Chatbox 與 OpenCode，練習研讀來源、分析數字，以及製作互動儀表板。

## 課前準備

- 準備 Google 帳號，登入 [NotebookLM](https://notebooklm.google.com/)。
- 安裝 [Chatbox](https://chatboxai.app/)。
- 準備 Python 與 `pandas`、`matplotlib`，供 Unit 2 在本機執行分析。
- API 網址、試用 Key 與設定步驟，請見 [課程試用 API 設定（Issue #1）](https://github.com/waue0920/ai_course_handson/issues/1)。

## 材料下載

**學生請直接點下表下載，不需要安裝 Git 或 Git LFS。**

| 材料 | 用途 | 下載 |
|---|---|---|
| How AI Impacts Skill Formation | Unit 1 來源研讀 | [論文 PDF](unit1_notebooklm/sources/2601.20245_How_AI_Impacts_Skill_Formation.pdf) |
| `sales_20.csv` | 月報前 20 筆，先測試欄位與分析程式 | [下載小樣本 CSV](https://raw.githubusercontent.com/waue0920/ai_course_handson/main/unit2_chatbox/sources/sales_20.csv) |
| `sales_month.csv` | Unit 2 實作、Unit 3 示範，約 30 MB | [下載月報 CSV](https://github.com/waue0920/ai_course_handson/releases/download/v0.2.0/sales_month.csv) |
| `sales_quarter.csv` | 課後延伸練習，約 100 MB | [下載季報 CSV](https://github.com/waue0920/ai_course_handson/releases/download/v0.2.0/sales_quarter.csv) |

下載後，將 CSV 放入本次實作資料夾，與產生的 `analyze.py` 放在一起，並確認程式使用正確的檔名與路徑。

也可前往 [v0.2.0 Release](https://github.com/waue0920/ai_course_handson/releases/tag/v0.2.0)，在 **Assets** 點選上述兩個 CSV；請選 CSV 附件，無須下載 Source code 壓縮檔。

### 使用 Git 下載（選用）

`sales_20.csv` 是一般文字檔，不需要 Git LFS；repo 內的完整月報與季報透過 Git LFS 管理。熟悉 Git 的同學可先安裝 [Git LFS](https://git-lfs.com/)，再執行：

```bash
git clone https://github.com/waue0920/ai_course_handson.git
cd ai_course_handson
git lfs pull
```

已有本機 repo 的同學，在 repo 目錄執行 `git lfs pull` 即可。如果 CSV 開頭是 `version https://git-lfs.github.com/spec/v1`，表示下載到的是指標檔；可直接改用上表的 Release 連結取得完整資料。

## Unit 1｜NotebookLM：研讀來源

以課程提供的論文與課堂指定來源，練習匯入資料、提問、整理摘要與心智圖，並點回引用查看原文。

重點是確認來源是否支持回答，並用自己的話說明理解與限制。

## Unit 2｜Chatbox：本機資料分析

在 Chatbox 連上 NCHC AI RAP，請模型產生 Python 分析程式，再於自己的電腦執行。

取得模型清單後，可選擇下列四個課程模型（名稱請完整比對）：

- `Muse-Spark-Open-816B-A42B`
- `NVIDIA-Nemotron-3-Ultra-550B-A55B`
- `gemma-4-31B-it`
- `gpt-oss-120b`

### 實作任務 第一階段：下載 20 筆資料，算出正確數值

分三階段完成：小樣本核對數值 → 完整月報畫圖 → 季報跨產品深入分析。所有程式都在本機執行。


```bash

```

將以下第一個 prompt 貼到 Chatbox：

```text
請寫一個可在本機執行的 Python 程式 analyze.py，使用 pandas
讀取目前資料夾的 sales_20.csv（UTF-8，可能有 BOM）。
https://raw.githubusercontent.com/waue0920/ai_course_handson/main/unit2_chatbox/sources/sales_20.csv
以欄位名稱「產品C」選取資料，每格代表一筆模擬銷售金額（元）。

請列出總筆數、缺失筆數、有效筆數、最小值、最大值，
並以線性插值計算 P50、P75、P90，顯示至小數點後兩位。
非數值資料請明確報錯，不要自行刪除；缺失值不參與統計。
這一步先不要畫圖。提供完整程式、套件安裝與執行指令，
並解釋百分位的計算方式。未讀到實際檔案前，不要編造結果。

```

 **對答案**

| 產品 C 檢查項目 | `sales_20.csv` 預期值 |
|---|---:|
| 總筆數／有效筆數 | 20／20 |
| 缺失筆數 | 0 |
| 最小值／最大值 | 1375／49065 |
| P50 | 32550.00 |
| P75 | 43345.00 |
| P90 | 46345.60 |

以上答案僅適用於這份月報前 20 筆資料。

### 實作任務 第二階段：產生畫圖程式，再分析完整月報

先在同一個 Chatbox 對話貼上第二個 prompt：

```text
請延續剛才已核對正確的分析程式，加入 matplotlib 畫圖功能。
讓我能透過命令列指定 CSV 檔案，例如：
python analyze.py sales_month.csv

保留產品C的統計結果與原本的缺失值、非數值處理規則。
畫出 30 個區間的直方圖，標示 P50、P75、P90 三條垂直線，
圖例顯示對應數值；橫軸為金額（元），縱軸為觀測筆數，
標題包含產品與資料檔名，輸出 chart.png。
中文缺字時可使用英文標籤。只用本機 pandas、matplotlib，
不呼叫外部服務。提供完整修改後程式與執行指令。

curl -fL https://github.com/waue0920/ai_course_handson/releases/download/v0.2.0/sales_month.csv -o sales_month.csv

python analyze.py sales_month.csv

```

 **對答案**

每次執行會覆寫 `chart.png`，需要保留兩張圖時請先另存。完整月報的百分位結果應由實際計算取得，不沿用小樣本答案。

繳交：月報統計結果、直方圖、兩項查核紀錄，以及一句對分布的解讀。

### 延伸練習 第三階段：

**情境：主管想知道「哪個產品的典型交易較高？哪個產品的高額交易落差較大？」請用季報比較產品 A–E，提出有數據依據的觀察。**

```text
curl -fL https://github.com/waue0920/ai_course_handson/releases/download/v0.2.0/sales_quarter.csv -o sales_quarter.csv


請自行設計 prompt，讓 Chatbox 協助產生本機分析程式，完成下列工作：

1. 各產品列出總筆數、有效與缺失筆數、平均數、P25、P50、P75、P90、P99；百分位統一使用線性插值。
2. 計算 IQR（P75 − P25）與 P90 − P50，分別比較中間一半資料的離散程度、典型交易到高額門檻的差距；指出 P50 最高及 P90 − P50 最大的產品。
3. 以各產品自己的 P90 為門檻，計算「嚴格大於 P90」的筆數比例，以及這些觀測金額占該產品總金額的比例。說明為什麼門檻、筆數比例與金額占比是不同概念；相同值可能使筆數比例不恰好等於 10%。
4. 繪製五產品百分位比較圖，以及使用共同金額區間、正規化比例的分布圖，確保比較尺度一致。
5. 寫下三項有數值支持的發現與兩項分析限制。若產品差異很小，也應如實報告；這是模擬金額資料，沒有日期、成本或顧客資訊，不可直接推論成長趨勢、利潤或顧客行為。

查核要求：各產品有效＋缺失＝總筆數，且最小值 ≤ P25 ≤ P50 ≤ P75 ≤ P90 ≤ P99 ≤ 最大值。若採分塊處理，須正確計算全體分位數，不能平均各塊的百分位；若用近似算法，需交代誤差並與精確結果核對。
```

 **對答案**
繳交：`quarter_summary.csv`、比較圖、完整程式與簡短分析報告，說明計算方法、查核證據與結論限制。

## Unit 3｜OpenCode：製作互動儀表板

教師使用 [OpenCode](https://opencode.ai/) 示範，把 Unit 2 的月報資料做成本機儀表板：

- 切換產品 A–E。
- 顯示 P50、P75、P90 與直方圖。
- 下載目前產品的圖表。
- 核對產品 C 的統計結果是否與 Unit 2 一致。

練習把需求說清楚，觀察 Agent 如何規劃、修改檔案與執行，再以實際操作驗收成果。

### 安裝、設定與使用（以 macOS 為例）
* 安裝初始化
```bash
# 1. 安裝 OpenCode 2（已安裝者可略過）
curl -fsSL https://opencode.ai/v2/install | bash

# 2. 重新載入終端機設定，確認版本為 2.x
source ~/.zshrc

# 3. 快速設定
mkdir -p ~/.config/opencode

curl -fL \
  https://raw.githubusercontent.com/waue0920/ai_course_handson/main/unit3_opencode/config/opencode.json \
  -o ~/.config/opencode/opencode.json
```

* 執行
```bash
# 4. 將引號內文字替換為 Issue #1 公布的完整 Key
export NCHC_RAP_KEY='貼上課堂提供的 Key'

# 5. 啟動 OpenCode
opencode
```
