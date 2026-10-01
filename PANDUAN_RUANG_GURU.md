# Panduan Ruang Guru, Manajemen Tugas & Evaluasi AI D-Chem

Dokumen ini adalah panduan lengkap pengoperasian **Ruang Guru D-Chem** untuk **Dhevira Aptia FIrmanda, S.Pd.**.

---

## 1. Akses Ruang Guru & Kata Sandi

- **Halaman Ruang Guru**: Buka berkas `Guru.html` di peramban, atau klik tautan **Ruang Guru** pada footer / panel guru di `index.html`.
- **Kata Sandi Default**: `guru08123`
- **Pengaturan Kata Sandi di Apps Script**:
  Jika menggunakan deployment Google Apps Script:
  1. Buka project Apps Script Anda.
  2. Buka menu **Project Settings (Ikon Roda Gigi)** > **Script Properties**.
  3. Tambahkan properti:
     - Property: `TEACHER_PASSWORD`
     - Value: `guru08123` (atau kata sandi baru sesuai keinginan Anda)
     - Property (Opsional): `GEMINI_API_KEY` (API Key dari Google AI Studio untuk penilaian AI otomatis)

---

## 2. Repositori Google Drive Resmi D-Chem

- **Tautan Folder Google Drive**: [Folder Google Drive D-Chem](https://drive.google.com/drive/folders/1i6pzb4q-QwC2bvWwyGferqg0_tkg9ZXp?usp=sharing)
- **ID Folder**: `1i6pzb4q-QwC2bvWwyGferqg0_tkg9ZXp`
- Seluruh 42 modul dan simulasi kimia interaktif di katalog D-Chem bersumber langsung dari Google Drive ini.

---

## 3. Fitur-Fitur Utama D-Chem

### A. Fitur Siswa (index.html)
1. **Lanjutkan Belajar Terakhir (Last Visited Banner)**:
   - Menampilkan banner pintar di bagian atas beranda yang menyimpan materi terakhir yang dibuka siswa.
   - Siswa cukup menekan tombol **Lanjut Belajar** untuk langsung melanjutkan proses belajarnya.
2. **Pelacak Kemajuan Belajar (Progress Checkmarks)**:
   - Setiap nomor langkah belajar dapat diklik oleh siswa untuk menandai selesai (`✅`).
   - Setiap bab memiliki indikator kemajuan (contoh: `3/5 Selesai`).
3. **Buka / Tutup Semua Folder (Expand/Collapse All Accordion)**:
   - Tombol *Buka Semua* dan *Tutup Semua* untuk memudahkan navigasi bab Kurikulum Merdeka.
4. **Navigasi Cepat per Jenjang (Quick Class Hub)**:
   - Klik kartu *Fase E (Kelas 10)*, *Fase F (Kelas 11)*, atau *Fase F (Kelas 12)* untuk otomatis menggulir halus ke katalog dan membuka bab yang sesuai.
5. **Tema Google Stitch Candy & Cyber Candy**:
   - Mendukung tema terang (*Candy 🍬*) dan tema gelap neon (*Cyber Candy ⚡🍬*).

### B. Fitur Guru & Pengelolaan (Guru.html & Mode Guru)
1. **Manajemen Tugas**:
   - Buat tugas baru dengan memilih salah satu dari 42 materi D-Chem.
   - Atur kelas sasaran, tenggat waktu (*deadline*), dan kebijakan pengumpulan terlambat.
   - Buat dan ekspor kode akses siswa / kelas.
2. **Evaluasi Otomatis dengan Gemini AI**:
   - Menganalisis isian LKPD, refleksi, dan esai siswa secara komprehensif menggunakan model Google Gemini.
   - Menghasilkan skor rekomendasi, analisis miskonsepsi, dan saran tindak lanjut guru.
3. **Data Roster Siswa**:
   - Impor data siswa dalam format baris `Kelas|NIS|Nama`.
   - Mengaktifkan atau menonaktifkan siswa tanpa menghapus riwayat tugas.
4. **Pengaturan Katalog Cloud**:
   - Guru dapat mengubah nama bab kimia secara langsung melalui tombol *Edit Judul Bab*.
   - Guru dapat mengatur ulang urutan belajar per bab dan menyimpan susunan baru ke Google Cloud (*Simpan ke Cloud*).
   - Memindahkan materi antar bab secara terstruktur melalui modal *Edit Bahan Ajar*.

---

## 4. Langkah Deployment ke Google Apps Script (Opsional)

Jika ingin menghubungkan antarmuka ke Google Sheet & Apps Script:
1. Buka [Google Apps Script](https://script.google.com).
2. Buat project baru bernama `D-Chem Backend`.
3. Salin seluruh isi berkas `Code.gs` lokal ke editor Apps Script.
4. Tambahkan berkas HTML baru bernama `Guru` dan tempel isi `Guru.html`.
5. Tambahkan berkas HTML baru bernama `index` dan tempel isi `index.html`.
6. Simpan project, lalu klik **Deploy** > **New Deployment**:
   - Tipe: **Web App**
   - Execute as: **Me**
   - Who has access: **Anyone**
7. Salin URL Web App yang dihasilkan.
8. Masukkan URL tersebut ke kolom **URL Backend GAS** pada dashboard guru D-Chem jika ingin tersambung penuh secara realtime.
