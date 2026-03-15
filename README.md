# Machine Vision Practice

This repository contains machine vision assignment work and practice exercises.

## Setup

1. Create and activate virtual environment:
```bash
python -m venv .venv
.venv\Scripts\Activate.ps1
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Contents

- `ImageProcessing_1.ipynb` - Fundamental image processing with OpenCV: color space conversions, geometric transforms, smoothing filters, edge detection (Canny), and histogram equalization
- `MachineLearningProcessing.ipynb` - End-to-end Oxford-IIIT Pet classification workflow covering dataset exploration, stratified train/validation/test splitting, a traditional ORB + Bag-of-Visual-Words + XGBoost pipeline, and a DenseNet-121 CNN baseline with augmentation experiments. The notebook reports core evaluation metrics including accuracy, precision, recall, and F1 score.
