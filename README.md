# Taiwan Stock Dashboard

使用 Python 與 Streamlit 建立的台灣股票技術分析儀表板。

系統整合上市與上櫃股票即時報價、歷史行情、技術指標、融資融券、三大法人、基本面、籌碼分布及股票新聞，並透過 Plotly 提供互動式圖表。

本專案主要用於展示 Python 資料處理、公開資料串接、網頁資料擷取、技術分析、資料視覺化及 Streamlit Web App 部署能力。

## 線上展示

[開啟 Taiwan Stock Dashboard](https://taiwan-stock-dashboard-dfmapmtnrxbnr9mpwfojpm.streamlit.app)

## GitHub Repository

[查看專案原始碼](https://github.com/st3325228228-cpu/taiwan-stock-dashboard)

---

## 專案特色

- 支援台灣上市與上櫃股票查詢
- 自動判斷 TWSE 或 TPEX 股票
- 顯示盤中即時價格與漲跌幅
- 提供歷史股價與成交量資料
- 整合多種常見技術分析指標
- 顯示融資、融券與三大法人資料
- 提供基本面、籌碼分布與股票新聞
- 顯示支撐、壓力與技術訊號
- 提供自選股清單
- 使用 Plotly 建立互動式圖表
- 使用 Streamlit 建立網頁操作介面
- 使用快取降低重複資料請求
- 使用並行請求提升資料載入效率
- 部署至 Streamlit Community Cloud

---

## 主要功能

### 1. 股票查詢

使用者可以輸入股票代號，例如：

```text
2330
2330.TW
```

系統會根據股票代號取得對應的價格與市場資料。

### 2. 即時報價

系統整合台灣證券交易所與櫃買中心公開資料，顯示：

- 股票名稱
- 即時成交價
- 漲跌金額
- 漲跌幅
- 今日開盤價
- 今日最高價
- 今日最低價
- 昨日收盤價
- 成交量
- 資料時間
- 上市或上櫃資料來源

### 3. 歷史行情

可調整查詢天數，檢視股票歷史資料：

- 開盤價
- 最高價
- 最低價
- 收盤價
- 成交量
- 日 K 線
- 週 K 線
- 月 K 線

### 4. 技術指標

系統提供以下技術分析指標：

- K 線 Candlestick
- 移動平均線 MA5
- 移動平均線 MA20
- 移動平均線 MA60
- KD 隨機指標
- MACD
- RSI 相對強弱指標
- Bollinger Bands 布林通道
- Fibonacci Retracement 費波那契回撤
- VWAP 成交量加權平均價
- OBV 能量潮
- Williams %R 威廉指標
- CCI 商品通道指標

使用者可以透過介面選擇是否顯示：

- 布林通道
- 費波那契回撤
- VWAP

### 5. 支撐與壓力分析

系統根據近期股價資料計算：

- 近 20 日壓力
- 近 60 日壓力
- 近 20 日支撐
- 近 60 日支撐
- Pivot Point 樞紐點
- 壓力位 R1、R2
- 支撐位 S1、S2
- 現價與關鍵價位距離

### 6. 融資融券

整合 TWSE 融資融券公開資料，顯示：

- 融資買進
- 融資賣出
- 融資餘額
- 融券賣出
- 融券回補
- 融券餘額
- 融資與融券比例
- 資料日期

### 7. 三大法人

顯示主要法人買賣超資料：

- 外資買賣超
- 投信買賣超
- 自營商買賣超
- 三大法人合計
- 資料日期

### 8. 基本面資料

整合台灣證券交易所公開資料，顯示：

- 本益比 P/E
- 股價淨值比 P/B
- 殖利率
- 市值
- 基本面資料日期

### 9. 股東與籌碼資料

系統可顯示：

- 主要股東資料
- 股東持股比例
- 集保戶股權分散
- 不同持股級距人數
- 不同持股級距比例
- 散戶與大戶籌碼分布

### 10. 股票新聞

透過 Yahoo 新聞 RSS 搜尋股票相關消息，顯示：

- 新聞標題
- 新聞連結
- 發布時間
- 新聞來源

### 11. 技術訊號評分

系統根據技術指標與市場資料產生規則式訊號摘要，包括：

- 多方訊號
- 空方訊號
- 技術評分
- 參考目標價
- 參考停損價
- 風險報酬比
- 技術面判斷

> 此功能為規則式技術分析，不是經過訓練的機器學習或深度學習預測模型。

### 12. 即時警示

當市場資料符合特定條件時，系統可顯示：

- 價格異常訊號
- 成交量變化
- 均線交叉
- RSI 超買或超賣
- MACD 黃金交叉或死亡交叉
- 支撐與壓力接近提醒

### 13. K 線型態分析

系統根據近期 K 線資料辨識部分常見型態，並提供簡要技術說明。

### 14. 多週期分析

同時觀察：

- 日線趨勢
- 週線趨勢
- 月線趨勢

協助比較不同時間週期的多空方向。

### 15. 自選股清單

使用者可以在側邊欄維護常用股票清單，快速切換與查詢不同股票。

---

## 系統流程

```text
使用者輸入股票代號
          ↓
判斷上市或上櫃市場
          ↓
取得即時報價與歷史行情
          ↓
取得融資融券、法人及基本面資料
          ↓
取得籌碼資料與相關新聞
          ↓
使用 pandas 與 NumPy 清洗資料
          ↓
計算技術指標與關鍵價位
          ↓
產生規則式訊號與警示
          ↓
使用 Plotly 建立互動式圖表
          ↓
透過 Streamlit 顯示分析結果
```

---

## 資料來源

本專案整合或使用以下公開資料與服務：

- 台灣證券交易所 TWSE
- 證券櫃檯買賣中心 TPEX
- 公開資訊觀測站 MOPS
- 臺灣集中保管結算所 TDCC
- Yahoo 新聞 RSS
- Yahoo Finance／yfinance

各資料來源可能因網站、API 或欄位格式調整而需要更新程式。

---

## 使用技術

### 程式語言

- Python

### Web App

- Streamlit

### 資料處理

- pandas
- NumPy

### 資料視覺化

- Plotly
- Plotly Graph Objects
- Plotly Subplots

### 網路資料存取

- requests
- BeautifulSoup
- lxml
- XML ElementTree
- yfinance

### 效能處理

- Streamlit Cache
- ThreadPoolExecutor
- 並行資料請求
- API Timeout
- 例外處理

---

## 專案檔案

```text
taiwan-stock-dashboard/
├── .streamlit/
│   └── config.toml
├── README.md
├── requirements.txt
└── stock_dashboard_streamlit.py
```

### 檔案說明

| 檔案 | 說明 |
|---|---|
| `.streamlit/config.toml` | Streamlit 介面與伺服器設定 |
| `stock_dashboard_streamlit.py` | 股票資料取得、技術分析、視覺化及 Streamlit 主程式 |
| `requirements.txt` | 專案使用的 Python 套件 |
| `README.md` | 專案功能、安裝與使用說明 |

---

## 安裝方式

### 1. 下載專案

```bash
git clone https://github.com/st3325228228-cpu/taiwan-stock-dashboard.git
```

### 2. 進入專案資料夾

```bash
cd taiwan-stock-dashboard
```

### 3. 建立虛擬環境

Windows：

```bash
python -m venv .venv
.venv\Scripts\activate
```

macOS／Linux：

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 4. 安裝套件

```bash
pip install -r requirements.txt
```

若需要手動安裝，可執行：

```bash
pip install streamlit yfinance plotly pandas numpy requests beautifulsoup4 lxml
```

### 5. 啟動程式

```bash
streamlit run stock_dashboard_streamlit.py
```

啟動後，瀏覽器通常會自動開啟：

```text
http://localhost:8501
```

---

## 使用方式

1. 開啟 Streamlit 應用程式。
2. 在股票代號欄位輸入股票代號。
3. 調整歷史資料查詢天數。
4. 選擇是否顯示布林通道、費波那契或 VWAP。
5. 等待系統取得股票資料。
6. 查看即時報價、技術圖表、籌碼與新聞。
7. 使用自選股功能快速切換股票。

---

## 快取設定

為降低重複請求並改善載入速度，系統針對不同資料設定快取時間。

例如：

- 即時報價：約 30 秒
- 股票新聞：約 10 分鐘
- 歷史行情：約 1 小時
- 融資融券：約 1 小時
- 法人資料：約 1 小時
- 基本面與籌碼資料：約 1 天

實際快取時間以程式設定為準。

---

## 系統限制

- 公開資料來源可能有延遲。
- 非交易時間可能無法取得最新盤中價格。
- 上市與上櫃資料格式可能不同。
- 外部網站改版後，部分資料擷取功能可能失效。
- 部分股票可能缺少基本面、股東或籌碼資料。
- 新上市股票可能沒有足夠歷史資料。
- 技術指標只能反映歷史價格與成交量。
- 規則式訊號不代表未來價格一定上漲或下跌。
- 免費雲端部署可能有休眠或資源限制。
- 大量或頻繁查詢可能受到資料來源限制。

---

## 資料與投資風險聲明

本專案僅供：

- Python 程式設計學習
- 資料分析練習
- 技術分析研究
- Web App 開發展示
- 個人作品集展示

本系統提供的價格、指標、評分、目標價、停損價及其他分析結果，均不構成任何形式的投資建議、買賣推薦或獲利保證。

股票市場具有風險，使用者進行任何投資決策前，應自行確認官方資料並獨立判斷。

---

## 專案目的

本專案用於練習與展示以下能力：

- Python 程式設計
- pandas 資料清洗與分析
- NumPy 數值運算
- REST API 串接
- JSON 與 XML 資料解析
- 網頁資料擷取
- BeautifulSoup HTML 解析
- 股票技術指標計算
- 金融資料分析
- Plotly 互動式視覺化
- Streamlit Web App 開發
- Session State 狀態管理
- 資料快取
- 並行資料請求
- 例外處理
- 雲端部署

---

## 未來改進方向

- 加入使用者登入功能
- 加入自選股永久儲存
- 加入 SQLite 或 PostgreSQL 資料庫
- 加入股票歷史資料定時更新
- 加入多股票比較功能
- 加入產業分類與同業比較
- 加入財務報表分析
- 增加營收與 EPS 趨勢圖
- 顯示除權息與股利資料
- 加入價格與成交量通知
- 加入 Telegram 或 Email 警示
- 增加更多 K 線型態
- 加入回測系統
- 顯示策略勝率與最大回撤
- 將規則式訊號與機器學習模型分開呈現
- 加入完整 ML 模型訓練與評估流程
- 使用 FastAPI 建立後端 API
- 使用 Docker 建立標準化部署環境
- 加入單元測試
- 建立 GitHub Actions CI/CD
- 加入資料來源狀態監控
- 改善手機與平板操作介面

---

## License

本專案目前主要作為個人學習及作品展示用途。

如需引用、修改或重新散布，請先確認各資料來源的使用規範及相關授權條件。
