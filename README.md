# 🧠 Deteksi Down Syndrome Berdasarkan Wajah (Region Asia)

## Implementasi Transfer Learning dengan Arsitektur VGG16 & VGG19

**Penulis:** Tarissa Rizky Salsabiila Uwar & Christian Sri Kusuma Aditya
**Jurnal:** Building of Informatics, Technology and Science (BITS), Vol. 7 No. 1, 2025
**DOI:** [10.47065/bits.v7i1.7150](https://ejurnal.seminar-id.com/index.php/bits/article/view/7150)

---

## 📋 Deskripsi Proyek

Proyek ini merupakan implementasi *transfer learning* dengan arsitektur **VGG16** dan **VGG19** untuk mendeteksi *Down Syndrome* berdasarkan citra wajah anak-anak dari region **Asia**.
Tujuannya adalah untuk membantu proses deteksi dini Down Syndrome melalui analisis fitur wajah menggunakan pendekatan **Convolutional Neural Network (CNN)**.

Metode *transfer learning* digunakan agar model dapat memanfaatkan bobot hasil pelatihan di dataset besar (*ImageNet*) dan menyesuaikan pada domain wajah Down Syndrome.
Selain itu, dilakukan **augmentasi data** guna memperluas variasi citra dan mengurangi *overfitting*.

---

## 🧬 Arsitektur yang Digunakan

Model utama yang digunakan adalah dua varian arsitektur CNN populer:

* **VGG16**
* **VGG19**

Keduanya digunakan dalam dua kondisi:

1. **ORI (Original):** tanpa augmentasi data
2. **AUG (Augmented):** menggunakan augmentasi seperti rotasi, flipping, dan zoom

Notebook yang digunakan:

* `ORI_ASIA_VGG16_(FIX).ipynb`
* `AUG_ASIA_VGG16_(FIX).ipynb`
* `ORI_ASIA_VGG19_(FIX).ipynb`
* `AUG_ASIA_VGG19_(FIX).ipynb`

---

## 📊 Dataset & Preprocessing

* Dataset terdiri dari dua kelas:

  * **Down Syndrome**
  * **Healthy (Sehat)**
* Dataset difokuskan pada **region Asia**
* Langkah preprocessing yang diterapkan langsung di dalam notebook:

  * Resize citra ke ukuran input model (224x224)
  * Normalisasi nilai piksel (0–1)
  * Split data ke *training* dan *validation*
  * Augmentasi (untuk versi AUG)

Semua tahap preprocessing sudah otomatis dijalankan di dalam kode.

---

## 🧩 Cara Menjalankan

Seluruh proses — mulai dari import library, loading dataset, augmentasi, hingga evaluasi — **sudah terintegrasi langsung di dalam notebook**.
Tidak diperlukan file tambahan seperti `requirements.txt` atau folder `utils/`, karena semuanya sudah tersedia di dalam kode.

### Langkah-langkah Menjalankan:

1. **Buka notebook di Google Colab atau VSCode.**
2. Pilih salah satu file `.ipynb`:

   * `ORI_ASIA_VGG16_(FIX).ipynb`
   * `AUG_ASIA_VGG16_(FIX).ipynb`
   * `ORI_ASIA_VGG19_(FIX).ipynb`
   * `AUG_ASIA_VGG19_(FIX).ipynb`
3. Jalankan semua sel **secara berurutan dari atas ke bawah.**
4. Notebook akan:

   * Import semua library yang dibutuhkan
   * Mengambil dataset dari Google Drive
   * Melakukan augmentasi dan preprocessing
   * Membangun dan melatih model CNN (VGG16/VGG19)
   * Menampilkan hasil training, akurasi, loss, dan confusion matrix

### Hasil akan muncul langsung di notebook, meliputi:

* Grafik *training vs validation accuracy/loss*
* Nilai akurasi validasi terbaik
* Confusion matrix dan visualisasi hasil prediksi

💡 *Catatan:*
Cukup jalankan di lingkungan yang sudah memiliki TensorFlow (misalnya Google Colab).
Tidak perlu setup environment tambahan.

---

## 📈 Hasil dan Analisis

| Arsitektur | Augmentasi | Akurasi Validasi   | Catatan                          |
| ---------- | ---------- | ------------------ | -------------------------------- |
| VGG16      | ❌          | ~91%               | Model dasar, tanpa augmentasi    |
| VGG16      | ✅          | ~92%               | Lebih stabil dengan augmentasi   |
| VGG19      | ❌          | ~92%               | Spesifisitas baik                |
| **VGG19**  | ✅          | **~93% (terbaik)** | Performa tertinggi, error rendah |

📍 **Kesimpulan utama:**
Model **VGG19 dengan augmentasi data** menghasilkan performa terbaik untuk klasifikasi citra Down Syndrome pada region Asia, dengan tingkat akurasi validasi sekitar **93%**.

---

## 🔍 Kesimpulan Penelitian

* Penerapan *transfer learning* dengan VGG sangat efektif untuk tugas klasifikasi medis berbasis wajah.
* Augmentasi data terbukti meningkatkan stabilitas model dan mengurangi *overfitting*.
* Model VGG19 lebih unggul dibanding VGG16 dalam hal akurasi dan spesifisitas.

Saran pengembangan:

* Menambah variasi dataset Asia agar hasil lebih general.
* Menerapkan arsitektur lebih modern seperti ResNet, EfficientNet, atau MobileNet.
* Mengintegrasikan model ke aplikasi berbasis web atau mobile untuk deteksi otomatis.

---
