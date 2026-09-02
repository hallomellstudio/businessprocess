# Website Mata Kuliah Proses Bisnis

Proyek Quarto berbahasa Indonesia untuk 14 pertemuan mata kuliah Proses Bisnis. Isinya mencakup silabus ringkas, materi mingguan, aktivitas kelas, tugas, proyek akhir, rubrik, dan glosarium.

## 1. Sesuaikan identitas

Cari seluruh teks yang memakai tanda kurung siku, misalnya `[NAMA DOSEN]`, lalu ganti dengan informasi mata kuliah Anda. Pada `_quarto.yml`, ganti `USERNAME` dan `NAMA-REPOSITORY` pada `site-url`, `repo-url`, serta tautan GitHub.

## 2. Tampilkan secara lokal

Instal Quarto dari <https://quarto.org/docs/get-started/>, kemudian jalankan:

```bash
quarto preview
```

Untuk membuat seluruh situs tanpa membuka pratinjau:

```bash
quarto render
```

Hasil render berada di folder `docs/`.

## 3. Masukkan ke GitHub

Buat repositori kosong, lalu dari folder proyek ini jalankan:

```bash
git init
git add .
git commit -m "Initial course website"
git branch -M main
git remote add origin https://github.com/USERNAME/NAMA-REPOSITORY.git
git push -u origin main
```

## 4. Aktifkan GitHub Pages

Workflow `.github/workflows/publish.yml` akan merender website ke folder `docs/` dan menerbitkannya setiap kali ada *push* ke branch `main`.

Pada repositori GitHub, buka **Settings → Pages**, lalu pada bagian **Build and deployment → Source** pilih **GitHub Actions**. Setelah itu, lakukan *push* baru atau jalankan workflow secara manual melalui tab **Actions**.

Jika Anda memilih metode **Deploy from a branch** alih-alih GitHub Actions, jalankan `quarto render`, masukkan folder `docs/` ke commit, lalu pilih branch `main` dan folder `/docs` pada pengaturan GitHub Pages.

Alamat situs biasanya berbentuk:

```text
https://USERNAME.github.io/NAMA-REPOSITORY/
```

## Struktur penting

```text
.
├── _quarto.yml
├── index.qmd
├── silabus.qmd
├── tugas.qmd
├── proyek.qmd
├── rubrik.qmd
├── glosarium.qmd
├── docs/                  # hasil quarto render
├── materi/
│   ├── index.qmd
│   └── 01-pengantar.qmd ... 14-presentasi.qmd
├── styles.css
└── .github/workflows/publish.yml
```

## Menambah materi

1. Duplikasi salah satu berkas `.qmd` di folder `materi/`.
2. Ubah judul, tujuan belajar, isi, dan aktivitasnya.
3. Tambahkan lokasi berkas pada bagian `website.sidebar.contents` di `_quarto.yml`.
4. Jalankan `quarto preview` untuk memeriksa hasil.

Dokumentasi publikasi GitHub Pages: <https://quarto.org/docs/publishing/github-pages.html>
