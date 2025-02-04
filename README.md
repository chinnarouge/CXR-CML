CXR-CML
Overview
CXR-CML (Chest X-Ray Contrastive Metric Learning) is a deep learning framework designed for analyzing chest X-ray images using contrastive learning techniques. The project leverages the CLIP (Contrastive Language-Image Pretraining) model architecture to perform zero-shot classification on various chest pathologies. This repository includes implementations for data processing, model training, evaluation, and inference.

Features
Zero-Shot Learning: Utilize pre-trained CLIP models to classify chest X-ray images without the need for fine-tuning on specific datasets.
Data Processing: Efficiently load and preprocess chest X-ray images and corresponding radiology reports.
Evaluation Metrics: Comprehensive evaluation metrics including AUC, F1 score.
Bootstrap Confidence Intervals: Compute confidence intervals for model predictions using bootstrap sampling.
Visualization: Generate visualizations for model predictions and performance metrics.
Installation
To set up the CXR-CML environment, follow these steps:

Clone the repository:

git clone https://github.com/yourusername/CXR-CML.git
cd CXR-CML
Create a virtual environment (optional but recommended):

python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
Install the required packages:

pip install -r requirements.txt
Usage
Data Preparation
Prepare your chest X-ray images and corresponding labels in CSV format.
Use the provided scripts to convert images to HDF5 format and generate CSV files containing image paths and labels.
Training the Model
To train the model, use the run_train.py script:

python run_train.py --cxr_filepath <path_to_hdf5> --txt_filepath <path_to_csv> --label_filepath <path_to_labels_csv>
Evaluation
To evaluate the model’s performance, use the eval.py script:

python eval.py --model_path <path_to_trained_model> --cxr_filepath <path_to_hdf5> --final_label_path <path_to_labels_csv>
Inference
To perform inference on new chest X-ray images, use the zero_shot.py script:

python zero_shot.py --model_path <path_to_trained_model> --cxr_filepath <path_to_hdf5> --cxr_labels <list_of_labels>
File Structure
CXR-CML/
│
├── clip.py                # Implementation of the CLIP model
├── data_process.py        # Data loading and preprocessing functions
├── dataset_maker.py       # Script to create datasets from images and labels
├── eval.py                # Evaluation metrics and functions
├── metrics.py             # Additional metrics for model evaluation
├── model.py               # Model architecture definitions
├── run_train.py           # Training script
├── simple_tokenizer.py    # Tokenization utilities
├── text_generation.py      # Script to generate text reports from labels
├── train.py               # Training utilities and dataset class
├── zero_shot.py           # Zero-shot classification utilities
├── zero_shot_test.py      # Testing script for zero-shot classification
├── README.md              # Project documentation
└── LICENSE                # License information
Contributing
Contributions are welcome! If you have suggestions for improvements or new features, please open an issue or submit a pull request.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgments
The CLIP model and its implementation were developed by OpenAI.
The dataset used in this project is derived from publicly available chest X-ray datasets.
