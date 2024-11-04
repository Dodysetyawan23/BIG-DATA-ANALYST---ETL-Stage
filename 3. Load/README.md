# Load
Tahap Load adalah langkah terakhir dalam proses ETL (Extract, Transform, Load). Pada tahap ini, data yang telah diekstraksi dan ditransformasi diunggah atau disimpan ke dalam sistem penyimpanan target, seperti data warehouse, database, atau file sistem. Tujuan dari tahap ini adalah untuk memastikan data dapat diakses dengan mudah dan cepat oleh pengguna atau aplikasi lain yang membutuhkannya.

## Macam
1. **Full Load** <br>
Seluruh data baru dimuat ke dalam sistem

2. **Incremental Load** <br>
Hanya data yang berubah atau diperbarui sejak pemuatan terakhir yang akan dimuat.

3. **Real-Time Load** <br>
Data dimuat ke sistem tujuan secara langsung atau mendekati waktu nyata saat data baru masuk

## Tools
Tools yang biasanya dijadikan untuk load data adalah
- MySQL
- PostgreSQL
- Big Query
