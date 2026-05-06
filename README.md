# Project README: YOLOv8 Object Detection on Custom Dataset

## Overview
This project demonstrates how to train a YOLOv8 object detection model on a custom dataset using Roboflow and Ultralytics YOLOv8. The goal is to detect specific objects (in this case, 'helmet') in images.

## Steps Performed:

1.  **Environment Setup**: Verified GPU access and installed necessary libraries (ultralytics, roboflow).
2.  **CLI Basics & Pre-trained Model Inference**: Demonstrated basic YOLOv8 command-line interface (CLI) usage and performed inference using a pre-trained COCO model (`yolov8n.pt`).
3.  **Custom Dataset Preparation (Roboflow)**: Utilized Roboflow to manage and export a custom dataset ('construction-safety-yol') in YOLOv8 format. This included downloading the dataset programmatically.
4.  **Custom Model Training**: Trained a YOLOv8s model (`yolov8s.pt`) on the custom dataset for 25 epochs. The training utilized images scaled to 800 pixels.
5.  **Model Validation**: Validated the custom-trained model to evaluate its performance on unseen data.
6.  **Custom Model Inference**: Performed inference on new images using the custom-trained model.
7.  **Model Deployment (Roboflow)**: Deployed the trained model weights to Roboflow's infrastructure for cloud-based inference.

## Results Analysis

### Training Performance (25 Epochs)
The model was trained with the following key metrics observed during the last epoch:

*   **Box Loss**: 0.748
*   **Class Loss**: 0.6731
*   **dFL Loss**: 0.9043
*   **mAP50**: 0.389 (Mean Average Precision at IoU threshold 0.5)
*   **mAP50-95**: 0.296 (Mean Average Precision averaged over IoU thresholds from 0.5 to 0.95)

Upon validation of the `best.pt` model, the following metrics were obtained:

*   **Precision (P)**: 0.602
*   **Recall (R)**: 0.55
*   **mAP50**: 0.390
*   **mAP50-95**: 0.299

The training results indicate that the model has learned to detect the specified class ('helmet') to a reasonable degree. The mAP50-95 of 0.299 suggests room for improvement, possibly through more epochs, data augmentation, or hyperparameter tuning. Visualizations like the confusion matrix and results plots (`confusion_matrix.png`, `results.png`, `val_batch0_pred.jpg`) were generated to further inspect training progress and predictions.

### Custom Model Inference
Inference with the custom-trained model on test images showed successful detection of helmets. For example, one test image (`001337_jpg.rf.76c5ba459c3f2b0de7dad900a1fb0a90.jpg`) identified two 'helmet' instances with confidence scores of 0.742 and 0.427 respectively. This demonstrates the model's ability to localize and classify objects on new, unseen data from the test set.

### Deployment on Roboflow
The model was successfully deployed to Roboflow, making it accessible via an API. Subsequent inference using the deployed model confirmed its functionality, returning JSON predictions for a randomly selected test image.

## Conclusion
This project provides a comprehensive workflow for developing and deploying custom object detection models using YOLOv8 and Roboflow. While the current model shows promising initial results, further optimization could lead to enhanced performance and robustness in real-world applications.

## Resources
*   [Roboflow Notebooks](https://github.com/roboflow/notebooks)
*   [Roboflow YouTube](https://www.youtube.com/c/Roboflow)
*   [Roboflow Discuss](https://discuss.roboflow.com/)
*   [Roboflow Models](https://roboflow.com)
*   [Roboflow Formats](https://roboflow.com/formats)
*   [Roboflow Templates](https://roboflow.com/templates)
