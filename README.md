# KAM-Analysis

## 關鍵查核事項寫作風格和預測能力之分析

### 目的：若能在不同會計師事務所之間發現寫作風格的差異，就可以利用寫作風格針對會計師事務所進行分類預測，在實務上，如果電腦分類出來的結果與實際上的有所不同，代表該份關鍵查核事項的寫作風格與出具的會計師事務所本身的寫作風格有所落差，則相關的利害關係人就需要特別注意這樣的特殊個案。

---

#### 資料集：台灣經濟新報資料庫中2020-2021年間公司財報中的關鍵查核事項段落
#### 情緒字典：採用財報分析中常用的Ｌ＆Ｍ財務情緒字典，又因文本為中文，所以使用張津挺所翻譯的中文財務情緒字典
#### 可讀性指標：使用宋曜廷等人創建的CRIE文本可讀性指標自動化分析系統所提出之指標
--
#### 方法：

##### 整合自台灣經濟新報資料庫中下載的公司財務報表相關資訊以及關鍵查核事項段落資訊，並且針對關鍵查核事項文字段落進行特徵的提取，
##### 其中特徵分別為文字統計特徵、情緒特徵以及可讀性特徵，以這三個特徵輸入模型進行分類，
##### 分類的類別分別為是否為四大會計師事務所(Big Four vs Non-Big Four)的二分類，以及進一步的分辨是哪一四大會計師事務所、或是非四大會計師事務所的五分類兩種，

##### 模型採用了單一分類器中的決策樹(Decision Tree)、天真貝氏(Naïve Bayes, NB)以及邏輯斯回歸(Logistic Regression)，
##### 以及集成分類器中的自適應增強(Adaptive Boosting, AdaBoost)、隨機森林 (Random Forest)、極限梯度提升 (eXtreme Gradient Boosting, XGBoost)，
##### 皆無調整參數，以原先預設進行訓練分類
--
#### 結果：
##### 不同會計師事務所間的確會有寫作風格的差異，可讀性指標的加入大幅度的提升了分類預測的結果，
##### 且以情感指標與可讀性指標組合得到最好的分類成果，在實務上可找出與平時寫作風格不同的特殊個案，幫助相關利害關係人注意隱含的訊息。


