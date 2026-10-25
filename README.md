# Schematic Labeling Using AI

An AI-powered computer vision pipeline for analyzing electrical schematics, identifying symbols and text, detecting wires, and inferring connections between components.

## Overview

Electrical schematics contain symbols, labels, and connecting wires that can be difficult to interpret automatically. This project combines computer vision, object detection, and optical character recognition (OCR) to analyze schematic images and produce annotated diagrams and connection reports.

## Features

- **Symbol detection:** Uses YOLO to identify schematic symbols.
- **Text detection:** Uses CRAFT to locate text regions.
- **Optical character recognition:** Uses Tesseract OCR to extract text.
- **Wire detection:** Uses OpenCV and the Hough transform to detect wire segments.
- **Connection analysis:** Uses NetworkX to represent and analyze relationships between detected elements.
- **Visual output:** Produces annotated schematic images and a text report of inferred connections.
- **Interactive demo:** Provides a Gradio interface for uploading a schematic and viewing the results.
- **AI Summary** Provides an AI Generated summary of the electrical schematic using Ollama

## Pipeline

1. Upload an electrical schematic image.
2. Detect symbols using YOLO.
3. Detect text regions using CRAFT and extract text using Tesseract.
4. Detect wire segments using OpenCV.
5. Analyze relationships between symbols, labels, and wires.
6. Display the annotated schematic and export the connection report.

## Setup and Installation

This project is designed to run in Google Colab, which provides a convenient environment for running the computer vision pipeline.

### 1. Open the notebook

Open `Line Detection AI with Tesseract.ipynb` in [Google Colab](https://colab.research.google.com/).

You can upload the notebook to Colab or open it from your GitHub repository.

### 2. Install dependencies

Install the Python dependencies listed in `requirements.txt`. Some packages, especially PyTorch, may need versions compatible with the available Colab runtime and GPU.

The project also requires the Tesseract OCR executable, in addition to the `pytesseract` Python package.

### 3. Set up Tesseract OCR

In a Colab cell, run:

```bash
!apt-get update -qq
!apt-get install -y tesseract-ocr
```

### 4. Set up CRAFT text detection

The project uses CRAFT for text-region detection. Clone or otherwise provide the CRAFT repository and ensure its dependencies and pretrained model weights are available.

Depending on the installed `huggingface_hub` version, the original CRAFT code may require a compatibility change. In `CRAFT/model.py`, replace the deprecated `cached_download` import and call with the supported `hf_hub_download` function, as appropriate for the installed version.

### 5. Run the notebook

Execute the notebook cells in order. The pipeline uses YOLO for symbol detection, CRAFT for text-region detection, Tesseract for OCR, OpenCV for wire detection, and NetworkX to construct inferred connections.

### 6. Launch the interactive interface

Run the Gradio interface cell near the end of the notebook. It provides an interface for uploading a schematic and viewing the annotated output and detected connection report.

The public Gradio URL is temporary and remains available only while the Colab runtime and app are running.

## Output Files

- `annotated_output.png` — schematic annotated with detection results.
- `output.txt` — text report of inferred connections.

## Outputs

The application produces:

- An annotated schematic image.
- A text report listing inferred connections between detected elements.
- An interactive interface for reviewing the results.

## Limitations

Results depend on image quality, model performance, text legibility, and wire-detection accuracy. Inferred connections should be reviewed against the original schematic. The current demo processes one image at a time.

## Technologies

- Python
- YOLO / Ultralytics
- CRAFT text detection
- Tesseract OCR
- OpenCV
- NetworkX
- Matplotlib
- Gradio
- Google Colab

## Future Improvements

- Export connections in structured CSV or JSON formats.
- Improve wire-to-symbol association and connection accuracy.
- Evaluate performance on a broader range of schematic layouts.
- Package the application for easier local deployment.

## Demo

Screenshots and a demonstration video will be added here.
