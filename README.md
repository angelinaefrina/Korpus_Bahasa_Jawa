# Korpus Suara Bahasa Jawa

Korpus ujaran spontan Bahasa Jawa yang dikumpulkan untuk tugas besar mata kuliah **IF4071 Pemrosesan Ucapan**, Program Studi Teknik Informatika, Institut Teknologi Bandung (ITB).

**Dosen pengampu:** Dessi Puji Lestari, S.T., M.Eng., Ph.D.

Kelompok 5:
| Nama | NIM |
|---|---|
| Stefan Mattew Susanto | 13523020 |
| Ferdinand Gabe Tua | 13523051 |
| Angelina Efrina Prahastaputri | 13523060 |
| Henry Filberto Shenelo | 13523108 |
| Ahmad Syafiq | 13523135 |

## Tujuan

Menyediakan data ujaran spontan Bahasa Jawa beserta transkripsi dan label untuk pelatihan dan pengujian sistem *Automatic Speech Recognition* (ASR) dalam lingkup mata kuliah IF4071.

## Ringkasan Korpus

| Aspek | Keterangan |
|---|---|
| Bahasa | Bahasa Jawa (dominan dialek Solo–Yogyakarta; rincian per penutur di `metadata/metadata.csv`) |
| Penutur | 10 orang (5 laki-laki, 5 perempuan), ID `S01`–`S10` |
| Jenis ujaran | Monolog spontan berdasarkan pertanyaan pemicu |
| Topik | 4 topik per penutur: `T01` = [isi], `T02` = [isi], `T03` = [isi], `T04` = [isi] |
| Jumlah file | 40 file audio (10 penutur × 4 topik) |
| Total durasi | [x] menit |
| Format audio | WAV, 16 kHz, 16-bit, mono |
| Lingkungan | Indoor, direkam mandiri oleh penutur di lokasi masing-masing |

## Struktur Folder

```
Korpus_Bahasa_Jawa/
├── audio/
│   ├── S01/ … S10/        # File audio per penutur
├── metadata/
│   └── metadata.csv       # Metadata per file dan atribut penutur
├── annotation/
│   └── annotation.csv     # Transkripsi dan label per segmen
├── consent/
│   └── consent_form/      # Template PSP kosong dan checklist persetujuan per Speaker ID
└── documentation/
    ├── README.txt
    └── [dokumentasi QC dan pedoman anotasi]
```

## Penamaan File

Format: `S{ID penutur}_T{ID topik}_{nomor urut}.wav`

Contoh: `S07_T02_001.wav` = penutur S07, topik T02, file ke-1.

## Metadata

File: `metadata/metadata.csv`

Kolom *[sesuaikan dengan header sebenarnya]*:
`File`, `Speaker`, `Gender`, `Age`, `Origin`, `Dialect`, `Topic`, `Duration`, `Environment`, `Device`, `Original_Format`, `Quality`

## Anotasi

File: `annotation/annotation.csv`

Satu baris = satu segmen ujaran. Audio tidak dipotong; batas segmen ditandai dengan timestamp (dalam detik) pada kolom `start` dan `end`.

Kolom *[sesuaikan dengan header sebenarnya]*:
`file`, `speaker`, `start`, `end`, `transcription`, `dialect`, `topic`, `event`

### Konvensi Transkripsi

- **Verbatim**: ditulis sesuai yang terdengar, tanpa diterjemahkan atau dibakukan. Pengulangan, kata pengisi, dan koreksi ucapan dipertahankan.
- Vokal *a* yang dilafalkan [o] ditulis sesuai bunyinya (*iso*, *ugo*, *ono*); yang dilafalkan [a] ditulis *a* (*isa*, *uga*, *ana*).
- Vokal *i/u* pada suku kata tertutup tetap ditulis *i/u* (*putih*, *dhuwur*).
- Campuran Bahasa Jawa dan Bahasa Indonesia ditulis sesuai ucapan.
- Penanda dalam teks:
  - `[UNCLEAR]` untuk ucapan tidak jelas
  - `[TRUNCATED]` untuk ucapan terpotong
  - `[NAMA]` untuk nama penutur

### Tag Peristiwa

| Tag | Definisi |
|---|---|
| `NONE` | Tidak ada peristiwa khusus |
| `LAUGHTER` | Tawa yang terdengar |
| `COUGH` | Batuk yang terdengar |
| `FILLED_PAUSE` | Jeda berisi suara pengisi |
| `OVERLAP` | Ucapan dua penutur atau lebih yang terjadi bersamaan |
| `BACKGROUND_NOISE` | Suara latar yang mengganggu atau relevan |
| `UNCLEAR_SPEECH` | Bagian ucapan tidak dapat dipahami |
| `TRUNCATED` | Ucapan atau kata terputus sebelum selesai |

Pedoman lengkap ada pada laporan
## Quality Control

Setiap file diperiksa untuk kejelasan suara, clipping, tingkat noise, suara orang lain, rekaman terpotong, kesesuaian format, dan kelengkapan metadata.

| Label | Jumlah file |
|---|---|
| Good | [x] |
| Acceptable | [x] |
| Reject (direkam ulang) | [x] |

Rincian: documentation/QC.md

## Etika dan Akses

- Seluruh penutur memberikan persetujuan melalui *informed consent* (PSP).
- Identitas penutur (nama, tanda tangan, kontak) **tidak** disimpan di repositori ini.
- Repositori bersifat **privat**. Akses hanya untuk dosen, asisten, dan mahasiswa mata kuliah IF4071.
- Data hanya boleh digunakan untuk keperluan akademik nonkomersial dalam mata kuliah ini. Penggunaan di luar mata kuliah hanya untuk data penutur yang menyetujui pernyataan opsional 4 (lihat checklist di folder `consent/`).
- **Dilarang menyebarluaskan data ke luar repositori ini.**
- Suara dapat mengidentifikasi seseorang, dan sebagian audio masih memuat nama penutur. Perlakukan data ini sebagai data pribadi.

## Keterbatasan

- Lingkungan dan perangkat perekaman berbeda-beda antarpenutur.
- Data berupa monolog, bukan percakapan dua arah.
- Sebaran dialek didominasi Solo–Yogyakarta.
- Nama penutur pada audio topik perkenalan tidak disenyapkan.

Penjelasan lengkap ada di laporan kelompok.

## Laporan

Laporan dapat diakses pada: [Laporan Tugas Besar Fase 1 Kelompok 5](https://docs.google.com/document/d/1txR0kapI7Czsq3utA4iFul3BNGCpGzj4kj2OfiXnuwM/edit?usp=drive_link)
