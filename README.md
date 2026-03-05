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

📁 提前準備檔案
在使用本專案之前，請先完成以下五個步驟，準備好需要的檔案和資訊：
第一步：搞懂 Trello 的基本結構
Trello 的資料結構很直觀，就像一面大白板：
￼
￼
元件
說明
範例
看板 (Board)
代表一個大專案或工作流
「2025年訂單處理」
列表 (List)
看板裡的階段分類
「待處理」、「出貨中」、「已完成」
卡片 (Card)
最基本的任務單元
「客戶A的訂單#123」
