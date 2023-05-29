# Regression Model for California House Pricing
Capstone Project Module 3
```
StudentID : JCDSOL-009-002
Kelas     : JCDSOL-09 (WA)
Topik     : California House Pricing
```
## Dataset
Dataset diambil dari [kaggle]([https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis](https://www.kaggle.com/datasets/camnugent/california-housing-prices) dan dimodifikasi oleh Purwadhika

## **BUSINESS PROBLEM UNDERSTANDING**

### **Context**

California, *the Golden State*, merupakan sebuah negara bagian di Amerika Serikat yang terletak di Pesisir Pasifik. Dengan jumlah penduduk lebih dari 39,2 juta jiwa dan total area sekitar 423.970 km<sup>2</sup> menjadikan California sebagai negara bagian Amerika Serikat yang terpadat berdasarkan kepadatan penduduk. PDB (produk domestik bruto) California sebesar 3.598 triliun USD pada tahun 2022 menjadikannya sebagai ekonomi sub-nasional terbesar di dunia. California juga merupakan rumah bagi beberapa perusahaan terbesar di dunia seperti Google dan Facebook dan tempat tinggal orang-orang terkaya di dunia.

Perekonomian yang maju menjadikan California sebagai kota dengan market properti yang paling mahal di Amerika Serikat.

### **Problem Statement**

Berdasarkan data dari [redfin](https://www.redfin.com/state/California/housing-market), harga median sebuah rumah sekarang (Q1 2023) di California sudah mencapai 750k USD, lebih dari dua kali harga nasional (370k USD). California memiliki empat dari lima pasar perumahan termahal di AS, yaitu Silicon Valley, San Francisco, Orange County, dan San Diego. Namun, tingkat kemiskinan, jika disesuaikan dengan biaya hidup, adalah yang terburuk di negara ini. California menyumbang 12% dari dari total populasi AS, tetapi seperempatnya merupakan tunawisma.

Dalam 5 tahun terakhir *supply* perumahan di pasar properti California mengalami penurunan, sedangkan tren untuk *demand* cenderung meningkat. Meskipun di awal tahun 2023 terdapat penurunan yang sangat drastis pada *demand*, tetapi grafik terus naik di bulan selanjutnya. Keadaan ini menyebabkan *house market bubble* sehingga harga rumah mencapai level yang tidak masuk akal, bahkan untuk penduduk dengan ekonomi menengah. Sebuah agen *real-estate*, [houzeo](https://www.houzeo.com/blog/california-real-estate-market/#housing-market-bubble), dalam artikel mereka mengatakan bahwa *house market bubble* memang sudah terjadi di California.

Selanjutnya, untuk menangani masalah ini sebuah perusahaan properti membuat plan untuk membangun perumahan baru untuk menambah *supply* di pasar. **Perusahaan ingin mendapatkan prediksi harga dari rumah yang akan dibangun sebagai pertimbangan untuk perencanaan biaya pembangunan dan perhitungan revenue yang didapat**.

### **Goals**

Berdasarkan problem tersebut, perusahaan tentu menginginkan ***`tool`* yang membantu dalam perhitungan prediksi harga** yang nantinya akan membantu mereka untuk mengambil keputusan.

### **Analytic Approach**

Analisis dilakukan dengan menggunakan fitur-fitur yang dari data sensus, melihat pola dari tiap fitur dan perbedaan antara satu perumahan dengan perumahan lainnya. Selanjutnya **menggunakan regresi untuk membangun model** yang akan digunakan melakukan prediksi terhadap harga median dari perumahan, yang nantinya akan digunakan oleh perusahaan sebagai dasar pertimbangan untuk biaya pembangunan dan perhitungan revenue.

### **Metric Evaluation**

Terdapat tiga metrik evaluasi yang digunakan, yaitu :

1. **RMSE** : nilai rataan akar kuadrat dari error
2. **MAE** : rataan nilai absolut dari error
3. **MAPE** : rataan persentase error

Semakin kecil nilai RMSE, MAE, dan MAPE yang dihasilkan, berarti model semakin akurat dalam memprediksi harga perumahan sesuai dengan limitasi fitur yang digunakan. Selain itu, jika model yang bagus ternyata adalah model regresi linear, maka evaluasi metrik **R-Squared** juga akan digunakan. Untuk metrik R-Squared, semakin mendekati 1, maka semakin fit pula modelnya terhadap data observasi.

Dikarenakan RMSE dan MAE sangat dipengaruhi oleh outlier, maka sebisa mungkin semua outlier akan dihilangkan.
