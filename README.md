# 🧠 Deep Learning Practical Exam — Set A

A hands-on deep learning practical covering **Artificial Neural Networks (ANN), OpenCV image preprocessing, Convolutional Neural Networks (CNN), Recurrent Neural Networks (RNN), and Transformer-based sentiment analysis**. The work is organized in one Jupyter notebook, with saved model files and output figures included.

> 📌 **Notebook:** [`notebooks/set-A.ipynb`](notebooks/set-A.ipynb)  
> 📦 **Dependencies:** [`requirements.txt`](requirements.txt)

---

## 📚 Practical Tasks

| Step | Topic | Objective | Main Output |
|---|---|---|---|
| 1 | 🩺 ANN — Diabetes Prediction | Train a binary classifier using patient features from the diabetes dataset. | Accuracy/loss curves, confusion matrix, saved ANN model |
| 2 | 🖼️ OpenCV — Image Processing | Load five images and apply resizing, grayscale conversion, Canny edge detection, and contour detection. | Image preprocessing grids |
| 3 | 🚗 CNN — CIFAR-10 Classification | Train a CNN to classify images from the CIFAR-10 dataset. | Sample images, training/validation curves, prediction examples, saved CNN model |
| 4 | ✈️ RNN — Airline Passenger Forecasting | Learn temporal patterns in monthly airline passenger counts and predict passenger numbers. | Time-series plot, actual-vs-predicted plot, training-loss curve, saved RNN model |
| 5 | 💬 Transformer — Sentiment Analysis | Classify movie-review sentiment and visualize model confidence scores. | Sentiment confidence chart |
| 6 | 📊 Model Comparison | Summarize the tasks, architectures, and outputs from the practical. | Comparison section in notebook |

---

## 🗂️ Project Structure

```text
Deep_Learning_Practical_Set_A/
├── README.md
├── requirements.txt
├── data/
│   └── diabetes.csv
├── notebooks/
│   └── set-A.ipynb
├── models/
│   ├── ann_diabetes_model.h5
│   ├── cnn_cifar10_model.h5
│   └── rnn_airline_model.h5
└── outputs/
    ├── ann_training_validation_accuracy.png
    ├── ann_training_validation_loss.png
    ├── ann_confusion_matrix.png
    ├── opencv_preprocessing_pipeline.png
    ├── opencv_original_images.png
    ├── opencv_5x5_processing_grid.png
    ├── cnn_cifar10_sample_images.png
    ├── cnn_training_validation_accuracy.png
    ├── cnn_training_validation_loss.png
    ├── cnn_prediction_examples.png
    ├── airline_passenger_timeseries.png
    ├── rnn_actual_vs_predicted.png
    ├── rnn_training_loss.png
    └── transformer_sentiment_confidence.png
```

---

## ⚙️ Setup & Installation

### 1. Requirements

- Python compatible with the installed TensorFlow/Keras stack
- Jupyter Notebook or JupyterLab
- The packages listed in `requirements.txt`
- Internet access may be needed if a dataset or pretrained Transformer model is downloaded at runtime

### 2. Create and activate a virtual environment

**Windows (PowerShell / Command Prompt):**

```bash
python -m venv .venv
.venv\Scripts\activate
```

**macOS / Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Launch the notebook

```bash
jupyter notebook
```

Open `notebooks/set-A.ipynb` and run the cells in order.

> ⚠️ **Path note:** The notebook may contain machine-specific paths for image files or CIFAR-10 batch files. Update those paths for your computer before running the related cells. The diabetes CSV is included in `data/`; if the notebook expects `diabetes.csv` in its current working directory, either update the read path to `../data/diabetes.csv` (when running from `notebooks/`) or place a copy in the expected directory. OpenCV's five original source images are not bundled separately here; add them to the image folder expected by the notebook before rerunning that task.

---

## 📈 Results & Output Gallery

The figures below are included from the provided practical outputs. They illustrate the recorded runs; exact metrics should be taken from the notebook output cells rather than inferred from the plots.

### 1. 🩺 ANN — Diabetes Prediction

**Training vs. validation accuracy**

![ANN training and validation accuracy](outputs/ann_training_validation_accuracy.png)

**Training vs. validation loss**

![ANN training and validation loss](outputs/ann_training_validation_loss.png)

**Confusion matrix**

![ANN confusion matrix](outputs/ann_confusion_matrix.png)

