# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding

Jaya Jaya Maju adalah perusahaan dengan lebih dari 1000 karyawan yang menghadapi tantangan tingginya **attrition rate** (karyawan yang keluar). Tingginya attrition ini berpotensi meningkatkan biaya rekrutmen, menurunkan produktivitas, dan mengganggu stabilitas operasional. Oleh karena itu, perusahaan ingin memahami faktor penyebab attrition dan melakukan prediksi agar dapat mengambil tindakan preventif.

---

## Permasalahan Bisnis

1. Mengapa tingkat attrition karyawan cukup tinggi?  
2. Siapa saja karyawan yang berisiko tinggi mengalami attrition?  
3. Bagaimana memprediksi attrition untuk membantu HR melakukan intervensi lebih awal?

---

## Cakupan Proyek

- Eksplorasi dan analisis data karyawan untuk memahami pola attrition.  
- Pembersihan dan persiapan data dengan encoding dan scaling.  
- Pembangunan model prediksi attrition menggunakan Logistic Regression.  
- Evaluasi model dengan metrik classification report dan confusion matrix.  
- Penyimpanan model dan fitur untuk keperluan deployment.

---

## Persiapan

### Sumber Data  
Dataset yang digunakan dalam proyek ini berjudul **Employee Data** dan diperoleh dari repositori GitHub.

🔗 [Employee Data – GitHub Repository](https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee)

### Setup Environment  
Ikuti langkah-langkah berikut untuk menyiapkan dan menjalankan proyek ini di lingkungan lokal Anda:

#### 1. Buat Virtual Environment (Opsional tapi Disarankan)
```bash
python -m venv venv
```
#### 2. Aktifkan Virtual Environment
Windows:
```bash
.\venv\Scripts\activate
```
macOS/Linux:
```bash
source venv/bin/activate
```
#### 3. Install Dependensi
Instal semua dependensi yang dibutuhkan dari file requirements.txt:
```bash
pip install -r requirements.txt
```
#### 4. Jalankan Notebook Analisis
Silakan buka file **`notebook.ipynb`** menggunakan **Jupyter Notebook** atau **ekstensi Jupyter di VSCode**, lalu jalankan semua sel satu per satu untuk melakukan proses eksplorasi dan analisis terhadap data yang tersedia.

#### 5. Jalankan Skrip Prediksi
Jika ingin melakukan prediksi terhadap data baru, Anda dapat mengedit variabel sample_input yang terdapat di dalam script **`predict.py`** Variabel ini berisi contoh data input yang akan digunakan oleh model saat aplikasi dijalankan.
```bash
python predict.py
```
#### 6. Jalankan Dashboard Visualisasi
```bash
streamlit run dashboard.py
```

## Hasil Analisis Visualisasi

1. **Rata-rata Pendapatan Bulanan Berdasarkan Status Attrition**  
   Visualisasi menunjukkan bahwa karyawan yang tidak mengalami attrition (Attrition = 0) memiliki rata-rata pendapatan bulanan yang lebih tinggi dibandingkan dengan mereka yang keluar dari perusahaan (Attrition = 1). Perbedaan yang cukup mencolok ini menunjukkan bahwa kompensasi merupakan faktor penting yang memengaruhi keputusan karyawan untuk tetap tinggal atau meninggalkan perusahaan.

2. **Distribusi Umur Berdasarkan Status Attrition**  
   Boxplot distribusi usia menunjukkan bahwa karyawan yang mengalami attrition cenderung berusia lebih muda (sekitar 25–35 tahun), dengan median usia lebih rendah dibandingkan dengan yang bertahan. Hal ini mengindikasikan bahwa karyawan muda lebih rentan untuk keluar, kemungkinan karena lebih fleksibel dalam mencari peluang kerja lain, atau merasa kurang memiliki keterikatan dengan perusahaan.

