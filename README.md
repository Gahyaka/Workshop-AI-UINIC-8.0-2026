# Workshop AI UINIC 8.0 — Sesi 2

Materi hands-on **Foundations of Computer Vision: CNN to Transfer Learning** — PyTorch + MobileNetV2 di Google Colab.

Workshop: Sabtu, 7 November 2026 · FST 303 UIN Sunan Kalijaga


## Link Notebook Google Colab

| Notebook | Untuk | Buka |
|---|---|---|
| `Workshop_AI_UINIC_8_0_Peserta_HandsOn.ipynb` | Hands-on Peserta | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/16mrCq6MZOxGYUWy-2AGJ2_T1pMTTs10L) |
| `Workshop_AI_UINIC_8_0_Narasumber.ipynb` | Demo Narsum | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/10FftbfC8kQTHHp0Ilhnyy-fSg5MahA2I) |

**Langkah membuka:**

1. Klik badge di atas — notebook terbuka di Colab.
2. **File > Save a copy in Drive** supaya hasilmu tersimpan di Drive sendiri.
3. **Runtime > Change runtime type > T4 GPU > Save**.
4. Jalankan sel berurutan dari atas ke bawah (Shift+Enter).

Webcam hanya berjalan di Chrome setelah izin kamera diberikan.

## Aturan tugas

- **Klasifikasi citra multi-kelas**, 2–5 kelas; disarankan **3–5**.
- Lebih dari 5 kelas harus dipangkas dulu — notebook berhenti dengan pesan.
- Struktur ZIP: folder per kelas di root, `train/val/test`, atau `train` + `test`.
- Ukuran gambar 128 px, backbone MobileNetV2 dibekukan, hanya head yang dilatih.

## Tema SDGs

- SDG 3 — Good Health and Well-Being
- SDG 2 & SDG 15 — Zero Hunger & Life on Land
- SDG 6 — Clean Water and Sanitation
- SDG 11 — Sustainable Cities and Communities
- SDG 12 — Responsible Consumption and Production
- SDG 13 — Climate Action

Pilih satu tema untuk kelompokmu. Contoh kasus dan kata kunci pencarian dijelaskan narasumber saat sesi.

## Alur singkat

| Langkah | Yang dilakukan | Isian |
|---|---|---|
| 0 | Setup, seed, cek T4 | — |
| 1 | Ekstrak ZIP, split 70/15/15 | `ZIP_PATH` |
| 2 | Distribusi kelas dan sampel foto | `RUMPANG A & B` |
| 3 | Transform dan augmentasi | `PANEL_AUGMENTASI` |
| 4 | MobileNetV2 + head | `RUMPANG-2/3/4` |
| 5 | Latih E1 lalu E2 | `PANEL_HYPER` |
| 6 | Evaluasi test sekali | — |
| 7 | Inferensi YAKIN/RAGU | `AMBANG_KONFIDENSI` |
| 7b | Opsional: unggah foto, webcam live | `LABEL_ASLI`, `JUMLAH_FRAME` |
| Akhir | Rangkuman dan catatan | 7 butir `CATATAN` |

Eksperimen E2: ubah **satu** variabel saja — disarankan `learning_rate` (1e-3 → 1e-4 bila loss melompat, 1e-2 bila terlalu lambat).

## Output Peserta
Menyelesaikan notebook yang sudah berjalan sampai `CATATAN` (tujuh butir catatan) dan slide presentasi.

| Outtline PPT |
|---|
| Latar belakang & SDGs | 
| Dataset | 
| Processing & augmentasi | 
| Hyperparameter |
| Evaluation |
| Inference | 
| Kesimpulan |

## Masalah umum

| Gejala | Penyebab | Solusi |
|---|---|---|
| GPU tidak terdeteksi | Runtime masih CPU | Change runtime type → T4 GPU → Save |
| ZIP tidak ditemukan | Path kosong atau salah | Biarkan `ZIP_PATH` kosong untuk unggah manual |
| Struktur dataset TIDAK dikenali | Susunan folder asing | Folder per kelas di root ZIP |
| NameError di baris `___` | Rumpang belum diisi | Isi pada sel misi terkait |
| Kamera gagal dibuka | Izin ditolak | Ikon gembok → Camera → Allow → refresh |

## Panduan PDF

- [Panduan peserta](panduan/Panduan_Peserta.pdf)
- [Panduan fasilitator](panduan/Panduan_Fasilitator.pdf)

## Struktur repo

```
.
├── Workshop_AI_UINIC_8_0_Peserta_HandsOn.ipynb
├── Workshop_AI_UINIC_8_0_Narasumber.ipynb
├── panduan/
│   ├── Panduan_Peserta.pdf
│   └── Panduan_Fasilitator.pdf
└── README.md
```

## Dataset contoh

[Potato Disease Data — PlantVillage](https://www.kaggle.com/datasets/aarishasifkhan/plantvillage-potato-disease-dataset) · 2.152 gambar, 3 kelas, lisensi Apache 2.0. Unduh dari Kaggle lalu unggah ZIP-nya ke Google Drive atau langsung ke Google Colab.

## Kredit

Materi disusun untuk Workshop AI UINIC 8.0, Sesi 2. Model dan bobot pretrained dari torchvision (MobileNetV2, ImageNet). Dataset tetap milik penyusunnya masing-masing; periksa lisensi sebelum dipakai ulang.
