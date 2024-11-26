# 2D-data-image-processing
Deskripsi Dataset
•	Nama Dataset: Fashion-MNIST.

•	Ukuran: 70.000 gambar.

o	Training Set: 60.000 gambar.

o	Testing Set: 10.000 gambar.

•	Dimensi Gambar: 28x28 pixel dalam skala grayscale (grayscale intensity dari 0 hingga 255).

•	Kelas (10 kategori):

o	T-shirt/top

o	Trouser

o	Pullover

o	Dress

o	Coat

o	Sandal

o	Shirt

o	Sneaker

o	Bag

o	Ankle boot

Alasan Pemilihan Dataset
1.	Kemiripan dengan Dunia Nyata:
o	Dataset Fashion-MNIST adalah dataset standar untuk klasifikasi gambar item fashion.
o	Dataset ini merepresentasikan tantangan sederhana namun relevan di dunia nyata.
2.	Kesederhanaan:
o	Dengan gambar berukuran kecil (28x28), dataset ini mudah diproses oleh model deep learning tanpa memerlukan banyak sumber daya.
3.	Tersedia Secara Luas:
o	Dataset ini mudah diakses langsung melalui pustaka tensorflow, tanpa perlu pengunduhan manual.
4.	Cocok untuk Eksperimen:
o	Dataset sering digunakan untuk menguji model deep learning karena strukturnya yang seragam dan terstandar.

Alasan Pemilihan Metode
1.	Menggunakan Convolutional Neural Networks (CNN):
•	CNN adalah metode terbaik untuk klasifikasi gambar karena mampu mengekstrak fitur visual seperti tepi, pola, dan bentuk.
•	Lapisan konvolusi menangkap fitur lokal dari gambar, sedangkan lapisan pooling mengurangi dimensi untuk efisiensi.
2.	Regularisasi dan Dropout:
•	Regularisasi L2: Menambahkan penalti pada bobot besar untuk mengurangi kompleksitas model.
•	Dropout: Mengabaikan beberapa neuron secara acak selama pelatihan, membantu mengurangi overfitting.
3.	Optimasi dengan Adam dan Learning Rate Scheduling:
•	Adam Optimizer: Cepat dan stabil, cocok untuk dataset seperti ini.
•	Learning Rate Scheduling: Mempercepat konvergensi dan menghindari stagnasi pada pelatihan.

Tahapan dan Hasil
Tahap 1: Memuat Dataset
•	Dataset Fashion-MNIST digunakan:
o	60.000 gambar pelatihan.
o	10.000 gambar pengujian.
•	Gambar memiliki resolusi 28x28 piksel dalam grayscale.
•	Dataset dibagi menjadi data pelatihan (80%) dan data validasi (20%).
•	Hasil Visualisasi Data: Contoh gambar dataset:
o	Label: T-shirt/top, Trouser, Pullover, dll.

Tahap 2: Preprocessing Data
Langkah:
1.	Normalisasi: Piksel gambar dinormalisasi ke skala [0, 1].
2.	Reshaping: Bentuk gambar diubah menjadi (28, 28, 1) agar kompatibel dengan CNN.

Alasan dilakukan :
1.	Normalisasi membantu mempercepat pelatihan dan meningkatkan stabilitas model.
2.	Reshaping memastikan gambar dapat diproses oleh lapisan konvolusi CNN.

Tahap 3: Membuat Model CNN
•	Arsitektur Model:
1.	Lapisan Konvolusi dan Pooling: Untuk mengekstrak fitur visual.
2.	Dropout: Untuk mencegah overfitting.
3.	Lapisan Fully Connected: Untuk memprediksi kelas gambar.
•	Kompilasi Model:
o	Optimizer: Adam (cepat dan stabil).
o	Loss Function: Sparse Categorical Crossentropy (untuk klasifikasi multi-kelas).
•	Alasan Pemilihan Metode:
o	CNN dipilih karena kemampuannya dalam menangani data gambar.
o	Dropout digunakan untuk mengurangi overfitting, terutama pada dataset kecil.

Tahap 4: Melatih Model
•	Early Stopping: Digunakan untuk menghentikan pelatihan jika validation loss tidak membaik selama 5 epoch.
•	Hasil Pelatihan:
o	Training Accuracy: 93.5%
o	Validation Accuracy: 91.2%

Tahap 5: Evaluasi Model
•	Hasil Evaluasi pada Data Pengujian:
o	Accuracy: 92.8%
o	Confusion Matrix: Digunakan untuk menganalisis performa model pada setiap kelas.
o	Precision, Recall, dan F1-Score:
 
o	Rata-rata Akurasi per Kelas: ~92%


Tahap 6: Menyimpan dan Memuat Model
•	Model disimpan dalam format .h5 untuk mempermudah penggunaan ulang tanpa perlu pelatihan ulang.
•	Model berhasil dimuat kembali dan diuji ulang dengan hasil yang sama seperti sebelumnya.

Tahap 7: Fine-Tuning Model
Langkah:
1.	Menambahkan regularisasi L2 untuk mencegah overfitting.
2.	Menggunakan learning rate scheduling untuk mempercepat konvergensi.

Hasil:
•	Akurasi Pengujian: 93.1%
•	Validation Accuracy meningkat dibandingkan sebelumnya.


Tahap 8: Uji Coba dengan Data Asli dan Palsu
1.	Data Asli: Gambar dari dataset pengujian diuji, menghasilkan prediksi yang akurat.
2.	Data Palsu: Gambar acak dihasilkan, model tetap memberikan prediksi meskipun datanya tidak bermakna.

Kesimpulan:
•	Model bekerja sangat baik pada data asli tetapi tidak memiliki mekanisme untuk mendeteksi data palsu.
•	Hal ini menunjukkan pentingnya menambahkan metode validasi input untuk aplikasi nyata.

Kesimpulan Akhir
1.	Akurasi Akhir: Model mencapai akurasi 93.1% pada data pengujian.
2.	Evaluasi Performa:
a.	Precision: Rata-rata ~92%
b.	Recall: Rata-rata ~92%
c.	F1-Score: Rata-rata ~92%
3.	Kelebihan:
a.	Model stabil dan mampu generalisasi dengan baik.
b.	Overfitting diminimalkan dengan teknik regularisasi.
 
