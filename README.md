# Analisis Dataset: Sleep Health and Lifestyle

Repositori ini berisi proyek analisis dan visualisasi data menggunakan dataset *Sleep Health and Lifestyle*. Proyek ini disusun untuk memenuhi tugas Ujian Tengah Semester (UTS) mata kuliah Analisis dan Visualisasi Data.

**Penulis:** Zafira Ryani Putri  
**NIM:** J0403241139  
**Kelas:** TPL 61 B/P2  

## Deskripsi Proyek
Analisis ini berfokus pada metrik kesehatan dan kebiasaan sehari-hari untuk melihat dampaknya terhadap kualitas tidur seseorang. Dataset terdiri dari 374 responden dengan 13 atribut, mencakup metrik seperti durasi tidur, tingkat stres, aktivitas fisik, detak jantung, hingga gangguan tidur (seperti *Insomnia* atau *Sleep Apnea*).

## Alur Analisis (Data Pipeline)

Proyek ini mencakup beberapa tahapan pra-pemrosesan dan analisis data:

1. **Pengumpulan Data:** Memuat dataset dari sumber eksternal (GitHub raw file) ke dalam DataFrame Pandas.
2. **Penelaahan Data (EDA):** 
   - Pengecekan tipe data, struktur kolom, dan ringkasan statistik.
   - Visualisasi distribusi *Quality of Sleep*.
   - Analisis hubungan antara *Stress Level* dan *Quality of Sleep* menggunakan *boxplot*.
3. **Validasi Data:** Memastikan tidak ada duplikasi data atau nilai yang tidak logis (misalnya: durasi tidur negatif atau melebihi 24 jam).
4. **Penentuan Objek Data:** Menghapus fitur yang tidak relevan untuk pemodelan (kolom `Person ID`).
5. **Pembersihan Data:** Menangani *missing values* pada kolom `Sleep Disorder` (219 baris kosong) dengan melakukan imputasi menggunakan nilai `'None'`.
6. **Konstruksi Data (Feature Engineering & Encoding):**
   - Memecah kolom `Blood Pressure` menjadi dua fitur numerik terpisah: `Systolic` dan `Diastolic`.
   - Melakukan *Label Encoding* pada variabel kategorikal (`Gender`, `Occupation`, `BMI Category`, dan `Sleep Disorder`) menggunakan `scikit-learn` agar siap digunakan untuk pemodelan *Machine Learning*.

## Temuan Menarik
* Mayoritas responden memiliki kualitas tidur yang cukup baik (skor 6 hingga 9).
* Terdapat korelasi negatif antara tingkat stres dan kualitas tidur: individu dengan tingkat stres rendah (skor 3–4) cenderung memiliki kualitas tidur yang tinggi, sedangkan tingkat stres tinggi menyebabkan penurunan dan variasi pada kualitas tidur.
* Terdapat korelasi linear antara tekanan darah *Systolic* dan *Diastolic*. Individu tanpa gangguan tidur (None) cenderung memiliki tekanan darah yang lebih rendah/normal dibandingkan dengan mereka yang mengidap *Sleep Apnea*.

## Cara Menjalankan Proyek

1. *Clone* repositori ini ke dalam mesin lokal Anda:
   ```bash
   git clone [https://github.com/Lehonci/dataset-uts-anavida.git](https://github.com/Lehonci/dataset-uts-anavida.git)
