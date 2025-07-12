# Saudi Arabia Used Cars Prediction By Machine Learning Model
Additional Portofolio Capstone Project Modul 3 Purwadhika Job Connector Data Science Online Batch 15 (JCDSOL-015)
- Mochamad Aditya Putra
- Link Drive untuk penjelasan PPT: https://drive.google.com/file/d/1ahSQW5Xpmf2x7eKzUYjKpu9ureNFBos4/view?usp=sharing
- Link Drive untuk PPT: https://docs.google.com/presentation/d/1s94GgoHzMH4fj8A6eUXuosuQX68TXjr-/edit?usp=sharing&ouid=115316219821335212082&rtpof=true&sd=true
- Link untuk google collab notebook: https://colab.research.google.com/drive/1RdpwL3b7nLN0UdwjHc1Bz6HkI11PRGq8?usp=sharing
- Link Dashboard Visualisasi: https://public.tableau.com/app/profile/aditya.putra5948/viz/dashboardsyarah/UsedCarsAvailableDashboard?publish=yes
- Link Dashboard Visualisasi (Power BI): https://drive.google.com/file/d/1YF5IkmE4Qmxt80h-HjN_EEf0Xvb7oLxD/view?usp=sharing

# Background
Perkembangan Penjualan Pasar Mobil Bekas di Arab Saudi:
Pasar mobil bekas di Arab Saudi mengalami pertumbuhan yang signifikan dalam beberapa tahun terakhir. Beberapa faktor pendorong utama termasuk peningkatan kesadaran konsumen tentang nilai mobil bekas, pertumbuhan populasi, dan ketersediaan platform digital yang mempermudah transaksi jual-beli mobil bekas.
- Peningkatan Permintaan: Seiring dengan pertumbuhan populasi dan urbanisasi, banyak konsumen yang mencari mobil bekas berkualitas sebagai alternatif dari mobil baru. Ini terutama berlaku bagi mereka yang ingin menghemat biaya tetapi tetap mendapatkan mobil dengan performa baik.
- Platform Online Mempermudah Transaksi: Platform online seperti syarah.com telah memperluas pasar dengan menawarkan berbagai pilihan mobil bekas dengan transparansi harga dan kondisi kendaraan. Hal ini memudahkan pembeli untuk membandingkan harga dan memilih mobil yang sesuai dengan anggaran mereka.
- Dampak Ekonomi: Selain itu, fluktuasi harga minyak dan reformasi ekonomi yang diterapkan oleh pemerintah dalam Visi 2030 turut berpengaruh pada preferensi konsumen. Banyak konsumen yang beralih ke mobil bekas sebagai pilihan lebih ekonomis dalam situasi ketidakpastian ekonomi.
- Tren Mobil Listrik dan Hibrida: Ada juga peningkatan minat terhadap mobil bekas dengan teknologi ramah lingkungan, seperti mobil listrik dan hibrida, sejalan dengan inisiatif pemerintah untuk mengurangi emisi karbon di negara tersebut.

Dataset ini didapat dari Purwadikha dan mewakili daftar mobil bekas yang dikumpulkan dari platform (syarah.com), dengan atribut terperinci untuk setiap mobil seperti tipe model, wilayah, merek, tahun, ukuran mesin, jarak tempuh, dan harga. Pasar mobil bekas di Arab Saudi sangat kompetitif, dipengaruhi oleh kondisi ekonomi, preferensi konsumen, dan kebijakan pemerintah mengenai impor otomotif dan pajak.

Gambaran Pasar:
Arab Saudi merupakan pasar besar untuk mobil baru maupun bekas karena populasi yang besar dan ketergantungan pada mobil sebagai moda transportasi utama. Merek populer seperti Toyota, Kia, GMC, dan merek mewah seperti Land Rover mendominasi pasar. Faktor-faktor yang memengaruhi nilai mobil bekas termasuk reputasi merek, jarak tempuh, kondisi, dan tahun produksi mobil.
Selain itu, dorongan pemerintah Saudi terhadap Visi 2030, yang bertujuan untuk mendiversifikasi perekonomian, juga mempunyai pengaruh tidak langsung dengan menjadikan kendaraan lebih terjangkau melalui reformasi kebijakan, sehingga mendorong minat terhadap pasar mobil bekas.

# Problem Statement
Tujuan penelitian kali ini adalah untuk membantu perusahaan untuk memprediksi harga mobil bekas berdasarkan berbagai atribut seperti jenis mobil, merek, ukuran mesin, jarak tempuh, tahun pembuatan, dan wilayah. Sifat pasar mobil bekas yang berfluktuasi dan beragamnya pilihan yang tersedia membuat harga tidak dapat diprediksi. Selain itu, memahami bagaimana berbagai faktor seperti ukuran mesin dan jarak tempuh memengaruhi harga akhir akan memungkinkan strategi penetapan harga yang lebih baik.

