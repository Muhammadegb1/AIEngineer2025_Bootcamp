# Speech Recognition & Audio Processing Project

This project demonstrates a complete speech processing pipeline using Python, combining **audio analysis**, **speech-to-text (ASR)**, **error evaluation**, and **text-to-speech (TTS)**.

The project is divided into **two files**, each with a clear responsibility:
1. Single-audio analysis and comparison of speech recognition techniques.
2. Batch transcription of multiple audio files and exporting results.

---

## File 1: `01 SpeechRecognition`

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

## File 2: `02 transcribe_audio_director & Text-to-speech`

### Purpose
Automates transcription of multiple audio files from a directory and generates both text and speech outputs.

### Main Features
- Load Whisper ASR-(Automatic Speech Recognition) model
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
### Conda Environment

Using a virtual environment is recommended to manage packages without affecting other projects.

Create and activate the environment:

```bash
conda create --name speech_env python
pip install ipykernel jupyterlab notebook
python -m ipykernel install --user --name speech_env --display-name "Python(speech_env)"
```

Install all required packages using:
```bash
pip install librosa SpeechRecognition jiwer matplotlib gTTS
pip install -U openai-whisper
```

**Note:** Whisper requires `ffmpeg` to be installed and available in system PATH.
           On Windows, you can install FFmpeg using [Chocolatey software](https://chocolatey.org/install)
           in **Windows PowerShell** - 
```bash
choco install ffmpeg
```
---
**Note:** Whisper requires 'PyTorch'. Install it according to your system configuration:
           [PyTorch installation guide](https://pytorch.org/get-started/locally/)
           Example for CPU-only: **pip3 install torch torchvision torchaudio**
           
---