3. **Attrition Berdasarkan Status Lembur (OverTime)**  
   Karyawan yang sering lembur (`OverTime = Yes`) memiliki proporsi attrition yang jauh lebih tinggi dibandingkan yang tidak lembur. Ini menunjukkan bahwa beban kerja berlebih atau jam kerja yang panjang dapat menjadi salah satu penyebab utama karyawan memutuskan untuk keluar. Oleh karena itu, pengelolaan beban kerja menjadi aspek penting dalam strategi retensi karyawan.

4. **Attrition Berdasarkan Kepuasan Kerja (Job Satisfaction)**  
   Meskipun semua level kepuasan kerja menunjukkan adanya attrition, tingkat attrition tertinggi terjadi pada karyawan dengan skor kepuasan kerja yang rendah (skor 1 dan 2). Sebaliknya, karyawan dengan kepuasan kerja tinggi (skor 3 dan 4) memiliki proporsi attrition yang lebih kecil. Ini menegaskan bahwa kepuasan kerja merupakan faktor penting dalam mempertahankan karyawan.

5. **Rata-rata Tahun Bekerja Berdasarkan Status Attrition**  
   Dari visualisasi rata-rata tahun bekerja, terlihat bahwa karyawan yang tetap bertahan memiliki masa kerja yang lebih lama dibandingkan mereka yang keluar. Ini menunjukkan bahwa semakin lama seseorang bekerja di perusahaan, semakin besar kemungkinan mereka untuk bertahan, kemungkinan karena loyalitas, jenjang karier yang jelas, atau keterikatan yang sudah terbentuk.

6. **Distribusi Jarak Rumah ke Kantor Berdasarkan Status Attrition**  
   Meskipun sebagian besar karyawan, baik yang bertahan maupun yang keluar, tinggal dalam jarak dekat ke kantor, proporsi attrition cenderung sedikit lebih tinggi pada mereka yang tinggal lebih jauh. Jarak rumah ke kantor bisa menjadi faktor stres tambahan yang mendorong karyawan untuk keluar, terutama jika tidak ada kebijakan kerja fleksibel.

7. **Attrition Berdasarkan Frekuensi Perjalanan Dinas (Business Travel)**  
   Karyawan yang sering melakukan perjalanan bisnis memiliki tingkat attrition yang lebih tinggi dibandingkan dengan mereka yang jarang atau tidak pernah melakukan perjalanan dinas. Hal ini bisa disebabkan oleh kelelahan, ketidakseimbangan work-life balance, atau stres dari mobilitas tinggi yang berulang.

8. **Jumlah Karyawan per Departemen dan Status Attrition**  
   Visualisasi jumlah karyawan dan attrition berdasarkan departemen menunjukkan bahwa departemen *Research & Development* memiliki jumlah kasus attrition tertinggi secara absolut, disusul oleh *Sales*. Sementara itu, departemen *Human Resources* mencatat jumlah attrition yang paling sedikit. Namun, untuk analisis yang lebih akurat, perlu diperhatikan proporsi attrition terhadap total karyawan di tiap departemen untuk mengidentifikasi potensi masalah retensi secara proporsional.

---

Insight dari visualisasi ini memberikan pemahaman mendalam terkait faktor-faktor yang berkontribusi terhadap keputusan karyawan untuk keluar dari perusahaan. Temuan-temuan ini dapat digunakan sebagai dasar bagi tim HR dalam menyusun strategi pencegahan attrition yang lebih efektif dan terarah.

## Business Dashboard (Lokal)

Proyek ini dilengkapi dengan prototipe dashboard interaktif berbasis **Streamlit** yang dirancang untuk membantu tim Human Resources (HR) dalam memahami data karyawan serta memprediksi kemungkinan attrition (keluar dari perusahaan). Meskipun belum terintegrasi dengan platform Business Intelligence (BI) seperti Metabase atau Power BI, semua komponen inti telah tersedia untuk pengembangan lebih lanjut.

Dashboard ini menampilkan beberapa fitur utama:

