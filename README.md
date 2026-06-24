# Autonomous Voice AI Agent & Workflow Orchestrator

Selamat datang di repositori **Autonomous Voice AI Agent & Workflow Orchestrator**. Proyek ini merupakan sebuah *Personal Operating System* otonom berbasis kecerdasan buatan (AI) yang dibangun di atas platform **n8n**. Sistem ini dirancang secara khusus untuk menjembatani input manusia yang sepenuhnya tidak terstruktur—seperti pesan teks acak atau rekaman suara (*voice notes*) saat di perjalanan—menjadi data terstruktur yang mengeksekusi otomatisasi backend secara *real-time*.

Alih-alih mengandalkan satu model LLM besar yang lambat dan mahal untuk memproses segala hal, proyek ini menerapkan arsitektur *decoupled* yang berfokus pada optimasi biaya (*cost-performance*), latensi sangat rendah, serta penanganan integritas data yang ketat.

---

## 🛠️ Tech Stack & Integrasi Sistem

* **Workflow Orchestrator:** n8n
* **AI Inference Engine:** Groq API (Orkestrasi Dual-Model: Compound & Compound Mini)
* **Audio Transcription Framework:** AssemblyAI / Whisper API
* **Interface Gateway:** Telegram Bot API
* **Scripting & Data Manipulation:** JavaScript (Node.js) di dalam runtime n8n
* **Database & Productivity Ecosystem:** Google Workspace APIs (Google Sheets, Google Tasks, Google Calendar)
* **Data Extraction:** Autonomous Web Scraping Engine

---

## 📐 Arsitektur Sistem (n8n Blueprint Canvas)

Berikut adalah cetak biru (*blueprint*) dari seluruh jalur pipa data (*data pipeline*) dan arsitektur logika yang dirancang di dalam kanvas n8n:

![n8n Architecture Blueprint](assets/n8n_blueprint.jpeg)

---

## 🚀 Bukti Eksekusi & Antarmuka (Proof of Concept)

Sistem ini telah diuji secara langsung dan terbukti mampu melakukan pemrosesan bahasa alami (NLP) untuk mengekstrak entitas waktu, kalkulasi finansial, hingga melakukan sintesis data pasar eksternal:

![Telegram Interface Execution](assets/telegram_execution.jpeg)

---

## 🌟 Fitur Unggulan & Aliran Data (Data Flow)

1. **Multi-Modal Ingestion Pipeline:**
   Menangkap muatan (*payload*) berupa teks dan rekaman suara secara asinkron melalui *Telegram Trigger*. Jika input berupa audio, sistem secara dinamis akan melakukan decoding dan mengirimkannya ke framework transkripsi untuk diubah menjadi teks mentah dengan tingkat presisi tinggi.

2. **Dual-Model Intent Routing:**
   Ditenagai oleh kombinasi strategis antara model **Groq Compound** dan **Groq Compound Mini**. Model yang lebih ringan bertindak sebagai *router* cerdas dengan latensi di bawah satu detik (*sub-second latency*), yang secara instan mengklasifikasikan intensi user ke dalam **5 jalur eksekusi spesifik**:
   * **Notes:** Untuk penyimpanan ide, pemikiran acak, atau catatan konseptual.
   * **Schedules:** Konversi bahasa alami menjadi format waktu ISO standar untuk penjadwalan *Google Calendar*.
   * **Tasks:** Manajemen delegasi tugas langsung ke *Google Tasks*.
   * **Finance:** Pemrosesan matematika keuangan untuk memperbarui buku kas (*ledger*) lokal.
   * **Deep Research:** Pemicu mesin pencari data eksternal.

3. **Programmatic Data Transformation:**
   Menggunakan node kustom **JavaScript** untuk menangani manajemen *state* saat runtime, kalkulasi angka, dan pembersihan struktur data sebelum berinteraksi langsung dengan API eksternal agar mencegah kegagalan skema data.

4. **Automated Market Research Engine:**
   Ketika mendeteksi intensi riset (seperti pada contoh pengujian saham VKTR), workflow akan mengaktifkan cabang otomatisasi untuk melakukan *scraping* data, mengekstrak ringkasan profil perusahaan, serta menyajikan analisis kondisi finansial secara ringkas dan padat kembali ke pengguna.

5. **Resilient Operations & Audit Logging:**
   Dilengkapi dengan penanganan kesalahan (*error handling*) bawaan yang mengintersep batas kuota API (*API boundaries*) dan menuliskan log sukses/gagal ke dalam lembar audit untuk menjaga stabilitas pipeline jangka panjang.

---

## 🚀 Cara Melakukan Deploy pada Instance n8n Anda

1. **Clone Repositori Ini:**
   ```bash
   git clone [https://github.com/username/nama-repositori.git](https://github.com/username/nama-repositori.git)
