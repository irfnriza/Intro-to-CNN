# CNN untuk Klasifikasi CIFAR-10  

Proyek ini merupakan implementasi sederhana dari **Convolutional Neural Network (CNN)** untuk melakukan klasifikasi gambar pada dataset CIFAR-10. Dataset CIFAR-10 terdiri dari 60.000 gambar berukuran 32x32 piksel yang terbagi ke dalam 10 kelas, seperti pesawat (*airplane*), mobil (*automobile*), burung (*bird*), dan lainnya.

## Deskripsi Kode  

### 1. Memuat Dataset CIFAR-10  
Dataset CIFAR-10 dimuat menggunakan fungsi bawaan TensorFlow.  
- Gambar dinormalisasi ke rentang [0,1].  
- Label dikonversi ke format *one-hot encoding* menggunakan `to_categorical` agar kompatibel dengan model.  

### 2. Arsitektur Model  
Model CNN dibangun menggunakan API Sequential dari TensorFlow. Arsitekturnya terdiri dari:  
- **Tiga Lapisan Konvolusi**  
  Masing-masing menggunakan fungsi aktivasi ReLU, diikuti oleh lapisan *MaxPooling* untuk mengurangi dimensi data.  
- **Lapisan Flatten**  
  Mengubah keluaran matriks dari lapisan konvolusi menjadi format vektor.  
- **Lapisan Dense dengan Dropout**  
  Lapisan *fully connected* dengan 128 neuron dan dropout sebesar 50% untuk mengurangi overfitting.  
- **Lapisan Output**  
  Lapisan dengan fungsi aktivasi *softmax* untuk mengklasifikasikan gambar ke dalam 10 kelas.  

### 3. Kompilasi dan Pelatihan Model  
Model dikompilasi dengan:  
- **Optimizer:** Adam  
- **Loss Function:** *Categorical Crossentropy*  
- **Metrik:** Akurasi  

Pelatihan dilakukan selama 10 *epoch* dengan ukuran batch 64. Validasi dilakukan menggunakan dataset uji.

### 4. Evaluasi dan Prediksi  
Setelah pelatihan, model dievaluasi menggunakan data uji untuk menghitung akurasi.  
Kode juga menyediakan fungsi untuk:  
1. Memuat gambar baru.  
2. Memproses gambar agar sesuai dengan format input model.  
3. Memprediksi kelas gambar menggunakan model terlatih.  
Hasil prediksi ditampilkan dengan nama kelas, seperti pesawat (*airplane*), mobil (*automobile*), dll.

### 5. Integrasi dengan Google Colab  
Kode ini memanfaatkan fungsi bawaan Google Colab untuk mengunggah gambar baru dan memprosesnya. Hal ini mempermudah pengujian dengan gambar di luar dataset CIFAR-10.

## Hasil  
Model ini memberikan akurasi yang cukup baik mengingat arsitekturnya yang sederhana. Implementasi ini cocok sebagai langkah awal untuk mempelajari konsep dasar CNN.

## Contoh Output  
Contoh prediksi untuk gambar yang diunggah:  

```text
File: uploaded_image.jpg  
Predicted Class Index: 1  
Predicted Class Name: automobile  
