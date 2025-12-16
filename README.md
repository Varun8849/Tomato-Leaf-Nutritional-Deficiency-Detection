# Layer-wise Analysis of Data Augmentation for Tomato Disease Detection

This repository contains the code and results for a research paper on analyzing the impact of different data augmentation strategies on a YOLOv8 model for tomato disease detection. The experiments are conducted on a custom tomato dataset with various augmentations applied in a layer-wise manner.

## Description

The primary goal of this research is to evaluate how different data augmentation techniques, when applied sequentially, affect the performance of a YOLOv8 model. The experiments are performed on a dataset of tomato images to detect various diseases. The Jupyter notebook `Layerwise results.ipynb` in this repository contains the complete implementation of the experiments, including data loading, model training, and evaluation.

## Reproducibility and Workflow

To ensure a fully transparent, leakage-safe, and reproducible workflow, we have utilized Roboflow for dataset management and a dedicated GitHub repository for the code. This allows independent researchers to reconstruct the dataset splits, reproduce model training, and verify all reported results.

### Dataset Partitioning and Augmentation
Dataset partitioning and data augmentation were performed using Roboflow, which provides a standardized, version-controlled, and reproducible pipeline for dataset management. The original tomato subset was uploaded to Roboflow, where it was automatically split into training, validation, and test subsets using a fixed 60-25-15 ratio. 

**Importantly, all augmentation operations were applied exclusively to the training subset within Roboflow, while the validation and test subsets were preserved in their original, unaltered form, thereby ensuring strict data leakage prevention.**

### Code and Experiments
This GitHub repository contains the complete model training, evaluation, and analysis code. This includes fully documented Python notebooks covering YOLOv8 training, layer-wise experiments, ablation studies, and evaluation metrics. The notebooks explicitly record the layer-wise augmentation outcomes (image counts after each augmentation stage) as reported in the paper, ensuring consistency between the dataset generation process and the experimental results.

### Dataset Summary
The following table provides a summary of the image sets used for training, testing, and validation for each experiment to ensure reproducibility.

| Experiment Name                          | Augmentations Applied         | Training Images | Validation Images | Test Images |
| ---------------------------------------- | ----------------------------- | --------------- | ----------------- | ----------- |
| Balanced Tomato Layered Augmentation     | All augmentations at once     | 1190            | 150               | 150         |
| Original Tomato dataset (356 images)     | None (Original images)        | 248             | 71                | 37          |
| Only "Flip" augmentation                 | Flip                          | 496             | 142               | 74          |
| "Flip and Rotation" augmentations        | Flip and Rotation             | 744             | 213               | 111         |
| "Flip, Rotation and Saturation"          | Flip, Rotation and Saturation | 992             | 284               | 148         |

## Resources
-   **GitHub (training & evaluation code):** [https://github.com/Varun8849/Tomato-Leaf-Nutritional-Deficiency-Detection](https://github.com/Varun8849/Tomato-Leaf-Nutritional-Deficiency-Detection)
-   **Roboflow Dataset (splitting & augmentation):** [https://universe.roboflow.com/tomato-nutrition/balanced-tomato-dataset-sfqxc](https://universe.roboflow.com/tomato-nutrition/balanced-tomato-dataset-sfqxc)


## Usage

The `Layerwise results.ipynb` notebook is self-contained and can be run cell by cell in a Jupyter environment to reproduce the experiments and results. The notebook is divided into sections, each corresponding to a different experiment with a specific data augmentation strategy.

## Results

The output of each code cell in the notebook shows the results of the corresponding experiment, including training progress, validation metrics, and test metrics such as mean Average Precision (mAP). These results can be used to compare the performance of the model under different augmentation strategies.

