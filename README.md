# Trello 訂單資料分析工具

這是一個透過 Python 連接 Trello API，自動抓取訂單資料並進行利潤分析的實戰專案。

## 📊 這個專案在做什麼？

我平常在工作中會用 Trello 管理訂單，為了自動化報表作業，我寫了 Python 程式：
1. 透過 Trello API 自動抓取訂單資料（2026-Trello-data.ipynb）
2. 將抓下來的資料（2026-Trello-data.csv）和成本資料（Cost.xlsx）進行比對
3. 自動計算每筆訂單的利潤，產生三種報表：
   - `Detailed_Report.csv`：詳細訂單明細
   - `Profit_Report.csv`：產品利潤分析
   - `Unmatched_Products.csv`：無法匹配成本的異常產品

## 🛠️ 使用技術

- **Python 3.8+**：主要開發語言
- **Trello API**：透過 REST API 取得看板資料
- **Pandas**：資料清理、合併、分析
- **Jupyter Notebook**：逐步執行程式碼，方便除錯和說明
- **python-dotenv**：管理 API 金鑰等敏感資訊

## 📁 專案檔案說明

### 原始程式碼
| 檔案名稱 | 說明 |
|---------|------|
| `2026-Trello-data.ipynb` | 連接 Trello API，抓取看板上的訂單資料 |
| `V10-計算利潤.ipynb` | 將訂單資料與成本資料合併，計算利潤並產生報表 |

### 輸入資料
| 檔案名稱 | 說明 |
|---------|------|
| `Cost.xlsx` | 產品成本主檔（包含 Product_ID 和 Cost） |
| `2026-Trello-data.csv` | 從 Trello 抓下來的原始訂單資料 |

### 輸出報表
| 檔案名稱 | 說明 | 用途 |
|---------|------|------|
| `Detailed_Report.csv` | 每筆訂單的詳細資料（含利潤） | 營運管理 |
| `Profit_Report.csv` | 按產品彙整的利潤分析 | 經營決策 |
| `Unmatched_Products.csv` | 無法匹配成本的產品清單 | 資料品質改善 |

## 🚀 如何執行

### 1. 安裝所需套件
```bash
pip install requests pandas python-dotenv openpyxl
