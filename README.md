CNN untuk Klasifikasi CIFAR-10
Kode ini merupakan implementasi sederhana dari model Convolutional Neural Network (CNN) yang digunakan untuk melakukan klasifikasi pada dataset CIFAR-10. Dataset ini terdiri dari 60.000 gambar berukuran 32x32 piksel yang terbagi ke dalam 10 kelas, seperti pesawat (airplane), mobil (automobile), burung (bird), dan lainnya.

Penjelasan Singkat Kode
Memuat Dataset CIFAR-10
Dataset CIFAR-10 dimuat menggunakan fungsi bawaan TensorFlow. Gambar dalam dataset dinormalisasi ke rentang [0,1], dan labelnya diubah keto_categorical agar sesuai dengan kebutuhan model.

Arsitektur Model CNN
Model dibangun menggunakan API Sequential dari TensorFlow. Arsitektur model terdiri dari:

Tiga Lapisan Konvolusi dengan fungsi aktivasi ReLU, masing-masing diikuti oleh lapisan MaxPooling untuk mengurangi dimensi data.
Lapisan Flatten untuk mengubah keluaran dari format matriks menjadi vektor.
Dense Layer dengan 128 neuron dan Dropout sebesar 50% untuk mengurangi overfitting.
Output Layer dengan fungsi aktivasi softmax untuk klasifikasi 10 kelas.
Kompilasi dan Pelatihan Model
Model dikompilasi menggunakan optimasi Adam, fungsi loss categorical crossentropy, dan metrik akurasi. Pelatihan dilakukan selama 10 epoch dengan ukuran batch 64, menggunakan data uji sebagai data validasi.

Evaluasi dan Prediksi
Setelah pelatihan, model dievaluasi pada data uji untuk menghitung akurasi. Kode juga menyediakan fungsi untuk memuat gambar baru, memprosesnya agar sesuai dengan format input model, dan memprediksi kelasnya. Nama-nama kelas dari dataset CIFAR-10 digunakan untuk menampilkan hasil prediksi secara lebih informatif.

Integrasi dengan Google Colab
Kode memanfaatkan fungsi bawaan Colab untuk mengunggah gambar baru dan memprosesnya menggunakan model terlatih. Hal ini mempermudah pengujian model dengan data di luar dataset CIFAR-10.

Kesimpulan
Kode ini adalah implementasi dasar CNN untuk klasifikasi gambar yang cocok untuk pembelajaran awal. Struktur model sederhana namun efektif dalam memahami konsep dasar convolutional neural networks. Dengan sedikit modifikasi, kode ini dapat disesuaikan untuk dataset lain atau pengujian lebih lanjut.

Kode ini berasal dari sumber: https://modul-praktikum-ai.vercel.app/Materi/4-convolutional-neural-network
