# Deep-Learning-Image-Classification (Oxford Flowers 102)

This project presents a comparative analysis of Deep Learning approaches for multi-class image classification using the Oxford Flowers 102 dataset. It was implemented in Python using the TensorFlow/Keras library.

## Architectures Evaluated

The study focuses on evaluating three different approaches:

* **Custom CNN:** A convolutional neural network designed and trained from scratch.
* **Transfer Learning:** Using a pretrained model (MobileNetV2) with ImageNet weights.
* **Fine-Tuning:** Adapting a pretrained model by unfreezing its final layers to improve specialization on the target dataset.

##  Methodology and Preprocessing

The workflow pipeline was developed using the TensorFlow Dataset API and includes:

* **Preprocessing:** Resizing images to 224 × 224 pixels and normalization.
* **Data Augmentation:** Applying data pipeline I/O optimizations using the `AUTOTUNE` parameter.
* **Training Configuration:** Using the `Adam` optimizer, `Sparse Categorical Crossentropy` loss function, a batch size of 32, and 15 training epochs.

## Key Findings

* **Fine-Tuning:** Achieved the best generalization performance, reaching **76.81% accuracy** on the test set. Fine-tuning the final layers significantly reduced the gap between training and test performance compared to standard transfer learning.
* **Transfer Learning:** Enabled rapid learning, achieving **73.98% test accuracy**. However, it exhibited significant overfitting, with a training accuracy of 98.63%. Nevertheless, it remains a good option for resource-constrained devices due to the lightweight MobileNetV2 architecture.
* **Custom CNN:** Failed to converge effectively, exhibiting underfitting and achieving only **12.68% test accuracy**. The limited training data (1,020 images) proved insufficient for learning 102 complex classes from scratch.
* **Confusion Matrix Analysis:** Most classification errors occurred among flowers with high morphological similarity, such as species belonging to the Asteraceae family. In contrast, flower species with distinctive colors achieved accuracy rates exceeding 90%.
