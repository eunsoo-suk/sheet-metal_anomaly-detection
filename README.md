**Sheet Metal Anomaly Detection**

**📌 Project Overview**

This project aims to detect defects in sheet metal images using a PatchCore-style anomaly detection pipeline with a ConvNeXt-Tiny backbone.
The pipeline builds a feature bank from normal samples, applies thresholding, and evaluates performance on normal vs defective test images.

**📂 Dataset Composition**

**Train set**

- train/good — normal samples

**Validation set**

- validation/good — normal samples (for threshold calibration)

**Test set**
- test_public/ :
    - good: Normal test images
  
    - bad: Evaluation images (normal and defective)
  
    - ground_truth: Defect masks (optional, matched by filename)

**[Download Sheet Metal Dataset]**(https://drive.google.com/file/d/1tIISRI8wKw9y29Q90IK5fWrSc4f6UAeC/view?usp=drive_link)

**⚙️ Workflow**

Imports & Configurations – set up environment, seeds, device.

Utilities – image preprocessing, tensor conversion, normalization.

Backbone Feature Extraction – ConvNeXt-Tiny (stage2 & stage3).

Feature Bank & Thresholding – PCA, coreset sampling, FAISS index, τ calibration.

Evaluation – AUROC, AUPRC, Precision, Recall, F1, confusion matrix.

Visualization – anomaly heatmaps, overlays, defect masks.

**📊 Results**

AUROC = 0.8681

F1 = 0.899

Precision = 0.909

Recall = 0.889