Pertanyaan Kunci:
1. Apa faktor utama yang mempengaruhi harga mobil bekas di Arab Saudi?
2. Bagaimana cara memprediksi harga mobil bekas secara akurat berdasarkan fitur-fiturnya?
3. Apakah model machine learning dapat mengalahkan model rule based non machine learning?

# Goals
Sebelumnya perusahaan sudah membuat rule based model untuk prediksi harga mobil bekas dengan metode Mean Absolute Error dan mendapatkan nilai error sebesar 55230.571 SAR Maka dari itu kita akan membuat model machine learning yang nantinya akan dibandingkan dengan rule based model (non machine learning) untuk mencari tahu model mana yang dapat memprediksi harga mobil bekas secara lebih baik.

Tujuan utama dari analisis ini adalah:
- Mengembangkan model machine learning untuk memprediksi harga mobil bekas berdasarkan fiturnya yang akan dibandingkan dengan model rule based non machine learning.
- Mengidentifikasi fitur terpenting yang mendorong perbedaan harga di pasar mobil bekas.
- Memberikan wawasan yang dapat ditindaklanjuti kepada penjual mobil bekas dan platform seperti syarah.com tentang cara memberi harga kendaraan mereka secara kompetitif.

# Analytical Approach
Analisis dimulai dengan eksplorasi data untuk memahami distribusi variabel dan korelasi antara variabel prediktor dengan harga mobil. Berikut tahapan pendekatan analitis yang dapat diambil:

1. Data Understanding: informasi data, statistic deskriptif, jumlah missing value, dan distribusi data secara keseluruhan
2. Data Cleaning: menangani missing values, duplicated values, anomalies, dan outliers.
3. Exploratory Data Analysis (EDA): Analisis visualisasi untuk memahami pola dan korelasi antar variabel (Q&A based).
4. Data Preparation, Model Development untuk Machine Learning, Hyperparameter Tuning, Feature Importance, Estimasi Keuntungan, dan Limitasi.
5. Kesimpulan dan Rekomendasi.

# Metric Evaluation
Kita akan menggunakan MAE sebagai metrics dalam menentukan model yang akan dipilih dengan alasan sebagai berikut:

MAE mengukur rata-rata kesalahan dalam satuan yang sama dengan variable target 'Price'. Dalam hal ini, kesalahan rata-rata dihitung dalam satuan Riyals. Ini memberikan interpretasi yang mudah dan jelas karena menunjukkan secara langsung berapa besar rata-rata kesalahan prediksi model dalam memprediksi harga mobil.
MAE tidak terlalu sensitif terhadap outliers dibandingkan metric seperti RMSE. Ini berarti bahwa jika ada beberapa harga mobil yang sangat ekstrem (mobil mewah dengan harga sangat tinggi), MAE tidak akan memberikan penalti besar terhadap kesalahan pada outliers tersebut.
MAE memberikan penilaian yang adil terhadap performa model di seluruh rentang harga mobil.
Karena variable target 'Price' memiliki rentang yang cukup luas, seperti pada dataset yang digunakan, MAE bisa digunakan untuk memberikan ukuran yang relatif netral terhadap keseluruhan performa model.
Lalu kita juga akan menggunakan MAPE dan R2 sebagai faktor pendukung MAE dan RMSE sebagai perbandingan terhadap MAE.

# Data Dictionary
|kolom | Penjelasan |
|----- | ---------- |
| Type  | Nama mobil bekas|
| Region| Wilayah tempat mobil bekas ditawarkan untuk dijual|
| Make| Nama perusahaan pembuat Mobil|
| Gear_Type  | Ukuran tipe gear mobil bekas |
| Origin| Asal mobil bekas|
| Options | Pilihan fitur pada mobil bekas|
| Year| Tahun pembuatan|
| Engine_Size | Ukuran mesin mobil bekas|
| Mileage | Jarak tempuh mobil bekas|
| Negotiable | Benar jika harga 0, berarti bisa nego|
| Price| Harga mobil bekas|

# Machine Learning Model Explanation
Model yang merupakan pipeline machine learning yang dirancang untuk memprediksi harga mobil bekas berdasarkan dataset. Berikut penjelasan dari komponen-komponen utama dan prosesnya:
1. ColumnTransformer:

