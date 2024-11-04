# Ekstrak
Ekstraksi adalah tahap pertama dalam proses ETL (Extract, Transform, Load). Tahap ini berfungsi untuk menarik data dari berbagai sumber, baik dari sistem database, file flat seperti CSV, API, hingga data streaming.

## Proses Ekstrak
#### 1. File CSV, Excel
```
import pandas as pd

df_military_expenditure = pd.read_csv('Military Expenditure.csv')
df_military_expenditure = pd.read_excel('Military Expenditure.xls')
```

#### 2. MySQL
```
import pymysql
import pandas as pd

HOST = 'xxx'
PORT = 'xxx'
USER = 'xxx'
PASS = 'xxx'
DB = 'xxx'

connMySQL = pymysql.connect(
    host=HOST,
    port=int(PORT),
    user=USER,
    passwd=PASS,
    db=DB,
    charset='utf8mb4'
)

def getData(conn):
    query = """
    SELECT * FROM military_expenditure
    """
    df = pd.read_sql_query(query,conn)
    
    return df

df = getData(connMySQL)
```

#### 3. MongoDB
```
from pymongo import MongoClient
import pandas as pd
# setup koneksi
connMongoDB = MongoClient(
            host = HOST,
            port = int(PORT), 
            serverSelectionTimeoutMS = 3000,
            username=USER,
            password=PASS
        )
db = connMongoDB.warehouse #nama database = warehouse
collection = db.military_expenditure  
# filter data
query = {}

hasil_query = collection.find(query)
# mengumpulkan data menjadi satu json
ls_dokumen = []

for dokumen in hasil_query:
    ls_dokumen.append(dokumen)
ls_dokumen
```