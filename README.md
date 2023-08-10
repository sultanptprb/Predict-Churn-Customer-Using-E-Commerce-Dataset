# Predict-Churn-Customer-Using-E-Commerce-Dataset

# 1. Latar Belakang
Perkembangan teknologi saat ini memberikan manfaat dan kemudahan dalam berbagai aktivitas sehari-hari. Aktivitas bisnis melalui media internet merupakan salah satu pemanfaatan teknologi. Internet merupakan sarana elektronik yang dapat dipergunakan untuk berbagai aktivitas seperti komunikasi, riset, dan transaksi bisnis. Sekarang sudah banyak orang yang memanfaatkan internet sebagai media pemasaran dan bisnis. Hal ini tidak aneh mengingat jumlah pengguna internet yang terus bertumbuh pesat dapat menjadi sebuah pasar yang potensial untuk dimasuki para pebisnis. Di lain pihak, praktik e-commerce dan e-bisnis ternyata mempunyai banyak keuntungan baik bagi perusahaan ataupun konsumen. Tren belanja online mulai diminati karena proses keputusan belanja online tidak serumit keputusan pembelian offline. Belanja online memang memudahkan dan menghemat waktu, menghemat biaya dibandingkan belanja tradisional. Proses keputusan belanja online adalah pencarian informasi, membandingkan alternatif yang ada, dan pengambilan keputusan. Pada tahap pencarian informasi, konsumen akan mencari referensi secara online dari manapun (seperti search engine atau Toko Online). Informasi yang dicari adalah berupa opini dari orang lain yang sudah mendapatkan manfaat dari produk yang dibeli ataupun untuk mendapat referensi toko online yang lebih baik.
Begitu ketat persaingan bisnis pada e-commerce membuat pelaku bisnis dari perusahaan 'xxx' melakukan berbagai upaya untuk mempertahankan customer salah satunya dengan berbagai campaign atau teknik marketing lainnya. Upaya yang dilakukan ini untuk menekan angka ***churn*** customer dari perusahaan. ***Churn*** merupakan suatu tindakan ketika customer berhenti melakukan transaksi atau pembelian pada perusahaan. Tingginya nilai ***churn rate*** merupakan hal yang harus dihindari, hal ini juga dapat mengindikasikan bahwa customer tidak puas terhadap pelayanan yang diberikan oleh perusahaan. Dari perusahaan sendiri tentu tidak ingin hal ini terjadi karena dibutuhkan biaya lebih besar untuk mencari customer yang baru dibandingkan biaya untuk mempertahankan customer. Berdasarkan [Philip E. Pfeifer](https://link.springer.com/article/10.1057/palgrave.jt.5740142) dalam jurnal yang berjudul *'The optimal ratio of acquisition
and retention costs'* disebutkan sudah menjadi teori umum bahwa dibutuhkan **5 kali biaya lebih banyak** dalam mendapatkan customer baru dibandingkan biaya dalam mempertahankan pelanggan yang sudah ada. Pada perusahaan 'xxx' ini ingin mengurangi jumlah customer yang ***churn*** dengan melakukan tindakan atau perlakuan yang tepat terhadap customer sesuai dengan *behavior* dari customer tersebut. Selanjutnya akan dilakukan pemodelan dengan menggunakan machine learning untuk memprediksi pelanggan yang akan ***churn*** atau tidak agar perusahaan dapat mengambil langkah yang tepat.

# 2. Rumusan Masalah
Pada suatu perusahaan tingginya pelanggan yang melakukan *Churn* merupakan suatu indikator tingkat kegagalan suatu perusahaan E-Commerce. Dimana apabila *Churn rate* sebesar 5% maka kita akan kehilangan 5% dari pelanggan tersebut. Tentu, Perusahaan sebisa mungkin harus menekan nilai *churn rate* ini sekecil mungkin. Sehingga diperlukan upaya untuk mengurangi persentase pelanggan yang melakukan *Churn*. Seperti disebutkan sebelumnya bahwa untuk mencari pelanggan lebih dibutuhkan biaya yang lebih besar dibandingkan mempertahankan pelanggan. Salah satu cara perusahaan e-commerce mempertahankan pelanggannya agar tidak melakukan Churn yaitu memberikan insentif retensi terhadap pelanggan. Insentif retensi terdiri dari berbagai macam seperti memberikan potongan harga, memberikan layanan yang menarik, memberikan prioritas pelayanan dan lain-lain. Namun, kebijakan pemberian insentif retensi belum dilakukan secara efektif. Kebijakan tersebut sering ditemui berbagai kendala bahkan membuat perusahaan semakin merugi karena pemberian insentif kepada pelanggan yang kurang tepat.

# 3. Tujuan
Sehingga dari permasalahan yang ada, perusahaan ingin memiliki kemampuan untuk dilakukannya prediksi kemungkinan seorang pelanggan akan *Churn* atau tidak. Untuk memfokuskan upaya retensi, pemberian insentif meningkatkan pelayanan pada pelanggan yang terindikasi akan melakukan *Churn*. Selain itu juga agar perusahaan mengetahui faktor yang memengaruhi pelanggan bertahan agar strategi bisnis yang dilakukan tepat dengan keinginan pelanggan untuk menurunkan tingkat dari pelanggan yang *Churn*.

# 4. Confussion Matrix
Target utama dalam masalah ini adalah pelanggan yang berhenti berlangganan (Churn), seperti target yang sudah disebutkan pada context sebelumnya yaitu:

Target:
* 0 : Tidak Churn 
* 1 : Churn

False Positive yaitu pelanggan yang aktualnya tidak churn tetapi diprediksi churn.<br>
**Konsekuensi** : Tidak efektif dalam pemberian insentif. <br>
False negative yaitu pelanggan yang aktualnya churn tetapi diprediksi tidak akan churn. <br>
**Konsekuensi** : Kehilangan pelanggan.

Berdasarkan Metric Evaluation yang ada akan digunakan serta konsekuensi yang ada. Akan dibuat model yang akan mengurangi resiko kehilangan pelanggan karena untuk mendapatkan pelanggan baru membutuhkan biaya lebih banyak dibandingkan kita mempertahankan pelanggan yang ada. Sehingga kita akan fokus pada nilai FN dengan mendapatkan nilai recall yang tinggi dan tetap membandingkan nilai precision agar tidak terlalu jauh, Sehingga digunakan metric F2_score dengan data yang imbalance. Dilakukan juga Sampling Undersampling dan Oversampling. Selanjutnya akan dibandingkan model mana yang paling cocok untuk digunakan pada kasus ini.

# Kesimpulan 
- Dalam melakukan cross validation digunakan 7 model klasifikasi machine learning yaitu Decision Tree, Random Forest, KNNeighbor, Logistic Regressioin, Xtreme G Boost, Gradient Boost, Ada Boost. Dari cross validation ini mengambil 3 model terbaik yang akan dituning, model terbaik berdasarkan akurasi ke data train, Berdasarkan tingkat akurasi yaitu **Xtreme G Boost, Logistic Regression, dan Gradient Boost.** Dengan masing-masing akurasi cross validation sesuai urutan yaitu **67.7%, 66.2%, 65.5%**
- Dalam proses tuning digunakan metode **Randomize Search** karena dirasa parameter pada tuning dari 3 model terlalu banyak dan untuk mempersingkat proses dan waktu tuning dilakukan dengan iterasi masing-masing model sebanyak **1000**. Dalam proses tuning didapatkan akurasi <br>
**XGBoost** = 74.71%<br>
**Logistic Regression**= 67.73%<br>
**Gradient Boost** = 75.9%<br>
Dan selanjutnya akan difitting ke data test, dan didapatkan hasil sebagai berikut.<br>
**XGBoost** = 81.87% <br>
**Logistic Regression** = 74.21% <br>
**Gradient Boost** = 84% <br>

- Berdasarkan hasil dari tuning ke data test maka ditentukan bahwa model terbaik adalah **Gradient Boost** Dengan parameter terbaiknya adalah<br>
'resampler': RandomUnderSampler(random_state=0)<br>
'model__subsample': 0.8<br>
'model__n_estimators': 196<br>
'model__max_features': 8<br>
'model__max_depth': 9<br>
'model__learning_rate': 0.09<br>
- **Gradient boosting** merupakan algoritma klasifikasi machine learning yang menggunakan ensamble dari decision tree untuk memprediksi nilai. **Gradient boosting** termasuk supervised learning berbasis decision tree yang dapat digunakan untuk klasifikasi. Gradient boosting dimulai dengan menghasilkan pohon klasifikasi awal dan terus menyesuaikan pohon baru melalui minimalisasi fungsi kerugian (Natekin dan Knoll, 2013).
- Feature yang paling berpengaruh terhadap model adalah **Tenure** dengan persen importance 38.37% lalu terdapat **CashbackAmount** sebanyak 15.94% dan **WarehouseToHome** sebanyak 9.85%
- Dengan berdasarkan asumsi bahwa  *Customer Acquisitioin Cost* memiliki biaya 5 kali lebih banyak dibandingkan dengan *Customer Retention Cost*, model dapat menghemat hingga **72%** biaya jika dibandingkan dengan tidak menggunakan model 

# Rekomendasi
**Rekomendasi Bisnis :** 
- Pihak perusahaan bisa melakukan eksplorasi kembali terkait pengukuran kepuasan customer, memperbaiki parameter kuesioner, dan memperbanyak dimensi pengukuran kualitas pelayanan, untuk mendapatkan hasil kuesioner yang seobjektif mungkin dan tidak bias. Dimensi-Dimensi yang direkomendasikan seperti, Durasi respon customer care, Durasi pengiriman barang, Kemampuan perusahaan dalam menanggapi komplain, kemampuan perusahaan dalam memberikan solusi dsb.
- Memberikan treatment spesial atau khusus untuk customer dengan masa penggunaan yang masih baru, untuk tetap dapat mempertahankan customer. Dengan harapan customer baru tetap setia dan bisa melakukan repurchase pada e-commerce tersebut
- Perusahaan bisa tetap menjaga customer yang telah lama tidak melakukan transaksi dengan mengirimkan campaign atau iklan terkait produk melalui e-mail atau phone number dari customer untuk tetap menjaga awareness customer terhadap perusahaan.

**Rekomendasi Model**
- Mencari referensi yang lebih kuat dalam melakukan Cost Evaluation dimana perhitungan terkait untung dan rugi biaya lebih akurat dan didukung juga oleh beberapa pandangan ahli.
- Untuk melakukan modelling bisa ditambah beberapa model yang sebelumnya tidak digunakan seperti CATBoost, dan LGBM. Agar memiliki opsi lebih banyak dalam mendapatkan model terbaik.
- Dalam melakukan hyperparameter tuning bisa melakukan Randomize Search dimana setelah mengetahui beberapa parameter terbaik, dituning kembali dengan menggunakan Grid Search agar kemungkinan untuk mendapatkan model terbaik semakin maksimal.
- Menambahkan beberapa feature lain yang dirasa memiliki korelasi yang kuat terhadap target seperti Durasi barang diantar dan diterima dsb. 
