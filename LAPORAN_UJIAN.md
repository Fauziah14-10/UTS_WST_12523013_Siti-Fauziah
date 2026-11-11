# Laporan UTS Web Software Tools

**Nama: Siti Fauziah**
**Nomor Induk Mahasiswa: 12523013**
**Kelas: A**
**Tanggal: 11 November 2026**

## A. Bukti pemeriksaan masalah
| Masalah | Alat yang digunakan | Bukti pemeriksaan | Perkiraan penyebab | Perbaikan | Hasil setelah perbaikan |
|---|---|---|---|---|---|
| Produk | Daftar produk tidak tampil |Network | Request /api/barang menghasilkan HTTP 404. Server menyediakan endpoint /api/products.|Ketidaksesuaian endpoint |Mengubah URL fetch dari /api/barang menjadi /api/product |Setelah pengujian ulang, produk berhasil ditampilkan sebanyak 4 produk
| Tombol keranjang |Tombol tambah ke keranjang tidak berfungsi |Element |Class tombol menggunakan add-button, tetapi JavaScript mencari .add-to-cart | Ketidaksesuaian nama class antara elemen HTML dan selector JavaScript| Mengubah selector .add-to-cart menjad add-button |setelah pengujian ulang, barang berhasil ditambahkan ke keranjang
| Total belanja | Total harga tidak sesuai ketika produk yang sama ditambahkan lebih dari satu kali| Element| Fungsi calculateTotal() hanya menjumlahkan item.price| Perhitungan tidak memperhitungkan properti quantity| Mengalikan item.price * item.quantity| hasil pengujian ulang, total belanja sudah berhasil menjumlahkan total barang

## B. Hasil pengujian
- Jumlah pengujian sebelum perbaikan: Tidak dilakukan pengujian otomatis sebelum perbaikan, pemeriksaan awal dilakukan memalui inspeksi kode dan pengujian langsung pada browser
- Jumlah pengujian berhasil setelah perbaikan:7 dari 7 pengujian berhasil
- Catatan perubahan pada fungsi yang diperiksa: 1. loadProduct() : penyesesuaian endpoint API. 2. renderProducts(): penyesuaian selector tombol keranjang. 3. calculateTotal(): perbaikan perhitungan harga berdasarkan quantity

## C. Kualitas kode
- Temuan sebelum perbaikan: 
1. Terdapat ketidaksesuaian endpoint API antara frontend dan backend sehingga daftar produk tidak dapat ditampilkan. Frontend menggunakan endpoint /api/barang, sedangkan backend menyediakan endpoint /api/products.

2. Terdapat ketidaksesuaian nama class pada tombol tambah ke keranjang. Elemen tombol menggunakan class add-button, sedangkan JavaScript mencari class add-to-cart, sehingga event klik tidak terpasang.

3. Fungsi calculateTotal() belum memperhitungkan jumlah barang (quantity) dalam keranjang, sehingga total harga tidak sesuai ketika produk yang sama ditambahkan lebih dari satu kali.

4. Ditemukan variabel discount yang tidak digunakan pada file src/cart.js.

5. Format penulisan kode pada public/app.js belum sesuai dengan standar formatter Biome.

- Perbaikan yang dilakukan:
1. Menyesuaikan endpoint API menjadi /api/products.

2. Menyesuaikan selector tombol menjadi .add-button.

3. Memperbaiki perhitungan total harga dengan mengalikan harga produk dan jumlah barang (price * quantity).

4. Menghapus variabel discount yang tidak digunakan.

5. Merapikan format penulisan kode menggunakan formatter Biome.

- Hasil pemeriksaan ulang: Aplikasi berhasil menampilkan daftar produk, tombol tambah ke keranjang dapat digunakan, dan total harga sudah memperhitungkan jumlah barang. Pengujian otomatis menunjukkan 7 pengujian berhasil dan 0 pengujian gagal. Pemeriksaan kualitas kode dilanjutkan menggunakan perintah lint, format, dan quality.

## D. Git
- Branch (jika membuat):
- Ringkasan commit:
- Hasil pemeriksaan `git status`:

## E. Pemakaian kecerdasan buatan (jika digunakan)
- Nama alat: 
- Pertanyaan/instruksi yang diberikan:
- Bagian jawaban yang diterapkan:
- Cara memeriksa apakah saran tersebut benar:

## F. Refleksi singkat
- Satu pelajaran paling penting dari ujian ini:
