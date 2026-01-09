# 📊 Retail Sales Performance Dashboard 2024

## 📌 Executive Summary
Proyek ini menganalisis performa penjualan ritel sepanjang tahun 2024 di empat kanal utama: **Shopee, Tokopedia, Website, dan Toko Offline**. Melalui analisis 10 dimensi data, proyek ini memberikan insight strategis mengenai profitabilitas, perilaku konsumen, efisiensi logistik, dan loyalitas brand untuk mendukung pengambilan keputusan berbasis data di tahun 2026.

---

## 📊 Dataset Information
Dataset yang digunakan dalam proyek ini bersumber dari Kaggle yang mencakup data transaksi retail sepanjang tahun 2024. Dataset ini telah melalui tahap pembersihan (*data cleaning*) dan pengayaan (*feature engineering*).

🔗 **Download Dataset:** [Indonesian Retail Sales & Cost Dataset](https://www.kaggle.com/datasets/lycusbendln/indonesian-retail-sales-and-cost-dataset)
---

## 🚀 Key Insights
*   **💰 Profitability Leader**: Toko Offline menyumbang margin profit tertinggi sebesar **54%**, menjadikannya kanal paling efisien secara biaya.
*   **👗 Product Hegemony**: Produk dengan identitas "Lokal" dan "Batik" (seperti *Dress Batik Modern*) mendominasi Top 5 Best-Seller, membuktikan kekuatan *Cultural Power* di pasar Indonesia.
*   **👥 Customer Demographics**: Target pasar utama adalah kelompok usia **25-34 tahun (Milenial)** yang menyumbang ~35% dari total transaksi di kedua gender.
*   **🚚 Logistics Zoning**: Biaya pengiriman terbagi menjadi 3 klaster harga (Rp12k, Rp16k, Rp26k). Wilayah luar Jawa (Tier 3) memerlukan strategi margin yang lebih tebal.
*   **⏰ Peak Operations**: Volume transaksi mencapai puncak pada **Jam Siang (11:00 - 16:00)**, terutama pada hari Rabu.

---

## 💡 Business Recommendations
Berdasarkan analisis data di atas, berikut adalah rekomendasi strategis untuk meningkatkan performa bisnis di tahun mendatang:

1. **Optimasi Profit via Kanal Mandiri:** Mengingat **Toko Offline** dan **Website** memiliki margin tertinggi (karena rendahnya biaya platform), perusahaan harus mulai mengalihkan trafik dari Marketplace ke Website melalui program loyalitas khusus web.
2. **Targeting Milenial:** Fokuskan budget iklan pada kelompok usia **25-34 tahun** dengan gaya konten yang relevan dengan tren milenial, karena segmen ini adalah penyumbang order terbesar (~35%).
3. **Strategi Stok Produk Lokal:** Terus kembangkan varian produk berbasis batik/lokal karena terbukti memiliki *product-market fit* yang kuat dan menjadi *top contributor* profit di semua kanal.
4. **Logistics Cost Management:** Untuk pengiriman ke luar Jawa (Tier 3), disarankan untuk menaikkan ambang batas "Gratis Ongkir" guna menutupi rata-rata biaya kirim yang mencapai Rp26.000 agar tidak menggerus margin produk.
5. **Konversi Non-Member:** Segmen Non-Member menyumbang profit besar (Rp5,6M). Perusahaan perlu meluncurkan kampanye *membership* yang agresif (misal: diskon pertama untuk member) untuk mengubah pembeli organik menjadi pelanggan setia.

---

### 🧱 Data Dictionary & Preparation
Berikut adalah rincian kolom yang terdapat dalam dataset ini, termasuk kolom hasil *Feature Engineering* (ditandai dengan ⭐):

| Kolom | Deskripsi | Tipe Data |
| :--- | :--- | :--- |
| **order_id** | ID unik untuk setiap transaksi. | String/ID |
| **tanggal_transaksi** | Waktu terjadinya transaksi. | DateTime |
| **channel_penjualan** | Kanal transaksi (Toko, Shopee, Tokopedia, Website). | Category |
| **nama_produk** | Nama produk retail lokal. | String |
| **qty** | Jumlah item terjual. | Integer |
| **harga_list** | Harga normal produk (sebelum diskon). | Currency |
| **harga_jual** | Harga jual akhir ke pelanggan. | Currency |
| **total_penjualan** | Total nilai pendapatan per transaksi. | Currency |
| **total_biaya** | Total beban (Produksi + Kirim + Platform). | Currency |
| **profit** | Keuntungan bersih per transaksi. | Currency |
| **metode_pembayaran**| Metode yang digunakan (Kartu Kredit, QRIS, dll). | Category |
| **event_promo** | Status kampanye promosi. | String |
| **Waktu Hari** ⭐ | **[Feature Engineering]** Kategorisasi jam transaksi (Pagi-Malam). | Category |
| **is_promo** ⭐ | **[Feature Engineering]** Status promo vs transaksi organik. | Category |

---

## 🛠️ Dataset & Feature Engineering
Selain mengolah data mentah, saya melakukan proses *feature engineering* untuk menambahkan dimensi analisis baru yang relevan dengan kebutuhan bisnis:

| Nama Kolom | Logika / Rumus | Deskripsi Bisnis |
| :--- | :--- | :--- |
| **Waktu Hari** | `=IFS(jam<11,"Pagi",jam<16,"Siang",jam<19,"Sore",jam<=23,"Malam", TRUE,"Dini Hari")` | Mengelompokkan jam transaksi ke dalam 4 zona waktu untuk mengidentifikasi jam operasional paling sibuk (*Peak Hours*). |
| **is_promo** | `=IF(event_promo="Normal","No Promo","Promo Event")` | Mengidentifikasi transaksi yang terjadi selama periode kampanye besar vs transaksi organik pada harga normal. |

---

## 🖼️ Dashboard Preview
*Klik pada setiap kategori di bawah ini untuk melihat detail visualisasi dashboard.*

<details>
  <summary><b>📈 Sheet 01: Profitability Overview</b></summary>
  <blockquote align="center">
    <img src="screenshot/the profit gap.png" alt="Profit Analysis" width="900">
    <br><i>Insight: Toko Offline memimpin efisiensi biaya dengan margin keuntungan sebesar 54%.</i>
  </blockquote>
</details>

<details>
  <summary><b>🛍️ Sheet 02: Cultural Power (Product Analysis)</b></summary>
  <blockquote align="center">
    <img src="screenshot/cultural powewr.png" alt="Product Analysis" width="900">
    <br><i>Insight: Dominasi produk batik modern menunjukkan kuatnya preferensi pasar terhadap identitas lokal.</i>
  </blockquote>
</details>

<details>
  <summary><b>🚚 Sheet 03: Logistics Zoning Efficiency</b></summary>
  <blockquote align="center">
    <img src="screenshot/logistic zooning.png" alt="Logistics Analysis" width="900">
    <br><i>Insight: Pemetaan klaster biaya pengiriman untuk optimasi margin di wilayah Luar Jawa.</i>
  </blockquote>
</details>

<details>
  <summary><b>🔥 Sheet 04: Peak Operations Heatmap</b></summary>
  <blockquote align="center">
    <img src="screenshot/peak hours.png" alt="Peak Hours" width="900">
    <br><i>Insight: Volume transaksi tertinggi terkonsentrasi pada hari Rabu di jam makan siang (11:00 - 16:00).</i>
  </blockquote>
</details>

<details>
  <summary><b>💎 Sheet 05: Brand Loyalty & Retention</b></summary>
  <blockquote align="center">
    <img src="screenshot/brand loyalty.png" alt="Brand Loyalty" width="900">
    <br><i>Insight: Analisis tingkat pembelian berulang dan loyalitas konsumen terhadap brand.</i>
  </blockquote>
</details>

<details>
  <summary><b>👥 Sheet 06: Customer Profile (Demographics)</b></summary>
  <blockquote align="center">
    <img src="screenshot/customer profile.png" alt="Customer Profile" width="900">
    <br><i>Insight: Demografi utama didominasi oleh kelompok usia 25-34 tahun (Milenial).</i>
  </blockquote>
</details>

<details>
  <summary><b>🌟 Sheet 07: Member Value Analysis</b></summary>
  <blockquote align="center">
    <img src="screenshot/member value.png" alt="Member Value" width="900">
    <br><i>Insight: Perbandingan nilai transaksi antara pelanggan Member vs Non-Member.</i>
  </blockquote>
</details>

<details>
  <summary><b>💳 Sheet 08: Payment Behavior</b></summary>
  <blockquote align="center">
    <img src="screenshot/payment behavior.png" alt="Payment Behavior" width="900">
    <br><i>Insight: Preferensi metode pembayaran yang paling sering digunakan oleh konsumen di berbagai channel.</i>
  </blockquote>
</details>

<details>
  <summary><b>💻 Sheet 09: Platform Efficiency</b></summary>
  <blockquote align="center">
    <img src="screenshot/platform efficiency.png" alt="Platform Efficiency" width="900">
    <br><i>Insight: Evaluasi performa teknis dan konversi penjualan di masing-masing platform digital.</i>
  </blockquote>
</details>

<details>
  <summary><b>📅 Sheet 10: Annual Sales Trend 2024</b></summary>
  <blockquote align="center">
    <img src="screenshot/sales trend 2024.png" alt="Sales Trend" width="900">
    <br><i>Insight: Visualisasi pertumbuhan penjualan bulanan sepanjang tahun 2024 untuk proyeksi tahun 2026.</i>
  </blockquote>
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
*   **LinkedIn**: [Ardiansyah Putra](https://www.linkedin.com/in/ardiansyah-putra-7746a0280)
