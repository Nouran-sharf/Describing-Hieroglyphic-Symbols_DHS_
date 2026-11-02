# DHS – Describing Hieroglyphic Symbols

**An Academic Project | Computer Vision & Natural Language Processing**

## Overview

DHS (Describing Hieroglyphic Symbols) is an academic project developed at the Faculty of Artificial Intelligence, Delta University for Science and Technology.

The project aims to make Ancient Egyptian hieroglyphs more accessible to tourists and non-specialists through an AI-powered system that detects hieroglyphic symbols in images, identifies their meanings, and provides English audio explanations.

The system combines Computer Vision and Natural Language Processing technologies in a mobile application built with Flutter.

## Project Workflow

The system follows four main stages:

### 1. Hieroglyphic Image Classification – CLIP

The first stage uses the pre-trained **CLIP (ViT-B/32)** model to determine whether an uploaded image contains Ancient Egyptian hieroglyphs.

- Uses zero-shot image classification.
- Compares the image against text prompts to distinguish hieroglyphic images from unrelated images.
- Filters out irrelevant images before proceeding to symbol detection.

**Evaluation:**
- Accuracy: 99% on a test set of 100 images.
- Inference time: approximately 564 ms per image.

### 2. Symbol Detection and Classification – YOLOv11

After an image passes the initial classification stage, **YOLOv11** detects individual hieroglyphic symbols and identifies their corresponding Gardiner codes.

- Trained on a dataset containing approximately 15,000 images.
- Covers 1,400 distinct hieroglyphic symbol classes.
- Uses bounding-box annotations to locate individual symbols.
- Includes images of symbols with different conditions, including faded and damaged inscriptions.

**Training and Evaluation:**
- Training epochs: 200.
- mAP50: 90.897%.


### 3. Symbol Descriptions and Audio Generation – Kokoro TTS

Once a symbol is identified, its Gardiner code is used to retrieve its corresponding description from a JSON database.

The **Kokoro Text-to-Speech (TTS)** system converts the retrieved English description into a WAV audio file, allowing users to listen to the meaning of the symbol.

- Contains descriptions for 200 hieroglyphic symbols.
- Descriptions were collected and prepared using historical and linguistic references.
- Text preprocessing is applied before audio generation.
- Provides spoken explanations to make the information more accessible to visitors.



### 4. Mobile Application – Flutter

The different components are integrated into a Flutter mobile application that allows tourists to interact with the system while visiting archaeological sites.

The application connects image input, symbol recognition, description retrieval, and audio narration in one user experience.

## Dataset

The project uses two main data resources:

- **Hieroglyphic Image Dataset:** Approximately 15,000 images covering 1,400 symbol classes, obtained through Roboflow and prepared for object detection.
- **Symbol Description Dataset:** A manually collected and structured JSON dataset containing descriptions of 200 hieroglyphic symbols, based on references including Allen (2014) and Wiktionary.


## My Contribution

I contributed to the project through:

- Working with the pre-trained CLIP model for hieroglyphic image classification.
- Integrating Kokoro TTS to generate English audio explanations.
- Contributing to data collection and preparation for the project.
