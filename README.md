# CNN vs Transfer Learning on CIFAR-10

Perbandingan dua pendekatan klasifikasi gambar: **CNN from scratch** pada CIFAR-10 vs **Transfer Learning (ResNet50)** pada Cats vs Dogs.

## Hasil

| Metode | Dataset | Akurasi Test |
|--------|---------|-------------|
| CNN from Scratch (2 conv layers) | CIFAR-10 (10 kelas) | 76.76% |
| Transfer Learning - Feature Extraction (ResNet50) | Cats vs Dogs (2 kelas) | 99.00% |
| Transfer Learning - Fine-tuning (ResNet50) | Cats vs Dogs (2 kelas) | **99.50%** |

## Setup

```bash
uv sync
uv run jupyter notebook
```

Jalankan semua cell di `notebook/cnn_vs_transfer_learning.ipynb` secara berurutan.

## Struktur Proyek

```
├── notebook/
│   └── cnn_vs_transfer_learning.ipynb   # Notebook utama
├── dataset/
│   ├── cifar-10-batches-py/             # CIFAR-10 (pre-downloaded)
│   └── cats_vs_dogs/dogs_vs_cats_subset/ # Cats vs Dogs dari Zenodo
├── report/
│   ├── laporan.tex                      # Source LaTeX (IEEEtran)
│   ├── laporan.pdf                      # Laporan PDF
│   └── figures/                         # Visualisasi hasil
├── pyproject.toml
└── .python-version
```

## Reproduksi Laporan

```bash
cd report
pdflatex laporan.tex
```

## Dependensi

Python >=3.14, PyTorch 2.12+, torchvision, numpy, matplotlib, scikit-learn, seaborn, tqdm, pillow, jupyter.

## Dataset

- **CIFAR-10**: 60.000 gambar 32×32, 10 kelas, 50.000 train / 10.000 test.
- **Cats vs Dogs**: Subset Kaggle/Microsoft dari Zenodo (Tue Boesen, 2024, CC-BY-4.0). 1.000 train / 200 val / 100 test (unlabelled).