- **Visualisasi Data Eksploratif (EDA)**: Menyajikan grafik dan insight terkait distribusi usia, pendapatan bulanan, status attrition, dan variabel penting lainnya.
- **Antarmuka Prediksi Interaktif**: Pengguna dapat memasukkan data baru dan mendapatkan prediksi apakah seorang karyawan berisiko keluar atau tidak.

Untuk menjalankan dashboard ini secara lokal, gunakan perintah berikut:

```bash
streamlit run dashboard.py
``` 
Model yang digunakan pada dashboard ini adalah Logistic Regression, dipilih karena kemampuannya dalam memberikan hasil prediksi yang cukup baik. Model ini dilatih menggunakan data historis karyawan, dengan mempertimbangkan fitur-fitur penting seperti usia, pendapatan, jarak ke tempat kerja, dan lainnya. Dalam dashboard, model ini memberikan prediksi probabilistik, yang dapat digunakan untuk menilai tingkat risiko attrition seorang karyawan. 

##  Conclusion

Model **Logistic Regression** berhasil dikembangkan untuk memprediksi kemungkinan attrition (keluar dari perusahaan) pada karyawan, dengan performa yang memadai berdasarkan fitur-fitur yang tersedia dalam data. Model ini bersifat interpretable dan cocok digunakan oleh tim non-teknis, seperti Human Resources (HR), dalam pengambilan keputusan berbasis data.

Melalui analisis eksploratif dan visualisasi data, diperoleh beberapa segmentasi karyawan yang memiliki risiko lebih tinggi mengalami attrition, yaitu:
- Karyawan dengan pendapatan bulanan yang rendah
- Karyawan yang berusia lebih muda (sekitar 25–35 tahun)
- Karyawan yang memiliki frekuensi lembur tinggi (OverTime = Yes)
- Karyawan yang sering melakukan perjalanan dinas
- Karyawan dengan tingkat kepuasan kerja rendah
- Karyawan dengan masa kerja yang pendek
- Karyawan yang tinggal lebih jauh dari kantor

Insight ini memberikan dasar bagi perusahaan untuk menyusun **strategi retensi yang lebih tepat sasaran**, seperti peninjauan kompensasi, pengembangan karier untuk karyawan muda, dan pengelolaan beban kerja bagi karyawan yang sering melakukan perjalanan dinas.

Lebih lanjut, model yang dibangun tidak hanya mampu memprediksi status attrition, tetapi juga memberikan **skor probabilitas** yang dapat digunakan untuk **mengidentifikasi karyawan-karyawan spesifik yang memiliki risiko tinggi keluar dari perusahaan**. Dengan menetapkan ambang batas tertentu (misalnya threshold = 0.5), perusahaan dapat melakukan segmentasi karyawan berdasarkan risiko dan mengambil langkah proaktif untuk mempertahankan talenta yang berharga.

Dengan pendekatan ini, HR tidak hanya bereaksi terhadap attrition yang sudah terjadi, tetapi juga dapat **melakukan pencegahan secara lebih dini dan terukur**.

---

##  Rekomendasi Action Items

Berikut beberapa langkah strategis yang dapat diambil perusahaan berdasarkan hasil analisis:

1. Kurangi beban kerja atau frekuensi perjalanan dinas
   Evaluasi kembali kebijakan business travel, khususnya bagi karyawan yang menunjukkan beban mobilitas tinggi.

2. Tinjau ulang skema kompensasi
   Tingkatkan daya saing gaji, terutama bagi karyawan di kelompok usia muda dengan pendapatan di bawah rata-rata.

3. Fokuskan program retensi untuk karyawan muda
   Implementasikan program pengembangan karier, coaching, mentoring, dan jalur promosi yang jelas untuk meningkatkan loyalitas karyawan muda.

---

Dengan mengimplementasikan strategi-strategi ini, perusahaan diharapkan dapat menurunkan angka attrition secara signifikan dan menciptakan lingkungan kerja yang lebih stabil dan produktif.

