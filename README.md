# Business Understanding

## Latar Belakang Bisnis

Jaya Jaya Maju adalah perusahaan multinasional yang telah berdiri sejak tahun 2000 dan memiliki lebih dari 1000 karyawan yang tersebar di seluruh wilayah Indonesia. Walaupun telah berkembang menjadi perusahaan besar, manajemen masih menghadapi tantangan dalam mengelola sumber daya manusia secara efektif. Salah satu tantangan utama adalah tingginya **attrition rate** (rasio jumlah karyawan yang keluar terhadap total karyawan aktif), yang telah mencapai lebih dari 10%. Tingginya attrition rate ini menimbulkan berbagai dampak negatif, seperti:

- Meningkatnya biaya rekrutmen dan pelatihan.
- Menurunnya produktivitas tim.
- Terganggunya stabilitas operasional perusahaan.
- Penurunan moral dan motivasi karyawan yang tersisa.

Manajer HR menyadari pentingnya memahami penyebab attrition ini secara lebih mendalam agar dapat melakukan tindakan preventif yang tepat.

## Permasalahan Bisnis

Berikut beberapa permasalahan bisnis yang dihadapi:

1. **Mengapa attrition rate karyawan sangat tinggi?**  
   Perusahaan belum memiliki pemahaman menyeluruh tentang faktor-faktor yang memengaruhi keputusan karyawan untuk keluar.

2. **Siapa saja karyawan yang berisiko tinggi mengalami attrition?**  
   HR kesulitan mengidentifikasi secara dini kelompok karyawan yang rawan keluar agar dapat dilakukan intervensi lebih awal.

3. **Bagaimana cara menyampaikan informasi attrition secara jelas dan real-time?**  
   Tidak tersedia dashboard atau sistem visualisasi yang komprehensif untuk mendukung pengambilan keputusan oleh tim HR.

## Cakupan Proyek

Untuk menjawab permasalahan tersebut, proyek ini akan mencakup hal-hal berikut:

- **Eksplorasi dan analisis data karyawan**  
  Memahami pola dan karakteristik dari data karyawan untuk menemukan faktor yang memengaruhi attrition.

- **Pembangunan model machine learning prediktif**  
  Menggunakan algoritma seperti Random Forest atau XGBoost untuk memprediksi potensi attrition berdasarkan atribut-atribut yang tersedia.

- **Visualisasi data dan pembuatan dashboard interaktif**  
  Menyediakan dashboard berbasis Streamlit yang memungkinkan HR melihat statistik, insight penting, serta memprediksi kemungkinan attrition secara interaktif.

- **Rekomendasi strategis berbasis data**  
  Memberikan insight dan rekomendasi kebijakan untuk menekan angka attrition dan meningkatkan retensi karyawan.

  ## Data Understanding

Dataset yang digunakan merupakan data fiktif dari perusahaan Jaya Jaya Maju, yang berisi informasi demografis dan pekerjaan karyawan. Dataset ini mencakup berbagai variabel yang dapat memengaruhi attrition karyawan, di antaranya:

- **Demografis:** Age, Gender, Education, MaritalStatus.
- **Pekerjaan:** Department, JobRole, JobLevel, MonthlyIncome, OverTime, YearsAtCompany, DistanceFromHome.
- **Kepuasan & Keterlibatan:** JobSatisfaction, EnvironmentSatisfaction, RelationshipSatisfaction, JobInvolvement.
- **Pelatihan & Kinerja:** TrainingTimesLastYear, PerformanceRating, YearsSinceLastPromotion.

### Temuan Awal (EDA)

- Karyawan dengan **OverTime = Yes** memiliki tingkat attrition jauh lebih tinggi.
- Attrition lebih banyak terjadi pada **karyawan muda (<30 tahun)**.
- Faktor-faktor seperti **JobSatisfaction rendah**, **DistanceFromHome jauh**, dan **YearsAtCompany sedikit** berkorelasi positif terhadap kemungkinan attrition.
- Variabel numerik dengan korelasi kuat terhadap attrition antara lain: `OverTime`, `MonthlyIncome`, dan `YearsWithCurrManager`.

---

## Data Preparation

Langkah-langkah yang dilakukan:

1. **Pembersihan Data**
   - Tidak ditemukan nilai null atau duplikat.
   - Outlier dicek dan ditangani jika diperlukan.

2. **Encoding Kategorikal**
   - One-Hot Encoding untuk kolom seperti `BusinessTravel`, `Department`, `EducationField`, dan `JobRole`.

3. **Feature Engineering**
   - Membuat variabel tambahan jika dibutuhkan seperti `TenureGroup` atau `IncomePerYear`.

4. **Splitting Data**
   - Data dibagi menjadi train dan test set dengan rasio 80:20 menggunakan stratifikasi pada target (`Attrition`).

---

## Modeling

Tiga algoritma digunakan untuk membandingkan performa model:

1. **Logistic Regression**
2. **Random Forest Classifier**
3. **XGBoost Classifier**

### Hasil Model
- **Random Forest** memberikan performa terbaik dengan akurasi ~87%.
- Fitur paling penting:
  - `OverTime`
  - `JobSatisfaction`
  - `DistanceFromHome`
  - `YearsAtCompany`

---

## Evaluation

Model dievaluasi menggunakan beberapa metrik:

- **Accuracy**
- **Precision**
- **Recall**
- **F1-Score**
- **Confusion Matrix**

### Validasi
- Menggunakan **k-fold cross-validation** untuk mengevaluasi generalisasi model.
- Hasil konsisten antara train dan test menunjukkan tidak ada overfitting.

---

## Deployment

Untuk memudahkan tim HR menggunakan hasil analisis ini, dibuat sebuah **dashboard interaktif** menggunakan **Streamlit**.

### Fitur Dashboard:
- **Prediksi attrition karyawan baru** berdasarkan input atribut.
- **Statistik attrition** berdasarkan kategori (umur, role, overtime, dll).
- **Segmentasi** karyawan berdasarkan risiko keluar.

📍 Link lokal dashboard: `http://localhost:8501`

---

## Kesimpulan dan Rekomendasi

### Kesimpulan:
- Model berhasil memprediksi karyawan yang berisiko keluar dengan akurasi tinggi.
- Faktor-faktor utama penyebab attrition telah teridentifikasi dengan baik.

### Rekomendasi:
1. **Kurangi beban lembur berlebihan**, karena sangat terkait dengan attrition.
2. **Lakukan survei berkala** untuk mengukur JobSatisfaction dan mengambil langkah cepat bila rendah.
3. **Integrasikan model prediksi** ke sistem HRIS untuk membantu identifikasi dini.
4. **Lakukan pelatihan manajemen** untuk menangani karyawan berisiko tinggi keluar.

