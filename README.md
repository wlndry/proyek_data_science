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

### 1. Rata-rata Pendapatan Bulanan Berdasarkan Status Attrition

Visualisasi menunjukkan bahwa rata-rata pendapatan bulanan karyawan yang **tidak mengalami attrition** (Attrition = 0) lebih tinggi dibandingkan dengan mereka yang mengalami attrition. Ini menunjukkan bahwa karyawan dengan gaji lebih rendah cenderung lebih berisiko untuk keluar dari perusahaan.

### 2. Distribusi Usia Berdasarkan Status Attrition

Distribusi usia mengindikasikan bahwa karyawan yang mengalami attrition cenderung berada pada kelompok usia yang lebih muda (sekitar usia 25–35 tahun), sedangkan karyawan usia di atas 40 cenderung bertahan lebih lama di perusahaan.

### 3. Frekuensi Perjalanan Dinas dan Hubungannya dengan Attrition

Dari visualisasi frekuensi perjalanan dinas, terlihat bahwa proporsi karyawan yang sering melakukan perjalanan bisnis memiliki tingkat attrition yang lebih tinggi dibandingkan mereka yang jarang atau tidak pernah bepergian. Hal ini dapat mengindikasikan bahwa frekuensi perjalanan kerja dapat menjadi faktor stres atau kelelahan.

---

## Business Dashboard (Lokal)

Saat ini belum tersedia dashboard interaktif dalam proyek ini. Namun, model dan fitur telah disimpan dan dapat digunakan untuk pengembangan dashboard di masa mendatang yang dapat membantu HR dalam pengambilan keputusan berbasis data.

Prototipe visualisasi dan prediksi telah dibuat dalam bentuk **Streamlit app** yang dapat dijalankan secara lokal dengan perintah berikut:

```bash
streamlit run dashboard.py
``` 

##  Conclusion

Model Logistic Regression berhasil memprediksi attrition karyawan dengan performa yang memadai berdasarkan fitur-fitur yang tersedia dalam data. Melalui analisis eksploratif, ditemukan bahwa beberapa faktor utama yang secara signifikan berkontribusi terhadap tingginya tingkat attrition antara lain:

-  Pendapatan bulanan yang rendah
-  Usia yang lebih muda
-  Frekuensi perjalanan dinas yang tinggi

Temuan ini memberikan wawasan penting bagi tim Human Resources (HR) untuk menyusun strategi retensi yang lebih terarah dan berbasis data.

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

