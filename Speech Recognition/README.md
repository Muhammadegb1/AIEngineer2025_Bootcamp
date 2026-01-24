# Speech Recognition & Audio Processing Project

## Overview
This project demonstrates a complete speech processing pipeline using Python, combining **audio analysis**, **speech-to-text (ASR)**, **error evaluation**, and **text-to-speech (TTS)**.

The project is divided into **two main scripts**, each with a clear responsibility:
1. Single-audio analysis and comparison of speech recognition techniques.
2. Batch transcription of multiple audio files and exporting results.

---

## Project Structure
```
project/
│
├── audio_analysis_asr.py        # Single audio processing and evaluation
├── batch_transcription_tts.py  # Directory transcription + CSV + TTS
├── speech_01.wav               # Example input audio
├── filtered_speech_01.wav      # Output after pre-emphasis
├── transcriptions.csv          # Generated transcription results
├── output.mp3                  # Generated TTS audio
└── README.md
```

---

## File 1: `audio_analysis_asr.py`

### Purpose
Processes a single speech file and compares different speech recognition approaches while analyzing audio characteristics.

### Main Features
- Load and visualize audio waveform
- Compute and display spectrogram (STFT)
- Apply **pre-emphasis filter** to enhance high-frequency speech components
- Speech recognition using:
  - Google Speech Recognition (via `speech_recognition`)
  - OpenAI Whisper
- Quantitative evaluation using:
  - Word Error Rate (WER)
  - Character Error Rate (CER)
- Comparison between original and pre-emphasized audio

### Technologies Used
- `librosa` – audio processing and visualization
- `matplotlib` – plotting waveforms and spectrograms
- `speech_recognition` – Google ASR
- `whisper` – OpenAI speech-to-text model
- `jiwer` – WER / CER evaluation
- `soundfile` – audio file writing

---

## File 2: `batch_transcription_tts.py`

### Purpose
Automates transcription of multiple audio files from a directory and generates both text and speech outputs.

### Main Features
- Load Whisper ASR model
- Transcribe all `.wav` files in a directory
- Save transcriptions to a structured CSV file
- Convert text to speech using Google Text-to-Speech (gTTS)

### Technologies Used
- `whisper` – batch speech recognition
- `csv` – structured transcription export
- `os` – directory traversal
- `gTTS` – text-to-speech generation

---

## Dependencies
Install all required packages using:
```bash
pip install numpy matplotlib librosa soundfile speechrecognition jiwer openai-whisper gtts
```

> **Note:** Whisper requires `ffmpeg` to be installed and available in system PATH.

---

## Usage

### Single Audio Analysis
```bash
python audio_analysis_asr.py
```

### Batch Transcription & TTS
```bash
python batch_transcription_tts.py
```

---

## Output
- Visual audio analysis (waveform & spectrogram)
- Speech-to-text transcriptions
- WER / CER evaluation metrics
- CSV file with batch transcriptions
- Generated MP3 audio from text

---

## Notes
- Designed for experimentation and comparison of ASR techniques
- Easily extendable to other datasets or Whisper models (`small`, `medium`, `large`)

---

## Author
Muhammad Agbariah
Computer Science | Speech & Audio Processing

