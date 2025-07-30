# OCR Plat Nomor Kendaraan dengan Visual Languange Model (llava-v1.5-7b-llamafile)
Project ini meenggunakan Sistem Character Recognition (OCR) dapat membaca plat nomor kendaraan dengan menggunakan model llava-v1.5-7b-llamafile, dijalankan datasheet secara lokal dengan LM Studio. Model ini menggunakan prompt untuk mengenali tulisan dari gambar plat.

# Struktur Folder Proyek
- aas_computervision (Folder utama)
- test (folder berisi datasheet gambar)
- generate_gt.py (code untuk generate ground_truth)
- ground_truth.csv (File CSV ground_truth)
- ocr_main.py (code koneksi visual studio code dan lm studio)
- results.csv (File CSV dari hasil image,	ground_truth,	prediction,	CER_score)

# Tools yang digunakan
- LM Studio 0.3.20
- Visual Studio Code

# Setup LM Studio
1. Masuk ke menu developer LM Studio
2. Select mode to load Model misal nya llava-v1.5-7b-llamafile
3. Status pilih ke Running
4. lalu cari di browser http://localhost:1234/v1/models
5. jika hasil nya seperti ini maka LM Studio berhasil di setup
{
  "data": [
    {
      "id": "llava-v1.5-7b-llamafile",
      "object": "model",
      "owned_by": "organization_owner"
    },
    {
      "id": "text-embedding-nomic-embed-text-v1.5",
      "object": "model",
      "owned_by": "organization_owner"
    }
  ],
  "object": "list"
} 

# Cara  Menjalankan 
1. Masuk ke menu developer LM Studio
2. Select model to load yaitu llava-v1.5-7b-llamafile
3. Status ubah ke Running
4. lalu buka Visual Studio Code jalankan program ocr_main.py
5. lalu tunggu hasil nya LM Studio mempredict datasheet kita gambar demi gambar, dan hasil nya disimpan di result.csv

# CER (Character Error Rate) adalah metrik yang menghitung seberapa banyak kesalahan karakter dalam hasil prediksi teks dibandingkan dengan teks asli (ground truth).
CER= Substitusi+Insert+Delete / Jumlah karakter ground truth 

​- Substitusi = karakter salah (misalnya B jadi 8)
- Insert = karakter tambahan yang seharusnya tidak ada
- Delete = karakter yang hilang

# Contoh Prediksi yang benar 
test015_1.jpg => GT: AD1798BT | Pred: AD1798 | CER: 0.25

# Contoh Prediksi yang salah
test011_2.jpg => GT: B9374RI | Pred: B9132 | CER: 0.714 



