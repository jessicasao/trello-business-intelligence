# Trello API 整合實戰：自動化訂單分析系統

透過 Python 串接 Trello API，建立從資料擷取、清洗到商業分析的完整流程

## 🚀 兩種使用方式

### 方式一：用自己的 Trello 資料（需要 API 金鑰）
適合已經有 Trello 看板、想要分析自己訂單的使用者。

```bash
# 1. 申請 API 金鑰（詳見 docs/教學指南.md）
# 2. 設定環境變數
cp .env.example .env
# 編輯 .env 填入你的金鑰

# 3. 執行第一個 notebook 抓取資料
jupyter notebook notebooks/01_從Trello抓取資料.ipynb

# 4. 執行第二個 notebook 分析資料
jupyter notebook notebooks/02_計算利潤並產生報表.ipynb
# 在 notebook 中選擇「使用自己的資料」
```

## 📊 這個專案在做什麼？

我平常在工作中會用 Trello 管理訂單，為了自動化報表作業，我寫了 Python 程式：
1. 透過 Trello API 自動抓取訂單資料
2. 將抓下來的資料和成本資料進行比對
3. 自動計算每筆訂單的利潤，產生三種報表

## 🛠️ 使用技術

- **Python 3.8+**：主要開發語言
- **Trello API**：透過 REST API 取得看板資料
- **Pandas**：資料清理、合併、分析
- **Jupyter Notebook**：逐步執行程式碼

## 📁 專案檔案說明

| 檔案名稱 | 說明 |
|---------|------|
| `01_從Trello抓取資料.ipynb` | 連接 Trello API 抓取訂單資料 |
| `02_計算利潤.ipynb` | 計算利潤並產生報表 |
| `Cost.xlsx` | 產品成本主檔 |
| `2026-Trello-data.csv` | 從 Trello 抓下來的訂單資料 |
