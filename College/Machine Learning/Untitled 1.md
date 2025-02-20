Arsitektur Jaringan

Arsitektur jaringan dalam **Jaringan Syaraf Tiruan (JST)** ada beberapa jenis, tergantung cara neuron-neuronnya dihubungkan dan bagaimana data mengalir. Berikut arsitektur utamanya:

### **1. Perceptron (Single Layer Perceptron - SLP)**

- **Terdiri dari:** Input layer → Output layer.
- **Cocok untuk:** Klasifikasi sederhana (linear separable).
- **Contoh:** Membedakan email spam dan non-spam.

### **2. Multi-Layer Perceptron (MLP)**

- **Terdiri dari:** Input layer → Hidden layer (1 atau lebih) → Output layer.
- **Cocok untuk:** Masalah yang lebih kompleks (non-linear separable).
- **Contoh:** Pengenalan tulisan tangan.

### **3. Convolutional Neural Network (CNN)**

- **Terdiri dari:** Layer konvolusi (feature extraction) → Pooling layer → Fully connected layer.
- **Cocok untuk:** Pengolahan gambar dan video.
- **Contoh:** Deteksi wajah, self-driving car.

### **4. Recurrent Neural Network (RNN)**

- **Terdiri dari:** Neuron dengan umpan balik (feedback loop).
- **Cocok untuk:** Data berurutan (teks, suara, time series).
- **Contoh:** Pengenalan suara, terjemahan bahasa.

### **5. Long Short-Term Memory (LSTM) & Gated Recurrent Unit (GRU)**

- **Varian RNN yang lebih canggih.**
- **Cocok untuk:** Prediksi jangka panjang dalam data sekuensial.
- **Contoh:** Prediksi harga saham, chatbot AI.

### **6. Generative Adversarial Network (GAN)**

- **Terdiri dari:** Generator (membuat data baru) & Discriminator (mengevaluasi data).
- **Cocok untuk:** Pembuatan gambar, deepfake, peningkatan resolusi gambar.
- **Contoh:** AI yang bisa membuat wajah manusia yang tampak nyata.

### **7. Transformer**

- **Menggunakan mekanisme attention untuk memahami hubungan antar kata dalam teks.**
- **Cocok untuk:** Pemrosesan bahasa alami (NLP).
- **Contoh:** ChatGPT, Google Translate.

Jadi, pilihan arsitektur tergantung pada jenis data dan tugas yang mau diselesaikan. 😊