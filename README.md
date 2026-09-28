# Dog Show Image Classifier

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white" alt="Python 3.9+" />
  <img src="https://img.shields.io/badge/PyTorch-2.x-EE4C2C?logo=pytorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/Status-Project%20Demo-4CAF50" alt="Project Demo" />
</p>

A Python deep learning project that classifies dog images using pretrained CNN models from `torchvision` and compares the model predictions against the expected dog breed labels.

## Overview

This project demonstrates image classification and model comparison by evaluating multiple pretrained architectures:

- `resnet`
- `alexnet`
- `vgg`

It extracts pet labels from filenames, runs each image through a pretrained model, checks whether the predicted label matches the expected label, and summarizes the model's performance.

## Why this project?

This repository is a practical example of:

- deep learning image classification
- transfer learning with pretrained CNNs
- evaluating model accuracy on a small dataset
- Python-based computer vision workflows

## Features

- Classify dog and pet images with pretrained ImageNet models
- Compare model predictions to image filename labels
- Determine whether labels are recognized as dog breeds
- Calculate accuracy and summary statistics
- Run experiments across multiple CNN architectures

## Project Structure

```text
dog_show_image_classifier/
├── check_images.py                 # Main entry point for the pipeline
├── classifier.py                  # CNN classifier using pretrained models
├── get_input_args.py              # CLI argument parsing
├── get_pet_labels.py              # Extracts labels from image filenames
├── classify_images.py             # Compares pet labels vs. classifier labels
├── adjust_results4_isadog.py      # Checks if labels are dog-related
├── calculates_results_stats.py    # Computes classification statistics
├── print_results.py               # Prints summary output
├── test_classifier.py             # Quick classifier smoke test
├── pet_images/                    # Sample dog images
├── dognames.txt                  # Dog breed names used for matching
├── imagenet1000_clsid_to_human.txt  # ImageNet class mapping
├── run_models_batch.sh            # Batch comparison script
├── requirements.txt               # Python dependencies
├── README.md                     # Project documentation
└── ...
```

## Requirements

This project requires Python 3.9+ and these packages:

- `torch`
- `torchvision`
- `Pillow`

Install dependencies:

```bash
pip install -r requirements.txt
```

## Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/dog_show_image_classifier.git
cd dog_show_image_classifier
```

2. Create a virtual environment (recommended):

```bash
python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows
```

3. Install the required libraries:

```bash
pip install -r requirements.txt
```

## Usage

Run the full image classification pipeline:

```bash
python check_images.py --dir pet_images/ --arch vgg --dogfile dognames.txt
```

Try other architectures:

```bash
python check_images.py --dir pet_images/ --arch resnet --dogfile dognames.txt
python check_images.py --dir pet_images/ --arch alexnet --dogfile dognames.txt
```

Quick smoke test for the classifier function:

```bash
python test_classifier.py
```

## Example Output

```text
----------- Statistics from calculates_results_stats.py -----------
Number of Images: 40
Number of Dog Images: 30
Number of Not-a-Dog Images: 10
Number of Correct Dog Matches: 25
Number of Correct Not-a-Dog Matches: 8
Percentage Correct Dogs: 83.33%
Percentage Correct Breeds: 75.00%
```

## Notes

- The classifier uses pretrained weights from `torchvision`, which may download model files the first time they are used.
- The project is designed as a learning/demo project and is easy to adapt for other image datasets.
- This repository is suitable for sharing on GitHub as a portfolio or machine learning project sample.

## License

This project is intended for educational use. Please review the repository's license files before publishing or distributing it publicly.

## Author

Emmanuel Michael Nyakeh Moriwa
