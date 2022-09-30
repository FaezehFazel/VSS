
from pathlib import Path
import pandas as pd
import numpy as np



# Cleaning the files
#### TEST
# wrangling csv files in concat-window\\18 folder
folder_train_ps="C:\\Users\\faeze\\OneDrive - Monash University\\Minor Thesis\\publish\\data\\22\\22_epli"
for file in Path(folder_train_ps).glob('*.csv'):
    df = pd.read_csv(file, header = None)
#     df = df.fillna(0)
    #Replacing true to zero
    df[:-1]= df[:-1]._convert(numeric=True)
    df = df.fillna(0)
    # replace '' with 0
    df.replace(r'^\s*$', 0, regex=True, inplace = True)
    #convert string to float
    df_1 = df.iloc[:,:-1].astype(float)
#     df_1 = df.iloc[:,:-1].astype(int).head()
    df_2 = df.iloc[:,-1]
    df = pd.concat([df_1, df_2],  axis=1)
#     df = df.iloc[1:,:]
    df.to_csv(file.with_suffix('.csv'), index = False, header = None)
    
    #######  In combining process an eextra row is added to dataframe which
#######  needs to be removed and the first column needed to be converted to float (integer) instead of objest.


folder="C:\\Users\\faeze\\OneDrive - Monash University\\Minor Thesis\\publish\\data\\22\\22_epli_vg_combined"
for file in Path(folder).glob('*.csv'):
    df = pd.read_csv(file, header = None)
    df = df.iloc[:-1 , :]
    df.iloc[0:,0] = df.iloc[0:,0].astype(float)
    df.to_csv(file.with_suffix('.csv'), index = False, header = None)