**Observation:** The accuracy curves rise and then level off near the end of training. The training loss continues to decrease while validation loss decreases more gradually, leaving a modest generalization gap. Use the notebook's test-set metrics and confusion matrix for the final evaluation.

### 2. 🖼️ OpenCV — Image Preprocessing

**Original images**

![Original images](outputs/opencv_original_images.png)

**Preprocessing pipeline**

![OpenCV preprocessing pipeline](outputs/opencv_preprocessing_pipeline.png)

**5 × 5 processing grid**

![OpenCV 5x5 processing grid](outputs/opencv_5x5_processing_grid.png)

**Pipeline:** Original image → resize to 128 × 128 → grayscale → Canny edges → largest contour highlighted.

### 3. 🚗 CNN — CIFAR-10 Image Classification

**Sample CIFAR-10 images**

![CIFAR-10 sample images](outputs/cnn_cifar10_sample_images.png)

**Training vs. validation accuracy**

![CNN training and validation accuracy](outputs/cnn_training_validation_accuracy.png)

**Training vs. validation loss**

![CNN training and validation loss](outputs/cnn_training_validation_loss.png)

**Prediction examples**

![CNN prediction examples](outputs/cnn_prediction_examples.png)

**Observation:** Training accuracy improves substantially, while validation accuracy levels off earlier. The increasing gap and rising validation loss in later epochs suggest possible overfitting; consider data augmentation, dropout, regularization, or early stopping.

### 4. ✈️ RNN — Airline Passenger Forecasting

**Monthly airline passenger time series**

![Airline passenger time series](outputs/airline_passenger_timeseries.png)

**Actual vs. predicted passengers**

![RNN actual versus predicted](outputs/rnn_actual_vs_predicted.png)

**Training loss**

![RNN training loss](outputs/rnn_training_loss.png)

**Observation:** The series has an overall upward trend and recurring seasonal peaks. Predictions broadly follow the pattern, but some peaks are underestimated. A time-based train/test split is important for forecasting evaluation.

### 5. 💬 Transformer — Sentiment Analysis

**Sentiment confidence scores**

![Transformer sentiment confidence](outputs/transformer_sentiment_confidence.png)

Green and red bars indicate the sentiment categories as represented by the original plot. Review the notebook's label mapping and model output before interpreting any individual prediction. The chart displays confidence scores, not an overall accuracy metric.

---

## 💾 Saved Models

| File | Purpose |
|---|---|
| `models/ann_diabetes_model.h5` | Saved ANN model for diabetes classification |
| `models/cnn_cifar10_model.h5` | Saved CNN model for CIFAR-10 image classification |
| `models/rnn_airline_model.h5` | Saved RNN model for airline passenger forecasting |

The model files are provided for reuse. Loading them may require compatible TensorFlow/Keras versions. The Transformer task uses a pretrained model or pipeline as defined in the notebook; no separate Transformer model file was supplied in this package.

---

## 🧪 Reproducibility Notes

- Run notebook cells from top to bottom so variables and model objects are initialized in order.
- Check dataset and image paths before executing the relevant steps.
- Training results can vary with library versions, hardware, random seeds, and dataset availability.
- The supplied `requirements.txt` records a specific package environment. Some package versions may not be available for every Python version or operating system; use a compatible Python environment if installation fails.
- The diabetes dataset and saved models are included in this package. The notebook may still download or require external datasets for CIFAR-10, airline passengers, or Transformer inference, depending on its implementation.
- No numeric performance result is claimed here unless it is printed in the notebook output.

---

## 🛠️ Technologies Used

- 🐍 Python
- 📓 Jupyter Notebook
- 🧮 NumPy and Pandas
- 📊 Matplotlib
- 🩻 Scikit-learn
- 🧠 TensorFlow / Keras
- 👁️ OpenCV
- 🤗 Transformers

---

## 🎯 Learning Outcomes

- Build and evaluate a feed-forward neural network for binary classification.
- Apply common image-processing operations using OpenCV.
- Train a CNN and inspect classification predictions.
- Model sequential data and compare RNN predictions with actual observations.
- Use a Transformer-based pipeline for text sentiment analysis.
- Interpret training curves and identify possible overfitting.

---

## 👤 Author

**Deep Learning Practical — Set A**

---

⭐ If this project helped you, consider starring the repository on GitHub.
