# Panduan Lengkap: D-Chem Portal Bahan Ajar Kimia SMA
**Pengembang/Pengampu:** Dhevira Aptia FIrmanda, S.Pd.  
**Kata Sandi Area Guru:** guru08123  
**Lokasi Berkas Lokal:** C:\Users\Tito\Desktop\D-Chem-Bahan Ajar\

---

## 🧪 Tentang D-Chem

**D-Chem** adalah platform portal bahan ajar kimia interaktif modern berbasis kurikulum SMA (Kurikulum Merdeka) yang mengadopsi sistem desain resmi **Google Stitch**:
- **Mode Terang (Candy)**: Gaya visual *Joyful Pop* dengan palet warna Raspberry Pop (#e040a0), Royal Violet (#7c52aa), Sky Blue (#0096cc), kontur pil bulat lembut (*pill shapes*), dan interaksi mikro pegas elastis (*bouncy spring*).
- **Mode Gelap (Cyber Candy)**: Gaya visual *Luminous Neon Glassmorphism* dengan latar obsidian pekat (#0d0b14), kaca akrilik gelap translusen, serta pendar neon magenta (#f43f9e), elektrik violet (#a855f7), dan aksen cyan glowing (#06b6d4).

Sesuai arahan, aset simulasi interaktif dari platform lain **tidak disalin** demi menjaga hak cipta dan orisinalitas kepemilikan. Portal D-Chem hadir dalam keadaan bersih (*clean state*) dan siap diisi dengan materi orisinal Ibu Dhevira sendiri.

---

## 📁 Struktur Berkas Proyek

1. **index.html**: Antarmuka web utama portal D-Chem (Bento grid bahan ajar, live search, filter fase kelas/format, viewer dokumen in-app untuk PDF LKPD, slide PPT, link media interaktif, kalkulator Mr, penyetara reaksi kimia, kamus istilah kimia, dan mode guru terproteksi).
2. **manifest.json**: Konfigurasi Progressive Web App (PWA) agar D-Chem dapat dipasang langsung di desktop (Chrome/Edge) dan smartphone Android/iOS.
3. **sw.js**: Service worker untuk kemampuan caching offline PWA.
4. **icon.svg**: Ikon resmi D-Chem (Erlenmeyer neon + orbit atom) berstandar Google Stitch.
5. **Code.gs**: Skrip backend Google Apps Script yang dapat dihubungkan ke Google Spreadsheet pribadi Ibu Dhevira.
6. **Stitch/**: Aset dan dokumentasi spesifikasi desain Google Stitch (Candy & Cyber Candy).

---

## 🔐 Cara Masuk ke Area Guru

1. Buka berkas index.html di browser Anda (Google Chrome, Edge, atau Firefox).
2. Klik tombol **Area Guru** di bilah navigasi kanan atas atau tombol **Masuk Area Guru** pada kartu sambutan.
3. Masukkan kata sandi mode guru:
   `	ext
   guru08123
   `
4. Tekan tombol **Buka Panel Akses**.
5. Setelah berhasil masuk:
   - Tombol berubah menjadi **Panel Guru** dengan badge aktif.
   - Dashboard pengelolaan bahan ajar akan terbuka.
   - Anda dapat menambahkan materi satu per satu secara manual atau melakukan pemindaian otomatis (*Auto-Scan*) folder Google Drive.

---

## ☁️ Menghubungkan Backend Google Apps Script & Spreadsheet Pribadi (Opsional)

Jika Ibu Dhevira ingin menghubungkan portal ke Google Spreadsheet sendiri untuk menyimpan daftar bahan ajar:

1. Buat Google Spreadsheet baru di Google Drive Anda.
2. Di Spreadsheet, klik **Ekstensi** > **Apps Script**.
3. Hapus kode default di Code.gs, lalu tempelkan (*copy-paste*) kode dari berkas Code.gs yang ada di folder ini.
4. Ganti konstanta SPREADSHEET_ID di baris 13 dengan ID Spreadsheet Anda (karakter acak di URL Spreadsheet antara /d/ dan /edit).
5. Klik **Deploy** (Terapkan) > **New deployment** (Penerapan baru).
6. Pilih jenis **Web app**:
   - **Description**: D-Chem Backend API
   - **Execute as**: Me (email Anda)
   - **Who has access**: Anyone (Siapa saja)
7. Salin Web App URL yang dihasilkan (berakhiran /exec).
8. Di index.html, ganti konstanta GAS_API_URL (sekitar baris 1642) dengan URL Web App Anda.

---

## ⚡ Cara Menambahkan Bahan Ajar ke D-Chem

### Opsi 1: Menambah Secara Manual via Panel Guru
1. Masuk ke **Panel Guru** (kata sandi guru08123).
2. Klik tombol **+ Tambah Bahan Ajar**.
3. Isi informasi materi:
   - **Judul Bahan Ajar** (contoh: *Praktikum Titrasi Asam Basa*)
   - **Tingkat / Fase Kelas** (Kelas 10 / 11 / 12)
   - **Format Berkas**:
     - HTML Interaktif: Untuk link simulator kimia web (PhET, ChemCollective, dsb.).
     - Dokumen PDF: Untuk modul atau LKPD.
     - Slide Presentasi (PPT): Untuk Google Slides atau presentasi PowerPoint.
     - Video: Untuk video edukasi YouTube.
   - **URL Berkas / Link**: Masukkan link Google Drive (pastikan akses publik Siapa saja yang memiliki link) atau tautan web.
   - **Pilihan Thumbnail**: Pilih salah satu tema thumbnail kimia atau tempelkan link gambar sendiri.
4. Klik **Simpan Bahan Ajar**. Materi akan langsung tampil di halaman depan.

### Opsi 2: Sinkronisasi Folder Google Drive Otomatis (Sangat Praktis)
Folder Google Drive resmi D-Chem karya Ibu Dhevira telah terpasang secara bawaan:
`https://drive.google.com/drive/folders/1i6pzb4q-QwC2bvWwyGferqg0_tkg9ZXp?usp=sharing`

1. Kumpulkan berkas LKPD PDF, slide materi PPT, atau materi Anda dalam Folder di Google Drive.
2. Atur izin akses folder Drive tersebut menjadi **Siapa saja yang memiliki link dapat melihat** (*Anyone with the link can view*).
3. Buka **Panel Guru** > link folder Google Drive resmi D-Chem sudah otomatis terisi di kolom **Auto-Sync Folder Google Drive**.
4. Klik tombol **Mulai Pemindaian Folder**.
5. Sistem akan mendeteksi seluruh berkas (42 media interaktif D-Chem) dan menyinkronkannya ke katalog D-Chem tanpa bercampur dengan materi portal lain.

---

## 📱 Menginstal Sebagai Aplikasi (PWA) di Komputer / Ponsel

1. Buka portal di peramban Chrome atau Edge.
2. Klik tombol **Pasang Aplikasi** di bagian atas atau klik ikon instal di bilah alamat peramban.
3. Aplikasi D-Chem akan terpasang sebagai aplikasi mandiri di komputer atau ponsel Anda dengan ikon resmi Erlenmeyer neon dan dapat dibuka sewaktu-waktu.
