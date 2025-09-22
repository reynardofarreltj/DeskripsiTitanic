# Korelasi Variabel Terhadap Tingkat Keselamatan (Survival Rate) 🚢

Korelasi membantu kita memahami hubungan antara dua variabel. Nilainya berkisar dari -1 hingga 1:
* **Korelasi Positif (mendekati 1):** Jika satu variabel naik, variabel lainnya cenderung naik.
* **Korelasi Negatif (mendekati -1):** Jika satu variabel naik, variabel lainnya cenderung turun.
* **Korelasi Lemah (mendekati 0):** Hubungan antar variabel tidak kuat atau tidak linear.

Berikut penjelasannya untuk dataset Titanic:

---

### 1. Jenis Kelamin (`sex_numeric`)
* **Korelasi: -0.54 (Korelasi negatif yang kuat)**
* **Penjelasan:** Ini adalah prediktor terkuat untuk keselamatan. Dalam data, `sex_numeric` diberi nilai 0 untuk perempuan dan 1 untuk laki-laki. Korelasi negatif yang kuat ini berarti **laki-laki (nilai 1) memiliki tingkat keselamatan yang jauh lebih rendah** dibandingkan perempuan (nilai 0). Ini sangat sesuai dengan kebijakan "wanita dan anak-anak terlebih dahulu" saat evakuasi.

---

### 2. Kelas Penumpang (`pclass`)
* **Korelasi: -0.34 (Korelasi negatif sedang)**
* **Penjelasan:** Kelas penumpang juga menjadi faktor penting. `Pclass` bernilai 1 untuk Kelas Pertama, 2 untuk Kelas Kedua, dan 3 untuk Kelas Ketiga. Korelasi negatif menunjukkan bahwa **semakin tinggi nomor kelasnya (dari 1 ke 3), semakin rendah tingkat keselamatannya**. Penumpang Kelas Pertama memiliki akses yang lebih baik ke dek sekoci dan diprioritaskan saat evakuasi, sehingga tingkat keselamatan mereka paling tinggi.

---

### 3. Bepergian Sendiri (`is_alone`)
* **Korelasi: -0.20 (Korelasi negatif)**
* **Penjelasan:** Variabel baru ini menunjukkan bahwa **penumpang yang bepergian sendiri (`is_alone` = 1) memiliki tingkat keselamatan yang lebih rendah** daripada mereka yang bepergian bersama keluarga (`is_alone` = 0). Ini mendukung cerita bahwa memiliki keluarga memberikan keuntungan, kemungkinan karena saling membantu dan menjadi prioritas (terutama jika ada wanita atau anak-anak).

---

### 4. Tarif (`fare`)
* **Korelasi: 0.26 (Korelasi positif)**
* **Penjelasan:** Ada hubungan positif antara tarif tiket dan keselamatan. Artinya, **semakin mahal harga tiket seorang penumpang, semakin tinggi kemungkinan ia selamat**. Hal ini sangat masuk akal karena harga tiket yang mahal berkorelasi langsung dengan kelas yang lebih baik (`pclass` 1), yang memiliki tingkat keselamatan tertinggi.

---

### 5. Ukuran Keluarga (`family_size`)
* **Korelasi: 0.02 (Korelasi sangat lemah/hampir netral)**
* **Penjelasan:** Angka korelasi ini sedikit menipu jika dilihat sendirian. Meskipun korelasinya mendekati nol, visualisasi *bar plot* yang Anda buat menunjukkan cerita yang lebih dalam. Hubungannya tidak lurus (linear), melainkan melengkung:
    * **Keluarga Kecil (2-4 orang):** Memiliki tingkat keselamatan **tertinggi**.
    * **Sendirian (1 orang):** Tingkat keselamatannya lebih rendah.
    * **Keluarga Besar (lebih dari 4 orang):** Tingkat keselamatannya **paling rendah**, kemungkinan karena kesulitan untuk mengumpulkan semua anggota keluarga di tengah kepanikan.
    Karena tingkat keselamatan naik lalu turun, korelasi linearnya menjadi hampir nol.

---

### 6. Umur (`age`)
* **Korelasi: -0.08 (Korelasi negatif sangat lemah)**
* **Penjelasan:** Seperti `family_size`, hubungan antara umur dan keselamatan juga tidak sepenuhnya linear. Korelasi yang lemah ini disebabkan karena **anak-anak memiliki tingkat keselamatan yang tinggi**, sementara orang dewasa dan lansia memiliki tingkat yang lebih rendah. Efek-efek yang berlawanan ini membuat korelasi secara keseluruhan menjadi lemah.
