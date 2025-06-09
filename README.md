# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding

Jaya Jaya Maju adalah perusahaan dengan lebih dari 1000 karyawan yang menghadapi tantangan tingginya **attrition rate** (karyawan yang keluar). Tingginya attrition ini berpotensi meningkatkan biaya rekrutmen, menurunkan produktivitas, dan mengganggu stabilitas operasional. Oleh karena itu, perusahaan ingin memahami faktor penyebab attrition dan melakukan prediksi agar dapat mengambil tindakan preventif.

## Permasalahan Bisnis

1. Mengapa tingkat attrition karyawan cukup tinggi?
2. Siapa saja karyawan yang berisiko tinggi mengalami attrition?
3. Bagaimana memprediksi attrition untuk membantu HR melakukan intervensi lebih awal?

## Cakupan Proyek

- Eksplorasi dan analisis data karyawan untuk memahami pola attrition.
- Pembersihan dan persiapan data dengan encoding dan scaling.
- Pembangunan model prediksi attrition menggunakan Logistic Regression.
- Evaluasi model dengan metrik classification report dan confusion matrix.
- Penyimpanan model dan fitur untuk keperluan deployment.

## Persiapan

### Sumber Data  
Dataset fiktif karyawan Jaya Jaya Maju dengan fitur demografis, pekerjaan, dan kepuasan kerja, termasuk kolom target `Attrition`.

### Setup Environment  
- Library: pandas, numpy, matplotlib, seaborn, sklearn, joblib, os
- Preprocessing: Label Encoding, StandardScaler
- Model: Logistic Regression (class_weight='balanced')
- Data splitting: train_test_split dengan stratify target

## Business Dashboard

Dalam proyek ini belum dibuat business dashboard interaktif. Model dan fitur telah disimpan untuk memungkinkan pengembangan dashboard di masa depan.

## Conclusion

Model Logistic Regression berhasil memprediksi attrition karyawan dengan performa memadai berdasarkan fitur yang tersedia. Faktor utama yang memengaruhi attrition dapat diidentifikasi melalui analisis fitur yang dilakukan.

## Rekomendasi Action Items (Optional)

- Kurangi beban lembur berlebihan yang berhubungan dengan attrition tinggi.
- Monitor kepuasan kerja karyawan secara berkala untuk mencegah attrition.
- Gunakan model prediksi untuk mengidentifikasi dan melakukan intervensi pada karyawan berisiko tinggi keluar.
