```
from datetime import datetime as dt
from dateutil import parser

import csv
import numpy as np
import pandas as pd

import matplotlib.pyplot as plt

csvFilename = "./source/tx_15n.csv"

#
def NormalizeDate(strDate):
    return parser.parse(strDate).strftime("%A")


# use panda
dfTX_Data = pd.read_csv(csvFilename)
dfTX_Data.index = pd.to_datetime(dfTX_Data['Date'])

dfTX_Data['TEST'] = dfTX_Data['Date'].apply(NormalizeDate)

print(dfTX_Data)
```
