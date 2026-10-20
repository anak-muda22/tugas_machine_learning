# UTS Machine Learning: Linear Regression & Logistic Regression

**Nama:** Muhamad Fatir  
**NIM:** 241011402714  
**Kelas:** 05 TPLM 005 / Reg B

## Deskripsi
Tugas menerapkan Linear Regression untuk memperkirakan penjualan dari biaya iklan dan Logistic Regression untuk klasifikasi email spam. Notebook mencakup visualisasi, pembagian data, evaluasi, eksperimen learning rate dan threshold, jawaban konsep, prediksi contoh, serta perbandingan bonus dengan scikit-learn.

Implementasi model dan metrik pada bagian utama dibuat dengan NumPy. scikit-learn hanya dipakai untuk eksperimen bonus. `RANDOM_STATE = 14`, yaitu dua digit terakhir NIM.

## Struktur File
```text
.
├── README.md
├── tugas_UTS.ipynb
├── Ads_Data.csv
└── Email_Data.csv
```

Kedua CSV harus berada di direktori yang sama dengan notebook. Notebook juga mencari file tersebut di direktori induk, tanpa bergantung pada path lokal tertentu.

## Dependensi dan Cara Menjalankan
Gunakan Python dan instal dependensi berikut:
```bash
python -m pip install numpy pandas matplotlib scikit-learn jupyter
```

Buka `tugas_UTS.ipynb` di Jupyter atau VS Code, pilih kernel Python yang sudah memiliki dependensi tersebut, lalu jalankan **Run All** dari awal. scikit-learn diperlukan untuk sel bonus.

## Ringkasan Hasil Eksekusi
Angka berikut berasal dari eksekusi notebook dengan dua CSV yang disertakan, seed 14, split regresi 80/20 dan split klasifikasi 75/25.

- Data: 40 observasi iklan dan 60 email.
- Linear Regression NumPy: `y_hat = 29.145637 + 8.855992 * BiayaIklan`.
- Evaluasi regresi: RMSE train `6.3366`, R² train `0.9253`; RMSE test `4.7507`, R² test `0.9728`.
- Gradient Descent (5.000 iterasi): learning rate `0.001` selesai tetapi lebih lambat; `0.02` mencapai solusi Normal Equation; `0.1` divergen dan dihentikan aman pada iterasi 141, dengan kegagalan tetap ditampilkan.
- Logistic Regression NumPy (threshold 0.5): accuracy `0.9333`, precision `0.8889`, recall `1.0000`, F1 `0.9412`; confusion matrix `[[TN=6, FP=1], [FN=0, TP=8]]`.
- Threshold `0.3`, `0.5`, dan `0.7` kebetulan memberi metrik sama pada test split ini. Threshold awal tetap `0.5` karena tidak tersedia biaya kesalahan atau validation set untuk memilih threshold lain.
- Pada bonus, Linear Regression NumPy dan scikit-learn memberikan hasil yang sama pada split ini. Koefisien Logistic Regression berbeda karena scikit-learn memakai regularisasi L2 secara default (`C=1.0`); metrik test keduanya kebetulan sama.

Hasil merujuk pada split dan konfigurasi di notebook; performa test dari satu split bukan jaminan kinerja pada data lain.
