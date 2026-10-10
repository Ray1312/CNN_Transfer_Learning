# Advanced CNNs and Transfer Learning -> Oxford-IIIT Pet

Proyek percobaan Deep Learning untuk membandingkan pelatihan CNN dari awal, transfer learning, fine-tuning, data augmentation, dan arsitektur pembanding pada klasifikasi 10 ras kucing dan anjing dari dataset Oxford-IIIT Pet.

# Percobaan

- B1: ResNet-18 dilatih dari awal (from scratch).
- B2: ResNet-18 pretrained ImageNet dengan feature extraction (backbone dibekukan).
- B3: ResNet-18 pretrained dengan fine-tuning layer4 dan fc.
- B4: Perbandingan feature extraction tanpa dan dengan data augmentation.
- B5: MobileNetV3-Small pretrained sebagai arsitektur pembanding.

Data yang dipakai berjumlah 1.977 gambar dari 10 kelas, dengan pembagian stratified: 1.383 training, 297 validation, dan 297 testing. Seed yang digunakan adalah 42.

# Hasil utama

| Eksperimen | Test Macro F1 
| B1 -> From Scratch | 0,5134 |
| B2 -> Feature Extraction | 0,9596 |
| B3 -> Fine-Tuning | 0,9593 |
| B4 -> Tanpa Augmentasi | 0,9630 |
| B4 -> Dengan Augmentasi | 0,9628 |
| B5 -> MobileNetV3-Small | 0,9628 |

# Cara menjalankan

1. Gunakan Python dan Jupyter Notebook / Google Colab.
2. Instal dependensi jika diperlukan:
   pip install -r requirements.txt
3. Buka notebook DeepLearning.ipynb.
4. Jalankan sel secara berurutan. Dataset Oxford-IIIT Pet dan bobot pretrained akan diunduh secara otomatis jika belum tersedia. Koneksi internet diperlukan saat pengunduhan pertama.
5. Hasil evaluasi dan log pelatihan disimpan ke file CSV melalui sel notebook.

# Output

- File CSV riwayat training dan ringkasan eksperimen B1–B5.
- experiment_summary.csv — ringkasan metrik semua eksperimen.
- B4_failure_analysis.csv — contoh kesalahan prediksi model B4 dengan augmentasi.
- Grafik training/validation loss dan analisis pada notebook serta laporan PDF terpisah.
