# ✨ VoiceCommand MFCC 1D CNN EdgeImpulse

[![Language: C++](https://img.shields.io/badge/Language-C%2B%2B-blue.svg)](https://isocpp.org/)
[![Platform: EdgeImpulse](https://img.shields.io/badge/Platform-EdgeImpulse-informational.svg)](https://www.edgeimpulse.com/)
[![Platform: Arduino](https://img.shields.io/badge/Platform-Arduino-00979D.svg)](https://www.arduino.cc/)

> Proyek ini mendemonstrasikan implementasi pengenalan perintah suara menggunakan ekstraksi fitur Mel-frequency cepstral coefficients (MFCC) dengan Convolutional Neural Network (1D CNN) yang dikerahkan melalui EdgeImpulse, ideal untuk aplikasi perangkat edge berbasis mikrokontroler.

## ✨ Fitur Utama

*   **Pengenalan Perintah Suara:** Menerapkan sistem yang kuat untuk mendeteksi dan menginterpretasikan perintah suara yakni: "maju", "mundur", "kanan", "kiri" dan "stop", cocok untuk aplikasi interaksi suara.
*   **Ekstraksi Fitur MFCC:** Memanfaatkan koefisien cepstral frekuensi Mel untuk merepresentasikan sinyal audio secara efisien, menangkap karakteristik penting untuk klasifikasi suara yang akurat.
*   **Klasifikasi Jaringan Saraf Konvolusional 1D (CNN):** Menggunakan arsitektur CNN satu dimensi yang dioptimalkan untuk tugas klasifikasi urutan, memungkinkan pemrosesan data audio yang canggih secara lokal.
*   **Pengerahan EdgeImpulse:** Memanfaatkan platform EdgeImpulse untuk siklus hidup pengembangan, pelatihan, dan pengerahan model pembelajaran mesin yang mulus ke perangkat edge, memastikan efisiensi dan kompatibilitas sumber daya.
*   **Penerapan Perangkat Edge (Arduino):** Kode inti dirancang untuk platform Arduino (`.ino` file), memfasilitasi pengerahan langsung model pengenalan suara ke mikrokontroler dengan sumber daya terbatas.
*   **Artefak Proyek EdgeImpulse:** Menyertakan paket pengerahan EdgeImpulse siap pakai (`ei-meeeloown-project-1-arduino-1.0.1-impulse-#1.zip`) untuk integrasi mudah ke lingkungan pengembangan Arduino Anda.
*   **Metrik Evaluasi Model:** Menyediakan metrik evaluasi model terperinci (`ei-meeeloown-project-1-classifier-model-evaluation-metrics-json-file-model.3.json`) untuk analisis kinerja dan penyempurnaan model.

## 🛠️ Tumpukan Teknologi

| Kategori              | Teknologi         | Catatan                                                                                                                                                                                                    |
| :-------------------- | :---------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Bahasa Pemrograman** | C++               | Bahasa utama yang digunakan untuk implementasi perangkat keras dan firmware, khususnya untuk mikrokontroler Arduino.                                                                                         |
| **Platform ML Edge**  | EdgeImpulse       | Platform terkemuka untuk membangun dan mengerahkan model pembelajaran mesin yang dioptimalkan untuk perangkat edge, digunakan untuk pengembangan model pengenalan suara.                                         |
| **Platform Hardware** | Arduino           | Lingkungan mikrokontroler target untuk pengerahan model pengenalan suara, didukung oleh EdgeImpulse.                                                                                                        |
| **Algoritma ML**      | 1D CNN            | Jenis arsitektur jaringan saraf konvolusional yang digunakan untuk pemrosesan data sekuensial (seperti audio MFCC) dan tugas klasifikasi.                                                                   |
| **Ekstraksi Fitur**   | MFCC              | Teknik standar dalam pemrosesan sinyal audio untuk mengekstraksi representasi fitur yang ringkas dari ucapan, yang kemudian dapat digunakan sebagai input untuk model ML.                                     |

## 🏛️ Tinjauan Arsitektur

Proyek ini mengadopsi arsitektur inferensi edge, di mana model pembelajaran mesin dilatih di cloud (melalui EdgeImpulse) dan kemudian mengerahkan perangkat keras dengan sumber daya terbatas (misalnya, papan Arduino). Prosesnya melibatkan:

1.  **Pengambilan Data & Pra-pemrosesan:** Data audio (perintah suara) dikumpulkan dan di-pra-proses.
2.  **Ekstraksi Fitur:** Fitur Mel-frequency cepstral coefficients (MFCC) diekstraksi dari data audio, mengubah bentuk gelombang mentah menjadi representasi yang lebih ringkas dan relevan secara diskriminatif.
3.  **Pelatihan Model (EdgeImpulse):** Fitur MFCC ini digunakan untuk melatih model Convolutional Neural Network 1D (1D CNN) dalam lingkungan EdgeImpulse. EdgeImpulse mengoptimalkan model untuk batasan perangkat edge.
4.  **Pengerahan Model:** Model yang telah dilatih dikemas oleh EdgeImpulse menjadi pustaka yang dapat digunakan pada perangkat Arduino.
5.  **Inferensi Edge (Arduino):** Kode Arduino (`MAIN_voiceCommand.ino`) menjalankan pustaka yang disebarkan. Ia terus-menerus mengambil data audio, mengekstrak fitur MFCC secara lokal, dan memasukkannya ke model 1D CNN untuk mengklasifikasikan perintah suara secara real-time.

Arsitektur ini memastikan latensi rendah, privasi data, dan efisiensi daya dengan melakukan inferensi langsung di perangkat.

## 🚀 Memulai

Untuk memulai proyek ini, ikuti langkah-langkah di bawah ini:

1.  **Kloning Repositori:**

    ```bash
    git clone https://github.com/meeeloown/voiceCommand-MFCC-1D-CNN-edgeImpulse.git
    cd voiceCommand-MFCC-1D-CNN-edgeImpulse
    ```

2.  **Instalasi Dependensi (Jika Ada Komponen Node.js):**
    Meskipun inti proyek adalah C++/Arduino, ada kemungkinan beberapa perkakas atau skrip manajemen proyek menggunakan Node.js.

    ```bash
    npm install
    ```

3.  **Memulai Pengembangan (Jika Ada Komponen Node.js):**
    Jika ada bagian proyek yang memerlukan server pengembangan Node.js (misalnya, untuk visualisasi atau pengujian simulasi), gunakan perintah berikut:

    ```bash
    npm run dev
    ```
    
    > **Catatan Penting:** Proyek utama (`MAIN_voiceCommand.ino`) adalah kode Arduino dan memerlukan Lingkungan Pengembangan Terpadu (IDE) Arduino. Anda mungkin perlu mengimpor pustaka EdgeImpulse yang dihasilkan (`ei-meeeloown-project-1-arduino-1.0.1-impulse-#1.zip`) ke IDE Arduino Anda, menginstal dependensi papan yang diperlukan, dan mengunggah kode ke papan Arduino Anda.

## 📂 Struktur File

```
/
├── MAIN_voiceCommand.ino
├── README.md
├── ei-meeeloown-project-1-arduino-1.0.1-impulse-#1.zip
└── ei-meeeloown-project-1-classifier-model-evaluation-metrics-json-file-model.3.json
```

*   **/ (Root Directory):** Berisi semua file proyek. Ini adalah repositori yang relatif datar, berfokus pada file-file penting yang diperlukan untuk proyek perintah suara.
    *   **`MAIN_voiceCommand.ino`**: File sketsa Arduino utama yang berisi logika untuk pengenalan perintah suara, integrasi dengan model EdgeImpulse, dan kontrol perangkat keras.
    *   **`README.md`**: File dokumentasi utama proyek yang sedang Anda baca.
    *   **`ei-meeeloown-project-1-arduino-1.0.1-impulse-#1.zip`**: Arsip ZIP berisi pustaka atau proyek EdgeImpulse yang diekspor, siap untuk diimpor dan digunakan dalam lingkungan pengembangan Arduino. Ini mewakili model ML yang dilatih dan pra-konfigurasi untuk pengerahan edge.
    *   **`ei-meeeloown-project-1-classifier-model-evaluation-metrics-json-file-model.3.json`**: File JSON yang merinci metrik evaluasi dan kinerja model klasifikasi. Ini memberikan wawasan tentang seberapa baik model yang dilatih melakukan tugas pengenalan suara.
