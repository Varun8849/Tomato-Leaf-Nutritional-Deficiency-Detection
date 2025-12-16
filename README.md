# Layer-wise Analysis of Data Augmentation for Tomato Nutritional Deficiency Detection

This repository contains the code and results for a research paper on analyzing the impact of different data augmentation strategies on a YOLOv8 model for tomato disease detection. The experiments are conducted on a custom tomato dataset with various augmentations applied in a layer-wise manner.

## Description

The primary goal of this research is to evaluate how different data augmentation techniques, when applied sequentially, affect the performance of a YOLOv8 model. The experiments are performed on a dataset of tomato images to detect various diseases. The Jupyter notebook `Layerwise results.ipynb` in this repository contains the complete implementation of the experiments, including data loading, model training, and evaluation.

## Reproducibility and Code

To address the need for reproducibility, this repository provides all the necessary code and a clear summary of the datasets used.

The notebook `Layerwise results.ipynb` contains all the code used for the experiments. This includes:
-   **Data Loading:** Code to download the datasets from Roboflow.
-   **Data Augmentation:** The different augmentation strategies are implemented by using different datasets from Roboflow, where the augmentations have been pre-applied. The notebook is structured to test each of these datasets sequentially.
-   **Model Training:** The code for training the YOLOv8 model for each experiment is included in the notebook, using the `ultralytics` library.

### Data Splitting and Leakage
To ensure that there is no data leakage between the training, validation, and test sets, the datasets were pre-split on Roboflow. The notebook downloads these already separated datasets and uses them for training, validation, and testing. This approach guarantees that the test set remains completely independent and is not seen by the model during training or validation.

### Dataset Summary
The following table provides a summary of the image sets used for training, testing, and validation for each experiment to ensure reproducibility.

| Experiment Name                          | Augmentations Applied         | Training Images | Validation Images | Test Images |
| ---------------------------------------- | ----------------------------- | --------------- | ----------------- | ----------- |
| Balanced Tomato Layered Augmentation     | All augmentations at once     | 1190            | 150               | 150         |
| Original Tomato dataset (356 images)     | None (Original images)        | 248             | 71                | 37          |
| Only "Flip" augmentation                 | Flip                          | 496             | 142               | 74          |
| "Flip and Rotation" augmentations        | Flip and Rotation             | 744             | 213               | 111         |
| "Flip, Rotation and Saturation"          | Flip, Rotation and Saturation | 992             | 284               | 148         |


## Usage

The `Layerwise results.ipynb` notebook is self-contained and can be run cell by cell in a Jupyter environment to reproduce the experiments and results. The notebook is divided into sections, each corresponding to a different experiment with a specific data augmentation strategy.

## Methodology

The notebook investigates the effect of applying data augmentations in a "layer-wise" manner. For each experiment, the notebook contains the complete code for:
-   Downloading the specific pre-augmented and pre-split dataset from Roboflow.
-   Counting the number of images per class.
-   Training the YOLOv8 model on the training set.
-   Validating the model on the validation set.
-   Testing the model on the independent test set.

## Results

The output of each code cell in the notebook shows the results of the corresponding experiment, including training progress, validation metrics, and test metrics such as mean Average Precision (mAP). These results can be used to compare the performance of the model under different augmentation strategies.

