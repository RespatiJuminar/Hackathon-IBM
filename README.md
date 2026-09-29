# Hackathon-IBM
# CampusCare AI: Asisten Akademik & Pendamping Kesehatan Mental Mahasiswa

## Deskripsi Proyek
CampusCare AI adalah platform pendamping mahasiswa berbasis AI yang menggabungkan dua fungsi utama:
1. Asisten Akademik Cerdas: Menjawab pertanyaan seputar pedoman akademik, skripsi, dan konsep mata kuliah (contoh: "Apa itu nested loop?") menggunakan teknologi RAG (Retrieval-Augmented Generation).
2. Pendamping Emosional (Curhat): Menjadi teman curhat yang empatik, mendeteksi emosi dari teks pengguna, dan diwujudkan dalam avatar 3D yang ekspresif.

## Fitur Utama
- Intent Router (Flow 0): Mengklasifikasikan pertanyaan pengguna secara otomatis (Akademik vs Curhat).
- Academic RAG (Flow 1): Mencari jawaban dari dokumen PDF pedoman akademik/skripsi dan materi kuliah.
- Emotional Support (Flow 2): Memberikan respons empatik dan mendeteksi emosi (stres, sedih, senang) untuk menggerakkan avatar 3D.
- Avatar 3D Interaktif: Model 3D yang dapat berbicara (Text-to-Speech) dan mengekspresikan emosi.

## Tech Stack
- AI Orchestration: [Langflow](https://www.langflow.org/)
- LLM Provider: Gemini 3.5-Flash
- Development Partner: IBM Bob (AI-assisted coding & testing)
- Vector Database: Astra DB (DataStax)
- Frontend: React.js / Flutter (dalam pengembangan)
- Avatar 3D: Three.js / VRM Model + NVIDIA Audio2Face (rencana)

## Arsitektur Sistem (Blueprint)
Proyek ini menggunakan 3 flow utama di Langflow:
1. Flow 0 - Intent Router: `Chat Input` → `Prompt Template` → `Gemini.ai` → `Label Router (Custom Component by IBM Bob)` → `If-Else`.
2. Flow 1 - Academic Assistant: `Chat Input` → `Astra DB (RAG)` → `Prompt Template` → `watsonx.ai` → `Chat Output`.
3. Flow 2 - Emotional Support: `Chat Input` → `Prompt Template (Empathy)` → `watsonx.ai` → `Parser (Emotion Tag)` → `Chat Output`.

*(Lihat folder `docs/` untuk diagram arsitektur dan screenshot Langflow)*

##  Cara Menjalankan (Local Setup)
1. Clone repositori ini.
2. Import file `.json` dari folder `langflow_flows/` ke dalam Langflow Desktop/Web.
3. Masukkan kredensial API Key (IBM Cloud, Astra DB, Gemini untuk fallback) di pengaturan komponen.
4. Jalankan Playground di Langflow untuk menguji flow.

## Tim Kuliah tipis tipis
- [Raditya Aji Respati Juminar] - [Ketua]

## Status Proyek Saat Ini
- [x] Ide & Business Canvas
- [x] Sertifikasi IBM SkillsBuild
- [ ] Prototype Flow 0 (Intent Router) - *Dalam Pengerjaan*
- [ ] Prototype Flow 1 (Academic RAG) - *Dalam Pengerjaan*
- [ ] Prototype Flow 2 (Emotional Support) - *Dalam Pengerjaan*
- [ ] Integrasi Frontend & Avatar 3D
