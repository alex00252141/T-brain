### 注意事項

1. 請從此[google storage連結](https://drive.google.com/file/d/1-bQlFLNdAo9bhouzpXIYCZ0pZb9JZezl/view?usp=sharing)將model:`news_cheat_model_ver_01.h5`下載到local folder位置
1. 需額外安裝套件keras_bert、keras
1. [vocab.txt](https://github.com/alex00252141/T-brain/blob/master/model/vocab.txt)需下載至local folder使用
1. 目前input文章最多400字(`未來最多加廣到500，要在往上就要看訓練GPU的強度了`)
1. 請參考`model/news_cheat_model_predict.ipynb`再現結果

-------
### 2020/7/19 [news_cheat_model_predict_04.ipynb](https://github.com/alex00252141/T-brain/blob/master/model/news_cheat_model_predict_04.ipynb) Release

1. 修正Input文章字元由400->500
2. 之前model無法針對詐騙人名是英文做判斷抓取，此版修正，並加強predict全英文對應取法
3. 民捷之前提供的法院判別詐騙文章有效數從8000筆新增到9600筆
4. 準確率約再提升0.5%
