Pembahasan pada Perancangan Proses/Algoritma:
- **Dataset citra kerusakan jalan**  
    “Input saya berupa foto kerusakan jalan yang sudah berlabel 9 kelas (jenis×tingkat).”
    
- **Preprocessing (Resize + Normalisasi)**  
    “Resize 224×224 karena VGG19 standar inputnya 224. Normalisasi biar distribusi pixel stabil dan training lebih cepat konvergen.”
    
- **Validation Data itu dipakai kapan?**  
    “Validation dipakai _selama training_ buat memantau performa. Kalau train naik tapi val turun → indikasi overfitting, jadi saya pakai sebagai acuan early stopping/penyetelan parameter.”
    
- **Training Data → Augmentasi**  
    “Augmentasi hanya di training supaya model tidak ‘hafal’ data—tujuannya supaya robust di variasi cahaya/sudut.”
    
- **Model CNN VGG19 + Transfer Learning → Pelatihan Model**  
    “Saya pakai transfer learning karena dataset lokal terbatas; backbone VGG19 menangkap fitur tekstur/pola kerusakan, lalu layer akhir saya sesuaikan untuk output 9 kelas.”
    
- **Testing Data → Evaluasi Model → Output Klasifikasi**  
    “Testing itu benar-benar data yang tidak dilihat saat training. Hasilnya dievaluasi pakai confusion matrix dan metrik multi-kelas, lalu output akhirnya adalah kelas prediksi (jenis+severity).”