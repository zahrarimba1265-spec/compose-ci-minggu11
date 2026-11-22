# compose-ci-minggu11

[![Compose Check](https://github.com/zahrarimba1265-spec/compose-ci-minggu11/actions/workflows/compose-check.yml/badge.svg)](https://github.com/zahrarimba1265-spec/compose-ci-minggu11/actions/workflows/compose-check.yml)

Stack WordPress + MariaDB (tugas Minggu 10) dengan CI GitHub Actions yang
memvalidasi file Compose setiap ada push ke `main` atau pull request.

## Cara menjalankan stack

```bash
git clone https://github.com/zahrarimba1265-spec/compose-ci-minggu11.git
cd compose-ci-minggu11
cp .env.example .env        # lalu edit .env, isi password sendiri
docker compose config -q    # validasi sintaks (sama seperti CI)
docker compose up -d
```

Buka http://localhost:8080 untuk menyelesaikan instalasi WordPress.
Hentikan dengan `docker compose down` (tambahkan `-v` untuk menghapus data).

## Cara kerja CI

Workflow `.github/workflows/compose-check.yml` menyalin `.env.example`
menjadi `.env` lalu menjalankan `docker compose config -q`. Job merah
berarti ada kesalahan penulisan pada file Compose.

## Tangkapan layar

![Actions hijau](docs/01-actions-hijau.png)
![Detail job](docs/02-detail-job.png)
![Halaman repo dan badge](docs/03-repo-badge.png)

## Sumber bantuan

Dokumentasi Docker Compose dan GitHub Actions, materi kuliah Minggu 10-11,
serta bantuan AI (Claude) untuk menyusun contoh file dan panduan langkah.
Semua file sudah saya baca, jalankan, dan pahami sendiri.
