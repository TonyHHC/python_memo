```
import gc

from datetime import datetime as dt
from dateutil import parser

import csv
import numpy as np
import pandas as pd

import matplotlib.pyplot as plt

import talib
from talib import abstract

# 取得指定日期 前 n 筆 或 後 n 筆 資料
def Find_n_Rows(dfSource, strDate, iNumRows):
    iIndex = dfSource.loc[dfSource['date'] == strDate].index.values[0]
    if iNumRows < 0:
        dfTmp = dfSource.iloc[iIndex + iNumRows + 1:iIndex + 1]
    else:
        dfTmp = dfSource.iloc[iIndex:iIndex + iNumRows]
    return dfTmp


csvFilename = "./source/AI_Log_15n_50.csv"

# use panda
dfTX_Data = pd.read_csv(csvFilename)

# get percent change
dfTX_Data['PCT_Close'] = (dfTX_Data['close'].pct_change() * 100)
dfTX_Data['SMA'] = abstract.SMA(dfTX_Data['close'], timeperiod=20)

# 取得指定日期 前 n 筆 或 後 n 筆 資料
strDate = '2018/12/28 11:45'

dfTmp = Find_n_Rows(dfTX_Data, strDate, -3)
print(dfTmp)

# get max/min index
print(dfTmp['close'].idxmax())
print(dfTmp['close'].idxmin())

# get max/min value
print(dfTmp['close'].max())
print(dfTmp['close'].min())

# get max/min rows
print(dfTmp.loc[dfTmp['close'].idxmax()])
print(dfTmp.loc[dfTmp['close'].idxmin()])

```
