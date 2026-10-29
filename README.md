# Pengingat Tahapan — Android project

Proyek awal Android native (Java) untuk aplikasi pencatatan agenda, tahapan, pengawasan/tindak lanjut, tenggat, notifikasi lokal, dan pencadangan JSON. Data tersimpan di SQLite lokal; tidak ada login, server, atau koneksi internet yang diperlukan untuk fungsi utama.

## Cara membangun APK
1. Instal Android Studio versi stabil yang mendukung Android Gradle Plugin 8.7.3.
2. Instal Android SDK Platform 35 dan Android Build Tools yang ditawarkan SDK Manager.
3. Ekstrak ZIP ini, lalu buka folder `PengingatTahapan` melalui Android Studio.
4. Tunggu Gradle Sync. Jika diminta, instal komponen SDK/JDK yang direkomendasikan Android Studio.
5. Pilih **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
6. APK debug biasanya berada di `app/build/outputs/apk/debug/app-debug.apk`.

## Fitur versi awal
- Dashboard jumlah agenda, tahapan aktif, dan tindak lanjut.
- Tambah, ubah, hapus, serta tandai selesai untuk agenda, tahapan, dan pengawasan.
- Tanggal mulai/tenggat, status, prioritas, lokasi, penanggung jawab, catatan.
- Pengingat lokal pada pukul 09.00 di tanggal tenggat yang dimasukkan.
- Ekspor dan impor cadangan JSON melalui pemilih berkas Android.
- Tanpa login, database SQLite lokal.

## Kebutuhan/pekerjaan teknis yang masih perlu diputuskan
- **Aturan tahapan resmi**: daftar dan urutan tahapan harus divalidasi terhadap Tatib/peraturan DPRD yang berlaku. Aplikasi ini tidak mengklaim daftar bawaan sebagai ketentuan resmi.
- **Pengingat yang andal**: Android versi baru membatasi alarm tepat waktu dan notifikasi. Izin notifikasi harus diberikan; perangkat bisa menunda alarm karena mode hemat baterai. Versi produksi sebaiknya menambah pengaturan waktu pengingat, pengingat berulang, dan pemulihan jadwal setelah perangkat restart.
- **Lampiran dokumen**: pemilih dokumen tersedia sebagai dasar, tetapi penyimpanan lampiran ke arsip belum diterapkan pada versi awal.
- **Cadangan**: ekspor/impor JSON tersedia; lakukan ekspor berkala sebelum mengganti HP atau menghapus aplikasi. Data offline tidak otomatis tersinkron antarperangkat.
- **Keamanan**: tanpa login berarti siapa pun yang dapat membuka HP dan aplikasi dapat melihat/mengubah data. Gunakan pengamanan perangkat dan jangan memasukkan informasi rahasia tanpa kebijakan pengamanan yang disepakati.
- **Uji perangkat**: build harus diuji di perangkat Android target, khususnya notifikasi, izin, format tanggal, ekspor/impor, dan pemulihan data.
- **Identitas resmi**: logo, warna, dan nama lembaga resmi dapat ditambahkan setelah aset dan persetujuan disediakan.

## Catatan
Ini adalah proyek sumber yang dapat dibuka dan dibangun di Android Studio; APK belum dikompilasi atau diuji pada perangkat dalam lingkungan ini. Gradle membutuhkan akses internet saat pertama kali mengunduh plugin/dependensi.
