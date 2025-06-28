# Computer Reasoning: Pidana Klasifikasi Wanprestasi di Pengadilan PN Jakarta Pusat

Proyek ini mengembangkan sistem **penalaran berbasis kasus (Case-Based Reasoning)** untuk mendukung pencarian dan analisis putusan hukum dalam ranah **Pidana Klasifikasi Wanprestasi di Pengadilan PN Jakarta Pusat**. Sistem ini memungkinkan pengguna untuk mencari kasus serupa berdasarkan ringkasan fakta dan mengevaluasi performa retrieval menggunakan pendekatan TF-IDF + SVM dan BERT Embedding.

## ⚙️ Teknologi yang Digunakan

- **Python** 3.10+
- **Pustaka**: pandas, scikit-learn, BeautifulSoup, pdfminer.six, sentence-transformers
- **Tools**: Google Colab / Jupyter Notebook
- **Model**: TF-IDF + SVM, Sentence-Transformers (indobenchmark/indobert-base-p1)

## 📋 Struktur Proyek

Proyek ini terdiri dari lima tahap utama:

1. **Membangun Case Base**: Mengunduh 127 dokumen dari Direktori MA RI, mengonversi PDF/HTML ke teks, dan membersihkan data.
2. **Case Representation**: Ekstraksi metadata (nomor perkara, tanggal, pasal, pihak) dan fitur (ringkasan fakta, argumen hukum, Bag-of-Words, panjang teks).
3. **Case Retrieval**: Vektorisasi dengan TF-IDF dan BERT, splitting dataset (80:20), dan retrieval kasus serupa.
4. **Solution Reuse**: Prediksi solusi berdasarkan Top-k retrieval (BERT) atau Top-1 (SVM), dengan verifikasi manual menggunakan 10 query uji.
5. **Model Evaluation**: Evaluasi performa (Accuracy, Precision, Recall, F1-score) dan visualisasi hasil (tabel metrik, bar chart, error analysis).

## 🚀 Petunjuk Instalasi & Eksekusi

### 1. Clone Repository

```bash
git https://github.com/haidarfaizul/computer-reasoning.git
cd computer-reasoning
```

### 2. Install Dependensi

Buat dan aktifkan environment (opsional):

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

Install dependensi dari `requirements.txt`:

```bash
pip install -r requirements.txt
```

Isi file `requirements.txt`:

```
pandas
scikit-learn
beautifulsoup4
pdfminer.six
sentence-transformers
```

Untuk Google Colab, jalankan perintah berikut di notebook:

```python
!pip install pandas scikit-learn beautifulsoup4 pdfminer.six sentence-transformers
```

### 3. Jalankan End-to-End Pipeline

Jalankan notebook secara berurutan:

1. `Tahap 1 Membangun Case Base.ipynb`: Konversi PDF ke teks dan pembersihan data.
2. `Tahap 2 Case Representation.ipynb`: Ekstraksi metadata dan fitur.
3. `Tahap 3 Case Retrieval.ipynb`: Vektorisasi dan retrieval kasus.
4. `Tahap 4 Solution Reuse.ipynb`: Prediksi solusi dari kasus serupa.
5. `Tahap 5 Model Evaluation.ipynb`: Evaluasi dan visualisasi performa.

**Catatan**: Sesuaikan path file di notebook dengan lokasi di Google Drive atau lokal.

## 🔧 Catatan Tambahan

- Proyek ini fokus pada domain **Pidana Klasifikasi Wanprestasi di Pengadilan PN Jakarta Pusat**.
- Ideal untuk pembelajaran, penelitian, atau pengembangan sistem hukum berbasis AI.
- Pastikan koneksi internet stabil untuk mengunduh model `indobenchmark/indobert-base-p1`.

## 📄 Kontributor

**Author**: Haidar Faizul Ikram El Jauhari
