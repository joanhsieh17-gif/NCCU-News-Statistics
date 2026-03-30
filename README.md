# 政大新聞光速彙整系統 NCCU News Statistics

一個基於 Python 與 Streamlit 打造的自動化網路爬蟲與資料視覺化工具。
本系統能夠自動探勘國立政治大學（NCCU）官方網站的最新新聞分類，並根據使用者指定的月份，快速抓取並彙整新聞資料，最後自動生成視覺化圖表與 Excel 統計報表。

## 專案架構
```
NCCU-News-Statistics/
│
├── app.py              # Streamlit 主程式 (爬蟲邏輯與 UI 介面)
├── requirements.txt    # 專案依賴套件清單
└── README.md           # 專案說明文件
```

## 核心功能
* **自動探勘分類 (Dynamic Category Discovery)**
    * 系統啟動時會自動解析政大官網，抓取最新的新聞分類 ID，無須手動維護分類代碼（並具備快取機制提升效能）。
* **光速爬蟲引擎與智慧煞車 (Smart Crawling Engine)**
    * 透過時間過濾機制，精準抓取目標月份的新聞。
    * 具備「智慧煞車」功能，當爬蟲偵測到文章日期已超過目標月份時，會自動停止翻頁，大幅節省系統資源與等待時間。
* **互動式資料視覺化 (Data Visualization)**
    * 整合 Plotly 呈現豐富的圖表：包含「發布單位分佈」圓餅圖與「新聞分類統計」長條圖。
* **一鍵匯出 Excel 報表 (Excel Report Export)**
    * 將抓取的詳細新聞清單（分類、日期、標題、單位、網址）與統計數據自動排版，並匯出成 `.xlsx` 格式供下載。

##  技術

* **前端介面**: [Streamlit](https://streamlit.io/)
* **資料處理**: [Pandas](https://pandas.pydata.org/)
* **網頁爬蟲**: [Requests](https://requests.readthedocs.io/), [BeautifulSoup4](https://www.crummy.com/software/BeautifulSoup/)
* **資料視覺化**: [Plotly Express](https://plotly.com/python/plotly-express/)
* **Excel 處理**: [Openpyxl](https://openpyxl.readthedocs.io/)

## 安裝與執行

請確保您的電腦已安裝 Python 3.7 或以上版本。

**1. 取得專案**
```bash
git clone [https://github.com/joanhsieh17-gif/NCCU-News-Statistics.git]
cd NCCU-News-Statistics
```

**2. 建立虛擬環境**

`macOS / Linux`
```bash
python -m venv venv
source venv/bin/activate
```

 `Windows`
```bash
py -m venv venv
venv\Scripts\activate
```

**3. 安裝必要套件**
```bash
pip install -r requirements.txt
```

**4. 啟動 Streamlit 應用程式**
```bash
streamlit run app.py
```

## 如何使用
* 執行上述指令後，瀏覽器將自動開啟 http://localhost:8501

* 拖曳滑桿選擇您想抓取的「月份」。

* 點擊 「🚀 開始光速抓取」，等待約 5-10 秒即可查看數據與下載報表。

