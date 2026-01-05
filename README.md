# 📊 Retail Sales Performance Dashboard 2024

## 📌 Executive Summary
Proyek ini menganalisis performa penjualan ritel sepanjang tahun 2024 di empat kanal utama: **Shopee, Tokopedia, Website, dan Toko Offline**. Melalui analisis 10 dimensi data, proyek ini memberikan insight strategis mengenai profitabilitas, perilaku konsumen, efisiensi logistik, dan loyalitas brand untuk mendukung pengambilan keputusan berbasis data di tahun 2026.

---

## 🚀 Key Insights
*   **💰 Profitability Leader**: Toko Offline menyumbang margin profit tertinggi sebesar **54%**, menjadikannya kanal paling efisien secara biaya.
*   **👗 Product Hegemony**: Produk dengan identitas "Lokal" dan "Batik" (seperti *Dress Batik Modern*) mendominasi Top 5 Best-Seller, membuktikan kekuatan *Cultural Power* di pasar Indonesia.
*   **👥 Customer Demographics**: Target pasar utama adalah kelompok usia **25-34 tahun (Milenial)** yang menyumbang ~35% dari total transaksi di kedua gender.
*   **🚚 Logistics Zoning**: Biaya pengiriman terbagi menjadi 3 klaster harga (Rp12k, Rp16k, Rp26k). Wilayah luar Jawa (Tier 3) memerlukan strategi margin yang lebih tebal.
*   **⏰ Peak Operations**: Volume transaksi mencapai puncak pada **Jam Siang (11:00 - 16:00)**, terutama pada hari Rabu.

---

## 🛠️ Dataset & Feature Engineering
Selain mengolah data mentah, saya melakukan proses *feature engineering* untuk menambahkan dimensi analisis baru yang relevan dengan kebutuhan bisnis:

| Nama Kolom | Logika / Rumus | Deskripsi Bisnis |
| :--- | :--- | :--- |
| **Waktu Hari** | `=IFS(jam<11,"Pagi",jam<16,"Siang",jam<19,"Sore",jam<=23,"Malam", TRUE,"Dini Hari")` | Mengelompokkan jam transaksi ke dalam 4 zona waktu untuk mengidentifikasi jam operasional paling sibuk (*Peak Hours*). |
| **is_promo** | `=IF(event_promo="Normal","No Promo","Promo Event")` | Mengidentifikasi transaksi yang terjadi selama periode kampanye besar vs transaksi organik pada harga normal. |

---

## 🖼️ Dashboard Preview
*Klik pada setiap kategori untuk melihat detail visualisasi.*

<details>
  <summary><b>📈 Sheet 1: Profitability Overview</b></summary>
  <p align="center">
    <img src="screenshots/sheet1.png" width="800">
    <br><i>Analisis profit per channel: Toko Offline memimpin dengan margin 54%.</i>
  </p>
</details>

<details>
  <summary><b>🛍️ Sheet 2: Cultural Power (Product Analysis)</b></summary>
  <p align="center">
    <img src="screenshots/sheet2.png" width="800">
  </p>
</details>

<details>
  <summary><b>🚚 Sheet 3: Logistics Zoning</b></summary>
  <p align="center">
    <img src="screenshots/sheet3.png" width="800">
  </p>
</details>

<details>
  <summary><b>🔥 Sheet 4: Peak Hours Heatmap</b></summary>
  <p align="center">
    <img src="screenshots/sheet4.png" width="800">
  </p>
</details>

<details>
  <summary><b>📊 Sheet 10: Sales Trend 2024 (Growth Analysis)</b></summary>
  <p align="center">
    <img src="screenshots/sheet10.png" width="800">
  </p>
</details>

---

## 💻 Tech Stack
*   **Microsoft Excel**: Data Cleaning, Pivot Tables, Power Pivot, & Data Modeling.
*   **Data Visualization**: Conditional Formatting (Heatmaps), Slicers, & Dynamic Charts.

---

## 🧭 How to Navigate the Dashboard
Dashboard ini dirancang secara interaktif untuk kebutuhan manajerial:
*   **Profit & Product (Sheet 1-2)**: Fokus pada profitabilitas kanal dan kekuatan produk.
*   **Logistics & Promo (Sheet 3-5)**: Analisis logistik, tren waktu belanja, dan efektivitas promo.
*   **Demographics & Platform (Sheet 6-9)**: Profil demografi, loyalitas member, perilaku pembayaran, dan efisiensi platform.
*   **Annual Growth (Sheet 10)**: Ringkasan tren penjualan tahunan untuk evaluasi pertumbuhan.

---

## 📬 Contact & Documentation
Jika Anda memiliki pertanyaan mengenai metodologi atau ingin berdiskusi lebih lanjut:
*   **Portfolio**: [Link Portfolio Anda](https://link-anda.com)
*   **LinkedIn**: [Nama LinkedIn Anda](linkedin.com)
