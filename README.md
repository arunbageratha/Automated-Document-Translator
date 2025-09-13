# Automated-Document-Translator
📖 Automated Document Translation Workflow (Summary)

This project demonstrates how to automate translation of documents (PDFs, audio, and video files) using n8n, integrating APIs for OCR, speech-to-text, translation, and AI title generation.

🔑 Key Tools

n8n – Workflow automation

Google Drive – File storage & triggers

Google Cloud Translation API – Language translation

11 Labs API – Speech-to-text for audio/video

Google Gemini (v2.5) – AI-powered title generation

Google Docs – Output storage

⚙️ Workflow Overview

Trigger – Google Drive monitors a folder for new uploads.

Download – File is retrieved via Google Drive node.

Routing – Workflow routes based on file type:

PDF → Extract text with Extract from File node

Audio/Video (MP4) → Transcribe with 11 Labs API (via HTTP request)

Pre-processing – Extracted or transcribed content is standardized into a single text field.

Translation – Google Cloud Translation API translates the text into the target language.

Title Generation – Google Gemini generates a short, AI-powered title (≈5 words).

Document Creation – A new Google Doc is created with the Gemini title, then updated with the translated text.

✅ Final Output

A new Google Docs file in Drive containing:

The translated document

An auto-generated title
