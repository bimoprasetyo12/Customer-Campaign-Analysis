# 📊 Marketing Campaign Analysis — Python & Power BI

![Dashboard Preview](Visuals/Marketing-Customer-Analysis.png)

---

## 🎯 Overview
Proyek ini menganalisis performa kampanye pemasaran menggunakan kombinasi **Python** (untuk data cleaning & analisis) dan **Power BI** (untuk visualisasi interaktif).  
Tujuannya adalah untuk memahami pola pelanggan, efektivitas channel marketing, serta karakteristik pelanggan yang paling responsif terhadap promosi.

Proyek ini dibuat sebagai bagian dari **portofolio Data Analyst / Business Intelligence**, menampilkan keterampilan end-to-end mulai dari data preprocessing hingga dashboard profesional.

---

## 🧠 Business Objectives
- Mengidentifikasi **segmen pelanggan paling responsif** terhadap kampanye.
- Menemukan **channel promosi paling efektif** berdasarkan data aktual.
- Menganalisis hubungan antara **income, umur, dan spending**.
- Menyajikan hasil dalam **dashboard Power BI bergaya minimalis bisnis.**

---

## 🧰 Tools & Technologies
| Tools / Library | Deskripsi |
|------------------|------------|
| 🐍 **Python (Pandas, NumPy, Matplotlib)** | Data cleaning & exploratory data analysis |
| 📊 **Power BI** | Visualisasi interaktif, DAX calculation, dan data modeling |
| 💾 **CSV Dataset** | Data kampanye pemasaran (umur, pendapatan, spending, channel, response) |
| 🧱 **GitHub** | Version control & portofolio publik |

---

## 📁 Project Structure
```

Marketing-Campaign-Analysis/
│
├── Data/
│   ├── marketing_campaign.csv               # Raw dataset
│   └── marketing_campaign_cleaned.csv       # Cleaned dataset (output dari Python)
│
├── Notebooks/
│   └── cleaning_analysis.ipynb              # Data cleaning & EDA
│
├── Dashboard/
│   └── Marketing_Campaign_Analysis.pbix     # Power BI dashboard
│
├── Visuals/
│   └── Marketing-Customer-Analysis.png      # Gambar preview dashboard
│
└── README.md                                # Dokumentasi utama proyek

````

---

## 🧹 Data Preparation (Python)
Langkah-langkah utama pada proses pembersihan data:

```python
import pandas as pd

# Load dataset
df = pd.read_csv("../Data/marketing_campaign.csv")

# Cleaning
df.drop_duplicates(inplace=True)
df.dropna(subset=["Age", "Income"], inplace=True)
df.columns = df.columns.str.strip().str.replace(" ", "_").str.lower()

# Feature engineering
bins = [18, 30, 40, 50, 60, 100]
labels = ["20s", "30s", "40s", "50s", "60+"]
df["age_group"] = pd.cut(df["age"], bins=bins, labels=labels)

# Export cleaned data
df.to_csv("../Data/marketing_campaign_cleaned.csv", index=False)
````

---

## 🧩 Power BI Dashboard

Dashboard ini dibuat untuk menyajikan insight dengan visualisasi minimalis dan efisien.

### 🔹 Key Visuals

| Visual           | Tujuan                                                                    |
| ---------------- | ------------------------------------------------------------------------- |
| **Card Metrics** | Menampilkan total pelanggan, rata-rata pendapatan, dan rata-rata spending |
| **Bar Chart**    | Menunjukkan tingkat respons per channel                                   |
| **Donut Chart**  | Distribusi campaign berdasarkan tipe                                      |
| **Column Chart** | Spending rata-rata berdasarkan kelompok umur                              |
| **Line Chart**   | Tren akuisisi pelanggan per bulan                                         |
| **Table View**   | Detail pelanggan dan performa campaign                                    |

---

### 🔹 DAX Measures

```DAX
Total Customers = DISTINCTCOUNT('marketing_campaign_cleaned'[CustomerID])
Total Spending = SUM('marketing_campaign_cleaned'[Spent])
Average Income = AVERAGE('marketing_campaign_cleaned'[Income])
Response Rate (%) = AVERAGE('marketing_campaign_cleaned'[Response]) * 100
```

---

### 🎨 Dashboard Design

* **Tema:** Minimalist Business (Putih, Abu muda, Biru keabu-abuan)
* **Font:** Segoe UI / Lato
* **Layout:** 2 baris × 3 kolom visual
* **Fokus:** Clean spacing, no gridlines, readable insight-first design.

---

## 📊 Key Insights

* 💡 **Response Rate 18.2%** — tertinggi pada *Social Media Channel*
* 🎯 **Campaign “Discount”** menunjukkan performa 2× lebih baik dibanding tipe lainnya
* 👥 Pelanggan berusia **30–40 tahun** paling aktif berbelanja dan merespons kampanye
* 💵 Pelanggan yang merespons memiliki **rata-rata income 25% lebih tinggi**
* 📆 Aktivitas pembelian meningkat signifikan di kuartal 4 (Q4)

---

## 🚀 How to Reproduce

1. Clone repository:

   ```bash
   git clone https://github.com/<username>/Marketing-Campaign-Analysis.git
   ```
2. Buka folder project:

   ```bash
   cd Marketing-Campaign-Analysis
   ```
3. Jalankan notebook:

   ```bash
   jupyter notebook notebooks/cleaning_analysis.ipynb
   ```
4. Buka **Power BI → Get Data → CSV →** pilih `marketing_campaign_cleaned.csv`
5. Gunakan DAX formulas dan layout sesuai panduan di atas
6. Simpan hasil sebagai `Dashboard/Marketing-Campaign-Analysis.pbix`

---

## 📷 Dashboard Preview

![Dashboard](Visuals/Marketing-Campaign-Analysis.png)

> Tema: Minimalist Business
> Tools: Power BI + Python
> Fokus: Clarity, konsistensi, dan insight-driven storytelling

---

## 🧾 Summary

Proyek ini menunjukkan bagaimana pendekatan **data-driven marketing** membantu tim memahami pelanggan, mengukur efektivitas kampanye, dan meningkatkan ROI.
Dengan kombinasi **Python + Power BI**, data mentah diubah menjadi insight bisnis yang actionable dan visual yang menarik.

---

## 👤 Author

**WorkArsip**
💼 *Data Analyst | Business Intelligence Enthusiast*
📧 [bimoprasetyosoleh@gmail.com](mailto:bimoprasetyosoleh@gmail.com)
🌐 [GitHub Portfolio](https://github.com/<bimoprasetyo12>)
🔗 [LinkedIn](www.linkedin.com/in/bimo-prasetyo-soleh-600579269)

---

### 📄 License

This project is licensed under the MIT License — feel free to fork and adapt with credit.
