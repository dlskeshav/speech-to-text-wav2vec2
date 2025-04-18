# 🧠 Speech Recognition with Wav2Vec2 — Evaluation on LibriSpeech

This repository demonstrates a mini speech recognition pipeline using Hugging Face’s **Wav2Vec2** model and the **LibriSpeech** dataset. It evaluates transcription quality using the **Word Error Rate (WER)** metric.

---

## 📌 Objective

To evaluate the transcription quality of the `facebook/wav2vec2-base-960h` model on a subset of the LibriSpeech dataset using robust metrics like WER. This serves as a reproducible mini-pipeline for audio-to-text evaluation.

---

## 📚 Dataset

- **Name:** LibriSpeech ASR Corpus
- **Subset Used:** `train.100` → `"clean"` split
- **Accessed via:** Hugging Face Datasets
- **Mode:** Streaming (for low-memory usage)
- **Sample Size:** 10 samples only (for quick demonstration)

---

## 🧠 Model Used

- **Model:** [`facebook/wav2vec2-base-960h`](https://huggingface.co/facebook/wav2vec2-base-960h)
- **Architecture:** Wav2Vec2 + CTC Head
- **Pre-trained on:** 960 hours of LibriSpeech
- **Sampling Rate:** 16kHz (mono-channel expected)

---

## 🛠️ Dependencies

```bash
pip install torch torchaudio transformers datasets evaluate jiwer

