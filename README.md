# 🎙️ Vox Convert

**Vox Convert** is a professional, open-source **Speech-to-Text transcription** web app. It combines a modern React frontend with a Python/Flask backend powered by the [`SpeechRecognition`](https://pypi.org/project/SpeechRecognition/) library.

Speak into your microphone or upload an audio file — Vox Convert turns your voice into clean, editable text in seconds.

![Vox Convert](https://img.shields.io/badge/Vox_Convert-v1.0-6366f1?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0id2hpdGUiPjxwYXRoIGQ9Ik0xMiAxNWEzIDMgMCAwIDAgMy0zVjZhMyAzIDAgMCAwLTYgMHY2YTMgMyAwIDAgMCAzIDN6bTUuMzctMUE1LjUgNS41IDAgMCAxIDYuNSAxNEg1YTYuNSA2LjUgMCAwIDAgMTMuMTYuNUgxOXYtMS4xaC0xLjYzWk0xMSA0aDJ2MTJoLTJWNFoiLz48L3N2Zz4=)
![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-3.0-black?style=for-the-badge&logo=flask)
![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)

---

## ✨ Features

- 🎤 **Live microphone transcription** — uses your browser's built-in Web Speech API (no backend required).
- 📁 **Audio file upload** — sends files to the Python backend which uses `SpeechRecognition` (Google / Sphinx engines).
- 🌍 **9+ languages** — English, Hindi, Spanish, French, German, Japanese, Chinese, Arabic and more.
- 📝 **Editable transcript** — refine results directly in the UI.
- 📋 **Copy & Download** — one-click copy to clipboard or export as `.txt`.
- 📊 **Live stats** — word & character counts, transcription timer.
- 🎨 **Beautiful UI** — animated gradient aurora, glassmorphism cards, dark theme.
- 🔌 **Connection indicator** — shows if the Python backend is reachable.

---

## 🧰 Tech Stack

| Layer       | Technology                                  |
| ----------- | ------------------------------------------- |
| Frontend    | React 19, TypeScript, Vite, Tailwind CSS    |
| Backend     | Python 3, Flask, Flask-CORS                 |
| Recognition | SpeechRecognition library (Google, Sphinx)  |
| Audio       | pydub + ffmpeg (optional, for non-WAV files)|
| Icons       | Lucide React                                |

---

## 🚀 Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/vox-convert.git
cd vox-convert
```

### 2. Start the Python backend

```bash
cd backend
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate
pip install -r requirements.txt
python app.py
```

The backend will start on **http://localhost:5000**.
> 🎵 For MP3/M4A/FLAC uploads, also install [ffmpeg](https://ffmpeg.org/download.html) on your system.

### 3. Start the frontend

From the project root (in a separate terminal):

```bash
npm install
npm run dev
```

Open **http://localhost:5173** — and start talking! 🎙️

> 💡 **Tip:** The "Live Microphone" tab works without the Python backend (uses your browser). Only the "Upload Audio File" tab needs the backend running.

---

## 📡 API Reference

The Python backend exposes two endpoints:

### `GET /health`
Health check.

```json
{ "status": "ok", "service": "vox-convert" }
```

### `POST /transcribe`
Upload an audio file.

- **Content-Type:** `multipart/form-data`
- **Field:** `file`

**Response:**

```json
{
  "text": "Hello world, this is a test.",
  "engine": "google",
  "filename": "recording.wav",
  "seconds": 1.204
}
```

---

## 📂 Project Structure

```
vox-convert/
├── backend/
│   ├── app.py              # Flask server
│   └── requirements.txt    # Python dependencies
├── src/
│   ├── App.tsx
│   ├── main.tsx
│   ├── index.css
│   └── components/
│       ├── Header.tsx
│       ├── ModeTabs.tsx
│       ├── LiveTranscription.tsx
│       ├── FileUpload.tsx
│       ├── TranscriptPanel.tsx
│       ├── BackendStatus.tsx
│       └── Footer.tsx
├── index.html
├── package.json
├── vite.config.ts
├── tsconfig.json
└── README.md
```

---

## 🛠 Build for production

```bash
npm run build
```

The static site is generated in `dist/`. Serve it with any static host (Netlify, Vercel, GitHub Pages, nginx, etc.).

---

## 🤝 Contributing

Contributions are welcome! To get started:

1. Fork the repo
2. Create a feature branch: `git checkout -b feat/amazing-feature`
3. Commit your changes: `git commit -m "feat: add amazing feature"`
4. Push: `git push origin feat/amazing-feature`
5. Open a Pull Request

Please follow the existing code style and include clear commit messages.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

- [SpeechRecognition](https://pypi.org/project/SpeechRecognition/) by Uberi
- [Flask](https://flask.palletsprojects.com/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Lucide Icons](https://lucide.dev/)

Made with ❤️ by Himansini Panda.
