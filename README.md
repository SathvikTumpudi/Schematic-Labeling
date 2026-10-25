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

## Pipeline

1. Upload an electrical schematic image.
2. Detect symbols using YOLO.
3. Detect text regions using CRAFT and extract text using Tesseract.
4. Detect wire segments using OpenCV.
5. Analyze relationships between symbols, labels, and wires.
6. Display the annotated schematic and export the connection report.

## Getting Started

The current implementation is developed in Google Colab.

1. Open the notebook in this repository using Google Colab.
2. Install the required dependencies.
3. Make the required model weights, class definitions, and CRAFT resources available.
4. Run the notebook's setup and model-loading cells.
5. Launch the Gradio interface.
6. Upload a schematic and review the annotated image and connection report.

Exact dependency versions and model-resource setup instructions will be documented alongside the notebook.

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

## Acknowledgments

This project combines existing computer vision, object detection, and OCR tools into a pipeline for electrical schematic analysis. Please consult the respective projects' licenses and attribution requirements when distributing their code or model resources.
