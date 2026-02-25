# 🚗 Saudi Arabia Used Car Price Prediction

**Machine Learning Regression & Business Insight Analysis**

---

## 📌 Business Context

Pasar mobil bekas di Arab Saudi memiliki variasi harga yang tinggi akibat kombinasi faktor seperti usia kendaraan, merek, fitur, dan kapasitas mesin. Ketidaktepatan dalam penentuan harga dapat menyebabkan:

* Overpricing → unit sulit terjual
* Underpricing → kerugian finansial
* Volatilitas harga antar segmen

Proyek ini bertujuan membangun model regresi yang tidak hanya akurat secara statistik, tetapi juga mampu mengidentifikasi faktor dominan penentu harga dan menerjemahkannya ke dalam insight bisnis.

---

## 🎯 Problem Statement

Bagaimana membangun model yang:

1. Meminimalkan error finansial (RMSE & MAE)
2. Stabil pada distribusi harga yang skewed
3. Mampu menjelaskan variasi harga secara signifikan
4. Tetap interpretatif dan selaras dengan logika pasar

Target: **Prediksi Price (SAR)**

---

## 📊 Data & Preparation

### Data Cleaning

* Penghapusan duplikat
* Eliminasi Price = 0
* Penanganan outlier (Mileage, Engine_Size)
* Feature engineering: `Car_Age`

### Preprocessing Strategy

* RobustScaler untuk fitur numerik
* OneHotEncoder untuk low-cardinality categorical
* BinaryEncoder untuk high-cardinality categorical
* Pipeline untuk mencegah data leakage

Distribusi target menunjukkan right-skewness dengan long tail pada segmen premium.

---

## 🧪 Modeling Strategy

Dilakukan benchmarking beberapa algoritma regresi:

* Linear Regression
* Regularized Regression
* Tree-based Models
* Ensemble Models

Validasi menggunakan:

* 5-Fold Cross Validation
* Multi-metric evaluation (MSE, RMSE, MAE, R²)

Fokus utama:

* RMSE → penalti error besar
* MAE → interpretasi bisnis
* R² → explanatory power

---

## 🏆 Final Model: Tuned XGBoost

Setelah hyperparameter tuning:

| Metric | Hasil       |
| ------ | ----------- |
| RMSE   | ~30.000 SAR |
| MAE    | ~17.000 SAR |
| R²     | 0.82        |

Model mampu menjelaskan sekitar 82% variasi harga kendaraan.

Tuning memberikan penurunan MSE sebesar ±22%, menunjukkan optimasi parameter signifikan terhadap performa.

---

## 🔎 Insight Analysis

### Feature Importance

Faktor dominan:

* Kelengkapan fitur (Options_Full)
* Usia kendaraan (Car_Age)
* Engine_Size
* Make & Type

### SHAP Interpretation

Analisis SHAP menunjukkan hubungan non-linear:

* Kendaraan lebih baru → kontribusi positif signifikan
* Mesin besar → premium pricing
* Mileage tinggi → tekanan harga negatif
* Fitur lengkap → uplift harga

Model selaras dengan dinamika pasar riil.

---

## 📉 Error Analysis

Temuan utama:

* Performa kuat pada segmen harga menengah
* Underestimation pada mobil premium
* Overestimation pada mobil harga rendah
* Indikasi regression-to-the-mean effect

Akar penyebab:

* Distribusi target tidak seimbang
* Long-tail pricing behavior

---

## 💼 Business Implication

Model dapat digunakan untuk:

* Automated pricing assistance
* Benchmark harga listing
* Decision support untuk dealer
* Identifikasi faktor premium value

Namun untuk segmen premium, disarankan validasi tambahan karena volatilitas harga lebih tinggi.



Mau kita naikkan lagi levelnya sedikit supaya benar-benar kuat untuk recruiter Data Scientist?
