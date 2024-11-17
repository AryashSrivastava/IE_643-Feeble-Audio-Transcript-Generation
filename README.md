# Feeble Audio-Based Transcript Generation
A speech recognition model using OpenAI Whisper that transcribes audio with pause detection.

![Python](https://img.shields.io/badge/python-3.9%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-active-brightgreen)

## Table of Contents
- [About](#about)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## About
This project implements a speech recognition pipeline using OpenAI's Whisper model. 
It splits audio based on pauses to improve transcription accuracy and handles multiple segments efficiently.

## Features
- Automatic audio transcription using OpenAI Whisper.
- Handles pauses to transcribe audio in segments.
- Customizable silence thresholds for segmentation.
- Works with diverse audio formats.

## Installation
1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/feeble-audio-transcription.git
    cd feeble-audio-transcription
    ```
2. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
3. Ensure `ffmpeg` is installed for `pydub`:
    - [FFmpeg Installation Guide](https://ffmpeg.org/download.html)

## Usage
1. Prepare your audio files.
2. Run the main script:
    ```bash
    python speechrecognition.py --input example_audio.mp3
    ```
3. Customize silence parameters in the script if needed.
4. View the transcription in the output file.

## Results
### Example Audio-to-Text Transcription
Original Audio:
![Audio Waveform](https://via.placeholder.com/400x150)

Transcription Output:
