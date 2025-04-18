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

📜 Script Flow
The script performs the following steps:

Load LibriSpeech ASR (clean, streaming).

Load facebook/wav2vec2-base-960h model and processor.

Run inference on 10 samples from the dataset.

Evaluate transcription results using Word Error Rate (WER).

Print results per sample and overall accuracy.

📈 Sample Output (Example)
yaml
Copy
Edit
Sample 1
Original Text   : A MOUSE FOUND A BEAUTIFUL RING IN THE GRASS
Predicted Text  : a mouse found a beautiful ring in the grass
WER for Sample  : 0.0000

...

Overall Evaluation:
Word Error Rate (WER): 0.0417
Approximate Accuracy : 95.83%
🧪 Metrics
WER (Word Error Rate) is calculated per sample and overall.

Accuracy is estimated as:

Accuracy
=
(
1
−
WER
)
×
100
Accuracy=(1−WER)×100
🧠 Model Architecture (Summary)
Feature Extractor: CNN layers extract low-level audio features.

Transformer Encoder: Captures long-range context via self-attention.

CTC Decoder: Maps audio features to text without needing alignment.

📂 Project Structure
perl
Copy
Edit
wav2vec2-eval/
├── NNDL_ASSIGNMENT_3.pdf       # Full code and writeup
├── evaluation_script.py        # Inference & WER calculation
└── README.md                   # Project overview
🏁 Conclusion
This evaluation demonstrates the practical effectiveness of Wav2Vec2 in transcribing speech from real-world datasets like LibriSpeech. The model achieves high accuracy with minimal tuning.

🔗 References
facebook/wav2vec2-base-960h (Hugging Face)

LibriSpeech Dataset (OpenSLR)

Wav2Vec2 Paper (Facebook AI)

