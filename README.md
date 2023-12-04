# Multimodal Model Pipeline for Medical Data

Welcome to the repository containing notebooks that illustrate the design, fine-tuning, and evaluation of multimodal models for medical data. In this project, we explore two different architectures based on BioBERT and CLIP models. The goal is to demonstrate the pipeline for fine-tuning and evaluating these models using the ROCCO and NIH datasets.

## Notebooks Overview

### 1. BioBERT and ResNet50 Model
- The first notebook showcases a model created by combining the BioBERT text encoder and ResNet50 image encoder. Fine-tuning is achieved through a contrastive loss (triplet_margin_loss) on the ROCCO dataset.
- Data preprocessing aligns with the model's design, and 100 data points are selected to showcase the entire pipeline.
- The model incorporates a linear head, and the notebook provides a visualization of the loss over three epochs.

### 2. CLIP Model with/Without No Grad Mode
- The second notebook is similar to the first, with the key difference being the use of the CLIP model for both text and image encoders. The model is fine-tuned on the ROCCO dataset using no grad mode, and also the for the second try the image encoder part is frozen during training.
- Results and loss plots are included in the notebook for comprehensive evaluation.

### 3. Evaluation of CLIP-Based Model on NIH Dataset
- The final notebook evaluates the CLIP-based model trained with no grad mode. Zero-shot evaluation is performed using the NIH dataset, and a pretrained model with a suitable head is utilized.
- The CLIP model was also loaded for this evaluation from HuggingFace.
- The limitations of the results are acknowledged, as the model was only fine-tuned for a few epochs on a limited dataset for demonstration purposes.

## Additional Tips for Performance Improvement

### Bonus: Beyond Increasing Dataset Size

Apart from increasing the dataset size, consider the following tips to enhance model performance:

1. **Temperature Function:**
   - Experiment with temperature scaling during training to adjust the model's confidence scores. This can potentially improve the discrimination ability of the model.

2. **Contrastive Loss Functions:**
   - Explore alternative contrastive loss functions besides triplet_margin_loss. Different loss functions may capture diverse aspects of the data relationships, potentially leading to better convergence.

3. **Unfreeze All Layers:**
   - Instead of freezing all layers during fine-tuning, selectively unfreeze certain layers, especially in the later stages of training. This allows the model to adapt to dataset-specific features.

4. **Hyperparameter Tuning:**
   - Perform systematic hyperparameter tuning, including learning rates, batch sizes, and optimization algorithms. Adjusting these parameters can significantly impact model convergence and performance.

5. **Data Augmentation:**
   - Apply diverse data augmentation techniques to artificially expand the dataset. This helps the model generalize better to unseen data patterns.

Due to time constraints, the provided code may require additional refinement for production use. If you have any questions or suggestions, don't hesitate to reach out!
