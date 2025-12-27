# 🎬 Movie Recommendation System

Hệ thống gợi ý phim sử dụng **MovieLens Dataset**, kết hợp ba phương pháp:
- **Content-Based Filtering**
- **Collaborative Filtering (SVD)**
- **Hybrid Recommendation**

Dự án được xây dựng bằng Python và có giao diện demo bằng **Streamlit**.

---

## 📌 Mục tiêu dự án

- Xây dựng hệ thống gợi ý phim cá nhân hóa
- Áp dụng các thuật toán Machine Learning trong Recommendation System
- So sánh và kết hợp nhiều phương pháp gợi ý
- Trực quan hóa kết quả thông qua giao diện Web

---

## 📂 Cấu trúc thư mục

Nguyễn_Quang_Anh_B21DCCN006_BTL/
│
├── data/
│ ├── movies.dat
│ ├── ratings.dat
│
├── recommender.py # Content-Based Filtering
├── collaborative.py # Collaborative Filtering (SVD)
├── hybrid.py # Hybrid Recommendation
├── main.py # Chạy hệ thống trên terminal
├── app.py # Giao diện Streamlit
├── requirements.txt # Danh sách thư viện
├── README.md
└── venv/



## 📊 Dataset

Sử dụng **MovieLens 1M Dataset**:
- ~1 triệu ratings
- ~6.000 users
- ~4.000 movies

**Các file sử dụng**:
- `movies.dat`: thông tin phim (movieId, title, genres)
- `ratings.dat`: đánh giá của người dùng (userId, movieId, rating)

Nguồn: https://grouplens.org/datasets/movielens/

---

## ⚙️ Cài đặt môi trường

### 1️⃣ Tạo môi trường ảo (khuyến nghị)

```bash
python -m venv venv
venv\Scripts\activate

2️⃣ Cài thư viện

bash
pip install -r requirements.txt

⚠️ Lưu ý:
scikit-surprise chưa hỗ trợ NumPy 2.x, do đó dự án sử dụng:
numpy==1.26.4

🚀 Cách chạy chương trình
▶️ Chạy trên Terminal
bash
python main.py

Chương trình sẽ:
Gợi ý phim theo Content-Based
Huấn luyện mô hình Collaborative Filtering (SVD)
Đánh giá mô hình (RMSE, MAE)
Gợi ý phim cho người dùng
Gợi ý Hybrid

🌐 Chạy giao diện Streamlit
bash
streamlit run app.py

Mở trình duyệt tại:
http://localhost:8501

🧠 Các phương pháp sử dụng
1️⃣ Content-Based Filtering
Sử dụng TF-IDF trên thể loại phim

Đo độ tương đồng bằng Cosine Similarity

Gợi ý phim dựa trên nội dung tương tự

2️⃣ Collaborative Filtering
Sử dụng thư viện Surprise

Thuật toán SVD (Singular Value Decomposition)

Dự đoán rating của user cho phim chưa xem

Đánh giá mô hình:
RMSE
MAE

3️⃣ Hybrid Recommendation
Kết hợp Content-Based và Collaborative Filtering

Công thức:

HybridScore = α * ContentScore + (1 - α) * CollaborativeScore
Cho phép điều chỉnh trọng số α trên giao diện Streamlit

📈 Kết quả mẫu
RMSE ≈ 0.87

MAE ≈ 0.69

Gợi ý phim cá nhân hóa theo từng người dùng

Giao diện trực quan, dễ demo

🛠 Công nghệ sử dụng
Python

Pandas, NumPy

Scikit-learn

Scikit-surprise

Matplotlib, Seaborn

Streamlit

####Trong trường hợp cài thư viện lỗi, xóa tất cả trong file requirements.txt rồi thay thế bằng file requirement.txt mới

# ===== CORE =====
python-dateutil>=2.8.2

# ===== NUMPY (BẮT BUỘC < 2.0 vì scikit-surprise) =====
numpy==1.26.4

# ===== DATA =====
pandas>=2.0.3
scipy>=1.10.1

# ===== MACHINE LEARNING =====
scikit-learn>=1.3.0
scikit-surprise==1.1.4

# ===== VISUALIZATION =====
matplotlib>=3.7.2
seaborn>=0.12.2

# ===== WEB UI =====
streamlit>=1.29.0
