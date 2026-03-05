# Trello 訂單資料分析工具

這是一個透過 Python 連接 Trello API，自動抓取訂單資料並進行利潤分析的實戰專案。

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
