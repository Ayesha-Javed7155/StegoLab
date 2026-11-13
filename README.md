# StegoLab

A Python and Gradio application for experimenting with **image and WAV audio steganography**. It demonstrates how a secret message can be embedded in media, recovered with a key, and evaluated under simulated distortion or tampering.

## Features

- **Image steganography:** embed and extract text messages in images.
- **Audio steganography:** embed and recover messages in WAV audio.
- **Key-based message transformation:** a shared key is used during embedding and extraction.
- **Integrity checking:** SHA-256 hashes help detect whether extracted content matches the expected message.
- **Error correction:** repetition-based encoding and majority-vote decoding help tolerate some corrupted bits.
- **Robustness experiments:** simulate noise, cropping/resizing, JPEG-like quantization, trimming, and sample or pixel tampering.
- **Visual analysis:** inspect embedding heatmaps, image differences, PSNR, and tamper-related measurements.
- **Audio analysis:** view activity scores and ranked audio segments.

## Tech Stack

- Python
- Gradio
- NumPy
- Pillow
- SoundFile
- SciPy

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Ayesha-Javed7155/StegoLab.git
cd StegoLab
```

### 2. Create and activate a virtual environment (recommended)

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Run the application

```bash
python app.py
```

Open the local Gradio URL printed in the terminal.

## How to Use

1. Launch the application.
2. Select the image or audio workflow.
3. Upload a supported image or WAV file.
4. Enter the message and key, then run the embedding process.
5. Use the extraction workflow with the corresponding key to recover the message.
6. Try the available attack simulations and analysis outputs to explore how media distortion affects recovery and integrity.

## Repository Structure

| File | Description |
|---|---|
| `app.py` | Gradio interface and image/audio processing workflows |
| `requirements.txt` | Python dependencies |

## Important Notes

- This is an educational and experimental project, not a production security tool.
- The key-based transformation in this project should **not** be treated as modern, secure encryption.
- SHA-256 integrity checks and error-correction experiments do not guarantee successful recovery after every type or level of attack.
- Use media files you own or have permission to process.

## Future Improvements

- Add automated tests and sample media for reproducible evaluation.
- Document supported file formats, payload limits, and measured robustness more fully.
- Replace educational key handling with a well-reviewed cryptographic design if the project is extended for security-sensitive use.
