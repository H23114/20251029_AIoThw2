# Bank Marketing Regression — 操作說明

本專案用於進行 UCI/Kaggle Bank Marketing 資料的探索式分析與回歸建模視覺化。主作業在 Jupyter Notebook 中完成。

## 專案結構

```
bank_marketing_regression/
├── 7114056078_hw2.ipynb   # 主程式 Notebook
├── bank.csv                # Kaggle 下載的資料檔（請自行放入）
├── report.pdf              # 最終報告（執行後可輸出/覆蓋）
└── requirements.txt        # 套件清單
```

## 環境需求

- Python 3.10+（建議 3.10 或 3.11）
- pip（或 pipx/conda 皆可）
- Jupyter（已列於 `requirements.txt`）

## 安裝步驟（Windows 範例）

1) 進入專案資料夾

- `cd bank_marketing_regression`

2) 建立並啟用虛擬環境（可選，但建議）

- 建立：`python -m venv .venv`
- 啟用：`.venv\Scripts\activate`

3) 安裝套件

- `pip install -r requirements.txt`

## 取得資料集

- 至 Kaggle 下載 Bank Marketing Dataset，將資料檔命名為 `bank.csv` 並放在本資料夾內（與 Notebook 同層）。
- 常見版本以分號 `;` 為分隔符；Notebook 內已實作分隔符自動偵測（`,` 或 `;`）。

## 執行 Notebook

- 啟動 Jupyter：`jupyter notebook`（或 `jupyter lab`）
- 開啟並執行：`7114056078_hw2.ipynb`
- 建議「Run All」依序執行所有儲存格。

Notebook 內容重點：
- 自動偵測 `bank.csv` 分隔符，降低讀檔錯誤機率。
- 產生下列圖表：
  - 數值欄位直方圖（分佈檢視）。
  - 數值欄位相關係數熱圖（自動在欄位不足時跳過）。
  - 類別欄位計數圖（若偵測到 `y` 或 `deposit` 作為標籤，會以其為 hue）。

## 匯出報告（report.pdf）

方式 A（Jupyter 介面）：
- 在瀏覽器的 Notebook 頁面，使用「File → Save and Export As → PDF」，或以「列印為 PDF」輸出為 `report.pdf`，存至專案資料夾覆蓋原檔。

方式 B（nbconvert，無需 LaTeX 的替代流程）：
- 先轉為 HTML：`jupyter nbconvert --to html 7114056078_hw2.ipynb --output report.html`
- 開啟 `report.html`，使用瀏覽器「列印為 PDF」產生 `report.pdf`。

方式 C（nbconvert 直出 PDF，需安裝 LaTeX）：
- `jupyter nbconvert --to pdf 7114056078_hw2.ipynb --output report.pdf`
- 若遇到缺少 LaTeX 的錯誤，改用方式 A 或 B。

## 常見問題（Troubleshooting）

- 找不到檔案：請確認 `bank.csv` 與 Notebook 位於同層目錄，且檔名正確。
- 欄位只剩 1 欄：通常是分隔符不符（`,` vs `;`），Notebook 已自動重試；若仍不正確，請手動確認資料檔的實際分隔符。
- PDF 匯出失敗：多半是缺少 LaTeX。請改用方式 A 或 B 以瀏覽器列印為 PDF。

## 套件清單

請見 `requirements.txt`。
