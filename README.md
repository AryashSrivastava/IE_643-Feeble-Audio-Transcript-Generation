# Feeble Audio-Based Transcript Generation
A comprehensive project focused on generating text transcriptions from feeble and distorted audio signals with minimal syntax and information loss. Leveraging pre-trained models and advanced noise-handling techniques, this project addresses complex challenges in speech recognition and transcription.

![Python](https://img.shields.io/badge/python-3.9%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-active-brightgreen)

---

## Team and Guidance
- **Course**: IE 643
- **Team Name**: NLPeeps
- **Team Members**: Aryash Srivastava (22B1506), Dhruv Garg (22B1529)
- **Guided by**: Prof. Balamurugan  
- **TA’s**: Mr. Rahul, Mr. Bheeshm

---

## Table of Contents
1. [Problem Statement](#problem-statement)
2. [Workflow](#workflow)
3. [Proposed Approach](#proposed-approach)
4. [Dataset and Preprocessing](#dataset-and-preprocessing)
5. [Experimental Setup](#experimental-setup)
6. [Experimental Results](#experimental-results)
7. [Installation](#installation)
8. [Usage](#usage)
9. [References](#references)
10. [Drive Link](#drive-link)


---

## Problem Statement
To generate accurate transcriptions from feeble audio recordings with minimal syntax and information loss. This includes handling distorted signals, muting sections, and predicting masked words effectively.

---

## Workflow
The project follows a systematic approach:
1. **Initial Theoretical Development**:
   - Exploration of speech recognition techniques like Hidden Markov Models and n-grams.
   - Ideation of prediction algorithms.

2. **Shift to Pre-Trained Models**:
   - Leveraging OpenAI Whisper for transcription.

3. **Distortion Handling**:
   - Using Gaussian and white noise to simulate real-world distortions.

4. **Muted Section Prediction**:
   - Employing spectrogram decomposition for silent region detection.

5. **Model Integration**:
   - Combining all components into a single pipeline.

---

## Proposed Approach
### Key Components:
1. **Speech Recognition**:
   - Shift from custom-built models to pre-trained Whisper for reduced complexity.
   
2. **Audio Distortion Generation**:
   - Adding Gaussian noise and replacing segments with white noise.

3. **Muted Part Prediction**:
   - Using spectrogram variance to identify muted sections.
   - Employing a fill-mask model to predict missing words.

---

## Dataset and Preprocessing
- **Dataset**: Mozilla "Common Voice" dataset.
- **Preprocessing**:
  - Clipping audio and adding Gaussian noise (amplitude 0 to 0.02).
  - Replacing 0.2 to 0.5 seconds of audio with white noise.

---

## Experimental Setup
1. **Base Models**:
   - Distortion Generator.
   - Spectral Differentiator for sentence segmentation.
   - Predictor for masked sentences.

2. **Final Predictor**:
   - Integrates all components for end-to-end transcription.

3. **Testing**:
   - Real-time audio evaluation using a test predictor model.

---

## Experimental Results
### Dataset Testing:
- **Input**: Feeble audio with distortions.
- **Actual Statement**:  
  `Then I got a hold of some dough and went goofy.`
- **Predicted Statement**:  
  `Then got a hold of some joe and went goofy.`

### Real-Time Testing:
- **Input**: Live recording.  
- **Predicted Output**: `Sun rises from East.`

---

# Novelty Asessment Additions
1. Only the first pause is predicted; no further predictions occur-> Improved through Pydub Silence, running the model over next white noise intervals after the 1st interval is processed.
2. Predictions are occasionally in incorrect languages-> Retraining the model over formatted dataset to make English as the default language
---

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
3. Install `ffmpeg` for audio processing:
    - [FFmpeg Installation Guide](https://ffmpeg.org/download.html)

---

## Usage
1. Prepare your audio files.
2. Run the main script:
    ```bash
    python speechrecognition.py --input example_audio.mp3
    ```
3. Customize silence thresholds and noise parameters in the script if needed.

---

## References
1. [Whisper: Automatic Speech Recognition System](https://github.com/openai/whisper)
2. [SpecAugment for Automatic Speech Recognition](https://ar5iv.labs.arxiv.org/html/1810.04826)
3. [Audio Deep Learning Made Simple](https://towardsdatascience.com/audio-deep-learning-made-simple-part-2-why-mel-spectrograms-perform-better-aad889a93505)

---

## Drive Link
Drive containing code walkthrough, demo & other important files is here:
https://drive.google.com/drive/folders/1KQfsV03J0JCduEdgUgeFWcVNsS8VVo_k

# To-Be-Added
1.Demo of the model->so user can record themselve with pauses and missing words and the model prints the voice-to-text

