
# Emotion-Aware Speech Recognition from MP4 Files

## 📌 Overview

This project is a Python-based system that performs **emotion-aware speech recognition** from MP4 video files. It combines automatic speech recognition (ASR) using OpenAI’s Whisper model with basic emotion detection using audio features.

### Features:
- 🎥 Converts MP4 to WAV audio
- 🧠 Transcribes speech to text using Whisper
- 🎼 Extracts MFCC and pitch-based audio features
- 😠 Classifies emotions (happy, sad, angry, neutral) using an SVM classifier

---

## 🛠️ Requirements

Install the required packages using pip:

```bash
pip install openai-whisper librosa numpy scikit-learn moviepy
```

---

## 📂 File Structure

- `main.py`: The main script containing all functions and execution logic

---

## 🔍 Key Functions

### `convert_mp4_to_wav(mp4_path, wav_path)`
Converts an MP4 video file to WAV format using `moviepy.editor.AudioFileClip`.

### `transcribe_audio(audio_path)`
Transcribes audio to text and detects language using the Whisper model.

### `extract_audio_features(audio_path)`
Extracts audio features:
- 13 MFCCs (Mel Frequency Cepstral Coefficients)
- 13 pitch-related values (mean pitch across time)

### `train_emotion_classifier()`
Creates a dummy emotion classifier using random data (for demo purposes) and trains an SVM model using `scikit-learn`.

### `classify_emotion(features, classifier, le)`
Predicts emotion from the extracted audio features.

### `emotion_aware_speech_recognition(mp4_path)`
The main function that:
- Converts video to audio
- Transcribes speech
- Extracts audio features
- Detects emotion
- Prints all results

---

## ▶️ How to Use

1. Update the path to your MP4 file:
```python
audio_path = "/content/drive/MyDrive/vedio.mp4"
```

2. Run the Python script:
```bash
python main.py
```

---

## ✅ Example Output

```
Detected Emotion: sad
Transcription: Hello, I'm feeling a bit low today.
Language Detected: en
```

---

## ⚠️ Notes

- The emotion classifier uses **random dummy data**. Replace with a real trained model and dataset (e.g., RAVDESS, Emo-DB) for production.
- Whisper model used is `"base"` — you can switch to `"small"`, `"medium"`, or `"large"` based on system capability and accuracy needs.
- Make sure your MP4 file contains **audio** — else, the converter will raise an error.

---

## 🙏 Credits

- **OpenAI Whisper** for ASR
- **Librosa** for audio feature extraction
- **MoviePy** for video/audio handling
- **Scikit-learn** for emotion classification