Transformer ini melakukan serangkaian langkah preprocessing pada dataset:
- OneHotEncoder (drop='first'): Variabel kategorikal seperti Gear_Type, Origin, dan Options diubah menjadi fitur biner. Opsi drop='first' mencegah collinearity dengan menghapus kategori pertama dari setiap variabel.
- BinaryEncoder: Untuk variabel kategorikal dengan banyak nilai unik (Type, Region, Make), digunakan metode binary encoding yang mengonversi variabel tersebut ke dalam format numerik.
- MinMaxScaler: Diterapkan pada fitur numerik seperti Year, Engine_Size, dan Mileage. Fitur-fitur ini diskalakan dalam rentang 0 hingga 1 agar bisa dibandingkan secara adil.
- RobustScaler: Diterapkan pada Mileage untuk membuat model kurang sensitif terhadap outlier dengan melakukan scaling berdasarkan rentang interkuartil (IQR).
- Remainder='passthrough': Kolom-kolom yang tidak disebutkan secara eksplisit dalam transformasi akan diteruskan tanpa perubahan.

Model - XGBoost Regressor (XGBRegressor):
Setelah preprocessing, model ini menggunakan XGBoost Regressor untuk memprediksi harga mobil. XGBoost adalah metode ensemble yang kuat berbasis gradient boosting, dikenal karena efisiensi dan performanya dalam tugas regresi maupun klasifikasi.

Beberapa hyperparameter kunci dalam XGBoost Regressor:
- learning_rate=0.037: Mengontrol seberapa cepat model belajar. Nilai yang lebih rendah berarti pembelajaran yang lebih lambat namun biasanya menghasilkan performa yang lebih baik.
- max_depth=8: Menentukan kedalaman maksimum setiap pohon dalam model. Pohon yang lebih dalam bisa menangkap pola yang lebih kompleks, tetapi juga berisiko overfitting.
- n_estimators=768: Jumlah pohon (weak learners) yang digunakan dalam model. Semakin banyak pohon umumnya akan meningkatkan performa hingga batas tertentu.
- colsample_bytree=0.5: Menentukan fraksi fitur yang digunakan saat membangun setiap pohon, memperkenalkan elemen randomisasi dan mengurangi overfitting.
- gamma=1: Mengontrol kompleksitas model. Nilai yang lebih besar menghasilkan model yang lebih sederhana (dengan lebih sedikit pemisahan pada pohon).

Parameter lain seperti subsample, min_child_weight, dan max_leaves juga berperan dalam mengontrol overfitting dan memastikan generalisasi.

# Feature Importance
Berikut merupakan feature (variable dependent) yang mempengaruhi target (price) dari model machine learning yang telah dibuat:
- Engine_Size (minmax):
Fitur ini memiliki pengaruh terbesar dalam model, yang menunjukkan bahwa ukuran mesin mobil adalah faktor paling signifikan dalam memprediksi harga. Semakin besar ukuran mesin, biasanya mobil cenderung lebih mahal karena berhubungan dengan performa dan kapasitas.

- Make_1 (binary):
Fitur ini merujuk pada kategori tertentu dari merek mobil (Make_1), yang ternyata berpengaruh cukup tinggi terhadap harga. Biasanya, mobil dengan merek yang lebih terkenal atau berkualitas tinggi memiliki harga yang lebih mahal.

- Year (minmax):
Tahun pembuatan mobil juga sangat penting dalam menentukan harga. Semakin baru tahun mobil, cenderung harganya lebih tinggi karena teknologi, performa, dan kondisi yang lebih baik.

- Options_Standard (onehot):
Fitur ini menunjukkan preferensi opsi standar yang juga berpengaruh. Mobil dengan opsi standar yang lebih lengkap atau canggih biasanya dihargai lebih tinggi.

- Make_3, Make_4, Make_2 (binary):
Berbagai kategori dari merek mobil (Make_3, Make_4, Make_2) juga memiliki pengaruh signifikan, menunjukkan bahwa merek tertentu selain Make_1 juga menjadi penentu harga.

- Mileage (robust):
Fitur ini mewakili jarak tempuh mobil (dalam mil), yang mempengaruhi harga secara signifikan. Semakin besar jarak tempuh, biasanya harga mobil akan lebih rendah karena mobil dianggap sudah lebih banyak digunakan.

Secara keseluruhan, fitur utama yang berhubungan dengan spesifikasi teknis (seperti ukuran mesin, tahun produksi, jarak tempuh) dan Merek mobil (Make) memberikan kontribusi terbesar dalam memprediksi harga mobil bekas dalam model ini.

# Kesimpulan
Model machine learning dapat memprediksi harga mobil dengan sangat baik dimana hanya memiliki nilai error sebanyak 11134.25 SAR, dengan model memiliki akurasi sebesar 92% dalam memprediksi harga mobil.
