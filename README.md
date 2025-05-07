# 📚 Book Recommendation System

## 📌 Deskripsi Proyek

Proyek ini bertujuan untuk membangun sistem rekomendasi buku menggunakan dua pendekatan utama:
1. **Content-Based Filtering**
2. **Collaborative Filtering**

Dengan memanfaatkan dataset dari Kaggle: [Book Recommendation Dataset](https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset), proyek ini bertujuan untuk membantu pengguna menemukan buku yang relevan dengan preferensi mereka, serta meningkatkan minat baca masyarakat.

## 🎯 Tujuan

- Membangun sistem rekomendasi yang personal dan akurat berdasarkan data pengguna dan buku.
- Mengimplementasikan dua pendekatan rekomendasi dan membandingkan kinerjanya.
- Mengevaluasi efektivitas masing-masing pendekatan melalui metrik evaluasi umum seperti RMSE, MAE, Precision@10, Coverage, Diversity, Recall@10, dan Hit Rate.

## 📂 Struktur Dataset

Dataset terdiri dari 3 file utama:

| File        | Deskripsi                                           |
|-------------|-----------------------------------------------------|
| `Books.csv` | Informasi tentang buku (judul, penulis, ISBN, dll) |
| `Ratings.csv` | Rating yang diberikan pengguna terhadap buku      |
| `Users.csv`  | Informasi demografis pengguna                      |

## 🛠️ Teknik yang Digunakan

### 1. Content-Based Filtering
- Ekstraksi fitur dari metadata buku menggunakan **TF-IDF Vectorizer**.
- Penghitungan **cosine similarity** antar buku.
- Sistem memberikan rekomendasi buku serupa berdasarkan input judul.

### 2. Collaborative Filtering
- Membuat fungsi rekomendasi yang dapat menyarankan buku-buku dengan prediksi rating tertinggi untuk pengguna tertentu.
- Rekomendasi berdasarkan preferensi pengguna yang serupa.

## 📊 Evaluasi Model

### 🔹 Content-Based Filtering
| Metrik        | Nilai   |
|---------------|---------|
| Precision@10  | 0.0143  |
| Coverage      | 0.0198  |
| Diversity     | 0.7468  |

### 🔹 Collaborative Filtering
| Metrik                    | Nilai   |
|---------------------------|---------|
| RMSE (0–1)                | 0.1598  |
| MAE (0–1)                 | 0.1250  |
| RMSE (1–10)               | 1.5983  |
| MAE (1–10)                | 1.2503  |
| Recall@10                | 0.0044  |
| Hit Rate                  | 0.0200  |

## 📈 Hasil & Kesimpulan

- **Content-Based Filtering** unggul dalam keberagaman (diversity), cocok untuk memberikan rekomendasi bervariasi walaupun masih kurang dalam presisi dan jangkauan pengguna.
- **Collaborative Filtering** menghasilkan prediksi rating yang cukup akurat (RMSE dan MAE rendah), namun belum optimal dalam merekomendasikan buku yang benar-benar dibaca pengguna (recall rendah).
- Kedua metode memiliki kelebihan masing-masing dan bisa dikombinasikan dalam sistem hybrid untuk hasil yang lebih baik.

## 👩‍💻 Kontributor

**Idha Kurniawati**  
Proyek ini dibuat sebagai bagian dari studi eksploratif untuk mendorong minat baca masyarakat melalui teknologi Machine Learning.
