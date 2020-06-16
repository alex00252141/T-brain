# T-brain
### Git 設定 (請提供給我 github account)
* sudo apt-get update
* sudo apt-get -y -qq install git
* git --version
* git clone https://github.com/alex00252141/T-brain.git

### Cloud Storage bucket 設定 ( 請提供給我 google account)
> tbrain-tsmc/ data/ 前處理的資料
> tbrain-tsmc/ 模型訓練資料/ tbrain_train_final_0610.csv

* 複製文件至共用資料夾 gsutil cp <file name> gs://tbrain-tsmc 
* 查看storage資料夾 gsutil ls gs://tbrain-tsmc 
* Python讀檔案
```
from google.cloud import storage
import pandas as pd

client = storage.Client()
bucket = client.get_bucket('tbrain-tsmc')
blob = storage.Blob('模型訓練資料/tbrain_train_final_0610.csv', bucket)

content = blob.download_as_string()
train = pd.read_csv(BytesIO(content))
train
```
