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
```

## 📊 這個專案在做什麼？

我平常在工作中會用 Trello 管理訂單，為了自動化報表作業，我寫了 Python 程式：
1. 透過 Trello API 自動抓取訂單資料
2. 將抓下來的資料和成本資料進行比對
3. 自動計算每筆訂單的利潤，產生三種報表

## 📁 提前準備檔案

在使用本專案之前，請先完成以下五個步驟，準備好需要的檔案和資訊：

### 第一步：搞懂 Trello 的基本結構
Trello 的資料結構很直觀，就像一面大白板：

| 元件 | 說明 | 範例 |
|------|------|------|
| 看板 (Board) | 代表一個大專案或工作流 | 「2025年訂單處理」 |
| 列表 (List) | 看板裡的階段分類 | 「待處理」、「出貨中」、「已完成」 |
| 卡片 (Card) | 最基本的任務單元 | 「客戶A的訂單#123」 |

### 第二步：取得 API 金鑰
1. 登入 Trello 後，前往 [Trello App-Key 頁面](https://trello.com/app-key)
2. 找到「開發人員 API 金鑰」→ 這是你的 `API_KEY`
3. 在同一頁下方點擊「手動生成權杖 (Token)」→ 這是你的 `API_TOKEN`

### 第三步：找到你的看板 ID
打開瀏覽器進到你的 Trello 看板，直接看網址列：
https://trello.com/b/XXXX123/2025-orders


其中 `XXXX123` 這串英數混合的編號，就是你的 `BOARD_ID`。

### 第四步：建立 .env 檔案保護機密資料
在你的 Python 專案資料夾裡，手動新增一個純文字檔，並命名為 `.env`（注意前面有個點）。

貼上以下內容並填入你的資訊：
TRELLO_API_KEY=你的API金鑰
TRELLO_TOKEN=你的API權杖
TRELLO_BOARD_ID=你的看板ID


安裝讀取環境變數的套件：
pip install python-dotenv



⚠️ **非常重要**：務必把 `.env` 加到你的 `.gitignore` 檔案中，絕對不要上傳到 GitHub！

### 第五步：關於免費版與資料抓取
如果你的 Trello 是免費版，API 能抓到的卡片資訊可能有限。要完整抓取所有卡片資料（例如自訂欄位），可能需要付費升級方案。建議先用免費版試抓，確認是否滿足需求再考慮升級。

## 🛠️ 使用技術

- **Python 3.8+**：主要開發語言
- **Trello API**：透過 REST API 取得看板資料
- **Pandas**：資料清理、合併、分析
- **Jupyter Notebook**：逐步執行程式碼
- **python-dotenv**：環境變數管理

## 📁 專案檔案說明

| 檔案名稱 | 說明 |
|---------|------|
| `01_從Trello抓取資料.ipynb` | 連接 Trello API 抓取訂單資料 |
| `02_計算利潤.ipynb` | 計算利潤並產生報表 |
| `Cost.xlsx` | 產品成本主檔 |
| `2026-Trello-data.csv` | 從 Trello 抓下來的訂單資料 |







