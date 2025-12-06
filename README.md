# Analisis A/B Testing: Efektivitas Iklan Pemasaran 📊

Repository ini berisi *notebook* analisis A/B Testing untuk menentukan apakah kampanye iklan pemasaran berhasil meningkatkan *Conversion Rate* (tingkat pembelian produk) secara signifikan dibandingkan dengan *baseline* (PSA).

## 📋 Ringkasan Eksperimen
Perusahaan pemasaran ingin mengetahui seberapa besar kesuksesan kampanye yang dapat dikaitkan langsung dengan iklan.
* **Tujuan:** Menentukan efektivitas iklan dalam mendorong konversi.
* **Metrik Utama:** *Conversion Rate* (Persentase pengguna yang membeli produk).
* **Varian:**
    * **Control (A):** Pengguna yang melihat *Public Service Announcement* (PSA).
    * **Treatment (B):** Pengguna yang melihat Iklan (*Ad*).

## 📂 Dataset
Data yang digunakan berasal dari Kaggle Marketing A/B Testing Dataset.
* **Total Sampel:** 588,101 baris.
* **Fitur Utama:**
    * `test group`: Kelompok eksperimen ('ad' atau 'psa').
    * `converted`: Status pembelian (True/False).
    * `total ads`: Jumlah iklan yang dilihat.
    * `most ads day/hour`: Waktu pengguna paling banyak melihat iklan.

## 🛠️ Teknologi & Libraries
Analisis dilakukan menggunakan **Python** dengan *library* berikut:
* `pandas`: Manipulasi dan pembersihan data.
* `numpy`: Operasi numerik.
* `matplotlib` & `seaborn`: Visualisasi data (Pie chart, Bar chart).
* `scipy.stats` & `statsmodels`: Uji hipotesis statistik (T-test).

## ⚙️ Metodologi
1.  **Data Preprocessing:**
    * Renaming kolom (menghapus spasi).
    * Label Encoding pada kolom `converted` (True=1, False=0).
    * Pengecekan *missing values* dan duplikasi.
2.  **Exploratory Data Analysis (EDA):**
    * Menganalisis distribusi grup (Iklan vs PSA).
    * Menganalisis waktu efektif (Hari dan Jam) penayangan iklan.
3.  **Uji Hipotesis:**
    * $H_0$: Conversion Rate Iklan $\le$ Conversion Rate PSA.
    * $H_1$: Conversion Rate Iklan $>$ Conversion Rate PSA.
    * Menggunakan **T-test** dan **Confidence Interval** dengan tingkat signifikansi ($\alpha$) 0.05.

## 📊 Hasil Temuan
* **Perbandingan Konversi:**
    * Kelompok Iklan (*Ad*): **2.55%**
    * Kelompok PSA: **1.78%**
    * *Lift:* Iklan meningkatkan konversi secara absolut sebesar ~0.77%.
* **Signifikansi Statistik:**
    * **P-value:** $1.70 \times 10^{-13}$ (Sangat kecil, < 0.05).
    * **Keputusan:** Tolak $H_0$. Perbedaan konversi sangat signifikan secara statistik.
* **Wawasan Tambahan:**
    * Iklan paling banyak dilihat pada hari **Jumat** dan **Senin**.
    * Jam paling aktif melihat iklan adalah pukul **10:00 - 15:00**.

## 💡 Rekomendasi Bisnis
Berdasarkan hasil uji statistik, kampanye iklan terbukti **efektif**. Direkomendasikan untuk:
1.  Melanjutkan alokasi anggaran untuk iklan komersial karena terbukti meningkatkan penjualan dibanding PSA.
2.  Mengoptimalkan penayangan iklan pada hari Jumat dan Senin di jam kerja (10:00 - 15:00) untuk memaksimalkan *exposure*.

## 🚀 Cara Menjalankan
1.  Pastikan Python terinstal.
2.  Install dependencies: `pip install pandas matplotlib seaborn scipy statsmodels`.
3.  Jalankan file `A_B_Testing.ipynb`.
