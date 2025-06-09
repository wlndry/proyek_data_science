# Proyek Pertama: Menyelesaikan Permasalahan Departemen Human Resources

## Business Understanding

Jaya Jaya Maju adalah perusahaan multinasional yang berdiri sejak tahun 2000 dengan lebih dari 1000 karyawan. Saat ini, perusahaan menghadapi masalah tingginya tingkat attrition (rasio karyawan keluar) yang telah melebihi 10%. 

Tingginya attrition ini berdampak pada:
- Biaya rekrutmen yang meningkat.
- Penurunan produktivitas.
- Terganggunya stabilitas tim dan kualitas layanan.

Departemen HR meminta bantuan untuk:
- Mengidentifikasi faktor-faktor yang memengaruhi attrition.
- Membangun dashboard pemantauan attrition dan faktor terkait.

### Pertanyaan Kunci:
1. Seberapa tinggi tingkat attrition di perusahaan saat ini?
2. Siapa saja karyawan yang berisiko tinggi untuk keluar?
3. Faktor apa yang paling berpengaruh terhadap attrition?
4. Bagaimana peran lembur, jarak rumah, dan kepuasan kerja terhadap attrition?
5. Bagaimana visualisasi data dapat membantu pengambilan keputusan oleh tim HR?

### Objektif Bisnis:
- Mengurangi tingkat attrition karyawan.
- Meningkatkan efektivitas strategi retensi SDM.

### Objektif Teknis:
- Melakukan eksplorasi data karyawan.
- Membangun dashboard visualisasi yang informatif dan mudah digunakan.
- (Opsional) Membangun model prediksi risiko attrition.

---

## Data Understanding

Dataset disediakan oleh tim HR Jaya Jaya Maju dan mencakup:
- **Demografi**: Age, Gender, MaritalStatus, Education, EducationField.
- **Pekerjaan**: Department, JobRole, JobLevel, MonthlyIncome, OverTime, YearsAtCompany.
- **Target**: Attrition (0 = No, 1 = Yes).

### Atribut Utama:
- `Attrition`: Target variabel
- `OverTime`: Lembur (Yes/No)
- `JobSatisfaction`, `EnvironmentSatisfaction`, `RelationshipSatisfaction`: Skala 1–4
- `YearsAtCompany`, `DistanceFromHome`, `NumCompaniesWorked`, dll.

---

## Data Preparation

Langkah-langkah yang dilakukan:
- Menghapus duplikasi dan data kosong (NaN).
- Encoding data kategorikal (Label/One-Hot Encoding).
- Standarisasi/normalisasi data numerik (jika dibutuhkan).
- Membuat kolom baru jika relevan (feature engineering).
- (Opsional) Split data 80:20 untuk modeling prediktif.

---

## Exploratory Data Analysis (EDA)

### Tujuan:
- Mengidentifikasi pola umum karyawan yang keluar.
- Menemukan fitur penting untuk dashboard dan insight bisnis.

### Temuan Awal (Contoh):
- Karyawan muda (usia < 30) lebih cenderung keluar.
- Karyawan yang lembur memiliki attrition rate lebih tinggi.
- Kepuasan kerja rendah dan jarak rumah jauh juga berkorelasi dengan attrition.

Visualisasi yang digunakan:
- Bar chart untuk distribusi attrition berdasarkan fitur.
- Heatmap korelasi antar fitur numerik.
- Pie chart proporsi attrition.

---

## Modeling (Opsional)

Jika ingin menambahkan prediksi risiko attrition:

### Algoritma yang Dicoba:
- Logistic Regression
- Random Forest
- XGBoost

### Evaluasi:
- Akurasi, Precision, Recall, F1-Score, Confusion Matrix
- Cross-validation untuk validasi model

### Hasil:
- Random Forest memberikan akurasi terbaik (~87%).
- Fitur paling penting: `OverTime`, `JobSatisfaction`, `DistanceFromHome`.

---

## Dashboard Development

### Tools:
- **Streamlit** untuk dashboard interaktif.
- **Pandas, Matplotlib, Seaborn** untuk manipulasi dan visualisasi data.

### Fitur Utama Dashboard:
1. **Ringkasan Attrition**: Total karyawan, jumlah dan persentase attrition.
2. **Filter Interaktif**: Filter berdasarkan usia, jabatan, departemen, dan lembur.
3. **Visualisasi Dinamis**:
   - Distribusi attrition berdasarkan departemen, usia, job level.
   - Korelasi antara attrition dengan Job Satisfaction, OverTime, DistanceFromHome.
4. **Insight Otomatis**: Highlight fitur yang paling memengaruhi attrition.
5. **(Opsional)**: Halaman prediksi risiko berdasarkan input karyawan.

---

## Evaluation

- Evaluasi keberhasilan dashboard dilihat dari:
  - Keterbacaan dan interaktivitas dashboard.
  - Kemampuan memberikan insight yang jelas bagi manajer HR.
  - (Opsional) Kinerja model prediktif jika digunakan.

---

## Deployment

- Dashboard di-deploy secara lokal menggunakan Streamlit.
- Akses lokal: [http://localhost:8501](http://localhost:8501)
- Struktur folder:


---

## Conclusion

- Attrition di Jaya Jaya Maju dipengaruhi oleh beberapa faktor seperti lembur, kepuasan kerja, dan jarak rumah.
- Dashboard yang dibangun mampu membantu HR dalam:
- Memantau attrition secara real time.
- Mengambil keputusan berbasis data untuk intervensi dini.
- (Opsional) Model prediksi dapat membantu HR mengenali karyawan berisiko tinggi.

---

## Rekomendasi Action Items

1. Lakukan survei rutin untuk mengukur Job Satisfaction dan Work-Life Balance.
2. Evaluasi kembali beban lembur karyawan di berbagai divisi.
3. Integrasikan dashboard ke sistem HRIS internal untuk pemantauan berkelanjutan.
4. Lakukan program retensi untuk kelompok usia dan jabatan dengan risiko attrition tinggi.
