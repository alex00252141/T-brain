# T-brain
### Git 設定 (請提供給我 github account)
* sudo apt-get update
* sudo apt-get -y -qq install git
* git --version
* git clone https://github.com/alex00252141/T-brain.git

### Cloud Storage bucket 設定 ( 請提供給我 google account)
> tbrain-tsmc/ data/ (前處理的資料) <br/>
* https://storage.googleapis.com/tbrain-tsmc/data/YUSUN.zip
* https://storage.googleapis.com/tbrain-tsmc/data/lAW.zip
> tbrain-tsmc/ 模型訓練資料/ tbrain_train_final_0610.csv  

> tbrain-tsmc/training_data/ tbrain_train_title_context.txt	


#### 使用方式請參照 sample.ipynb
* 複製文件至共用資料夾 gsutil cp <file name> gs://tbrain-tsmc 
* 查看storage資料夾 gsutil ls gs://tbrain-tsmc 
* Python讀檔案
``
from google.cloud import storage
import pandas as pd

client = storage.Client()
bucket = client.get_bucket('tbrain-tsmc')
blob = storage.Blob('模型訓練資料/tbrain_train_final_0610.csv', bucket)

content = blob.download_as_string()
train = pd.read_csv(BytesIO(content))
train
``
#### JSON Format: 
``
[{'news_ID': 1,  

  'hyperlink': 'https://news.cnyes.com/news/id/4352432',  
  
  'content': {'title': '量化交易追求絕對報酬 有效對抗牛熊市',  
  
   'context': '近年來投資市場波動越來越明顯，追求低波動、絕對報酬的量化交易備受注目。專家表示，採用量化交易策略投資台股，不管是處於多頭或是空頭市場，績效及波動度均可領跑大盤，甚至比國內投資台股的股票型基金及 ETF 的波動率還低，表現也更為穩定。\n大數據時代來臨，風行歐美 50 年的量化交易儼然成為顯學，台灣亦開始重視此一趨勢發展，也因此，中華機率統計學會及台北科技大學管理學院攜手主辦，並由元大期貨、...'},  
   
  'name': '[]'},  
  
  {...},  
  
  {...}  
  ]``
