# Petunjuk Pengerjaan Tugas 7 — SI RAKUS

Paket ini merupakan kerangka pembelajaran. Dua bagian penting pada kode sengaja diberi `TODO` agar mahasiswa menyelesaikannya dan memahami operasi Update serta Delete sesuai panduan dosen.

## 1. Selesaikan TODO Update

Buka `crud-lokal.dart`, cari komentar `TODO TUGAS MAHASISWA` di dalam metode `_ubahBuku`.

Di dalam `setState`, ganti objek pada posisi `index` dengan objek hasil form `bukuBaru`. Baris yang perlu dipahami adalah:

```dart
_daftarBuku[index] = bukuBaru;
```

Setelah operasi berhasil, tampilkan SnackBar yang menyatakan data contoh berhasil diperbarui. Jangan menampilkan pesan berhasil sebelum operasi dijalankan.

## 2. Selesaikan TODO Delete

Cari komentar `TODO TUGAS MAHASISWA` pada metode `_konfirmasiHapus`.

Di dalam `setState`, hapus item dengan membandingkan ID, bukan index:

```dart
_daftarBuku.removeWhere((item) => item.id == buku.id);
```

Setelah operasi berhasil, tampilkan SnackBar bahwa data contoh berhasil dihapus. Penghapusan hanya terjadi jika pengguna memilih tombol “Hapus” pada AlertDialog.

## 3. Jalankan proyek

Salin isi `crud-lokal.dart` ke `lib/main.dart` pada proyek Flutter yang memiliki `pubspec.yaml`, lalu jalankan:

```powershell
flutter pub get
flutter analyze
flutter run -d chrome
```

Kode ini tidak menggunakan package tambahan dan dapat diuji menggunakan Flutter SDK. Setelah TODO diselesaikan, uji Create, Read, Update, dan Delete dari antarmuka.

## 4. Skenario pengujian

1. Create: tekan “Tambah Buku”, isi seluruh field dengan benar, tekan “Tambah”, dan pastikan kartu baru muncul.
2. Read: pastikan kartu data awal dan data baru muncul pada daftar; buka “Detail” untuk memeriksa field lengkap.
3. Update: ubah stok salah satu buku, simpan, lalu pastikan jumlah stok dan status (tersedia/habis) berubah sesuai nilai baru.
4. Delete: tekan “Hapus”, pastikan AlertDialog muncul, pilih “Batal” dan pastikan data tetap ada; ulangi lalu pilih “Hapus” dan pastikan data menghilang.
5. Filter: cari judul/penulis dan pilih kategori; pastikan daftar menyesuaikan filter.

## 5. Screenshot

- `screenshot-daftar.png`: tampilkan halaman yang memuat data hasil Create dan daftar Read.
- `screenshot-hapus.png`: tampilkan AlertDialog konfirmasi ketika tombol Hapus ditekan, sebelum memilih konfirmasi.

Jangan membuat screenshot palsu atau mengubah gambar agar tampak seolah-olah kode berjalan. Ambil langsung dari aplikasi Flutter yang telah diuji.

## 6. Batasan data

Data disimpan in-memory di dalam `State`. Data akan kembali ke data awal setelah aplikasi dimulai ulang. Operasi CRUD mengelola dataset latihan, bukan katalog resmi perpustakaan dan bukan implementasi pengelolaan koleksi petugas F-07.
