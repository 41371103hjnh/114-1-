# 114-1 師大科技系程式語言
授課教師：蔡芸琤老師  
姓名：何佳恩 系級：科技系二年級   
課程筆記區、作業連結區、專題連結區   
## 🍜[HW1.拉麵點餐系統](https://github.com/41371103hjnh/114-1-/blob/main/HW1%E6%97%A5%E5%B8%B8%E6%94%AF%E5%87%BA%E9%80%9F%E7%AE%97%E8%88%87%E5%88%86%E6%94%A4_gradio.ipynb)  
拉麵店簡易點餐系統， 訂單成立時會附上今日運勢。  
1. I/O to GoogleSheet  
   輸入 (Input to GoogleSheet)：將數據資料寫入 Google 試算表  
   輸出 (Output from GoogleSheet)：從 Google 試算表讀取數據並用於分析或顯示  
2. 使用 if、else、for、def
3. 使用 Gradio連結程式  
## 📋[HW2.成績一本通](https://github.com/41371103hjnh/114-1-/blob/main/HW2_%E6%88%90%E7%B8%BE%E4%B8%80%E6%9C%AC%E9%80%9A_gradio.ipynb)
- 成績紀錄結合AI摘要與建議
- 透過Gemini API key生成AI 摘要  
## 🍅[HW3.番茄鐘系統](https://github.com/41371103hjnh/114-1-/blob/main/HW3_%E5%BE%85%E8%BE%A6%E6%B8%85%E5%96%AE%E8%88%87%E7%95%AA%E8%8C%84%E9%90%98%E7%B4%80%E9%8C%84.ipynb)
1. 任務列表資料可即時同步到Google sheet    
2. 完成任務、刪除任務與查詢功能
3. 番茄鐘計時
4. 生成任務實際花費時間的統計圖表  
5. 可以把結果匯出與匯入紀錄（CSV / JSON）  
6. 結合gemini建議
7. [json檔](https://github.com/41371103hjnh/114-1-/blob/main/tasks_export_20251025_163419.json) [csv檔](https://github.com/41371103hjnh/114-1-/blob/main/tasks_export_20251025_163312.csv)
## 🌳[HW4.環境資訊中心 台灣新聞爬蟲](https://github.com/41371103hjnh/114-1-/blob/main/HW4_%E7%92%B0%E5%A2%83%E8%B3%87%E8%A8%8A%E4%B8%AD%E5%BF%83_%E5%8F%B0%E7%81%A3%E6%96%B0%E8%81%9E%E7%88%AC%E8%9F%B2.ipynb)
- 爬蟲結果完整回傳到試算表crawler分頁(每次刷新)
- 前30熱詞排行，熱詞盡可能排除人名或非文章內容的雜訊
- 關鍵字雲圖
- Gemini 生成各項摘要(含SDGS永續指標分析)
- 可下載壓縮包(兩份csv+一份txt)  
[insight.txt](https://github.com/41371103hjnh/114-1-/blob/main/insight.txt)
[crawler_export.csv](https://github.com/41371103hjnh/114-1-/blob/main/crawler_export.csv)
[stats_export.csv](https://github.com/41371103hjnh/114-1-/blob/main/stats_export.csv)
* 若第一次跑發生版本error，請先跑以下程式碼，跑完刪掉cell 0 ，再手動Runtime-Restart session後應該就能正常啟動了!  
由於不確定是不是自己電腦的問題，因此用這種方式備註，謝謝您   
```python
# Cell 0｜環境修復：解決 numpy/pandas 二進位不相容錯誤
!pip -q uninstall -y numpy pandas scikit-learn scipy jax jaxlib opencv-python opencv-python-headless opencv-contrib-python || true
!pip -q cache purge

# 重新安裝與你 Cell 1 相容的穩定版本
!pip install --no-cache-dir -U \
  "numpy==2.2.1" \
  "pandas==2.2.3" \
  "scikit-learn==1.5.2" \
  "scipy==1.14.1"

# 驗證版本
import numpy, pandas, sklearn, scipy
print("numpy:", numpy.__version__)
print("pandas:", pandas.__version__)
print("scikit-learn:", sklearn.__version__)
print("scipy:", scipy.__version__)

# 🔄 強制重啟 Python 核心（Colab 會提示「重新連線」）
import IPython; IPython.get_ipython().kernel.do_shutdown(True)
```
## 🎄[HW5.新北耶誕城 美食&遊玩地圖指南](https://github.com/41371103hjnh/114-1-/blob/main/HW5_%E6%96%B0%E5%8C%97%E8%80%B6%E8%AA%95%E5%9F%8E_%E7%BE%8E%E9%A3%9F%26%E9%81%8A%E7%8E%A9%E5%9C%B0%E5%9C%96%E6%8C%87%E5%8D%97.ipynb)
1. 自動智慧搜尋：輸入關鍵字即可於耶誕城周邊搜尋美食或景點，並能自動判斷是「美食模式」或「遊玩模式」 
2. SERP API取得資料、Folium地圖整合顯示  
3. 店家資訊小卡：每個地點附有照片縮圖、店名、電話、評分、地址等資訊  
4. AI 逐店分析、TOP 3推薦  
5. 聖誕氛圍介面：燈泡、雪花、金色字體設計，呈現節慶感

## 📚[HW6.課程小助理](https://github.com/41371103hjnh/114-1-/blob/main/HW6_%E8%AA%B2%E7%A8%8B%E5%B0%8F%E5%8A%A9%E7%90%86.ipynb)
1. PDF 課表 → 一鍵轉換成試算表（Gemini 解析）
2. AI生成當日提醒、學習建議
3. 生成每日課程小卡(上課時間、地點、行前提醒、學習建議、即時天氣)
   - 天氣訊息來自Openweather API，地區設定為台北
4. 每日學術文章推薦：Phys.org 自動抽取
5. 雲端留言板（儲存在 Google Sheet留言板分頁）  
[參考課表](https://github.com/41371103hjnh/114-1-/blob/main/export.pdf)
##[專題提案報告](https://www.youtube.com/watch?v=wcNFh9eP8yw)
