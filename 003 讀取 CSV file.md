## 讀取 CSV file
```
import gc

import csv
import numpy as np
import pandas as pd

csvFilename = "./source/tx_15n.csv"

# use panda
dfTX_Data = pd.read_csv(csvFilename)
dfTX_Data.index = pd.to_datetime(dfTX_Data['Date'])

print(dfTX_Data)

dfTmp = dfTX_Data['2019/05/02 09:00':'2019/05/04 09:00']
print(dfTmp)
```
