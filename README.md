# Classification-of-Alzheimer-s-using-MRI-Images
Classification of Alzheimer's Disease (AD) and Mild Cognitive Impairment (MCI) using MRI Images


# Deep Learning / CNN
## Project Level : High-Intermediate 
*You may find the report of the project under the name "Classification of Alzheimer's Disease (AD) and Mild Cognitive Impairment (MCI) using MRI Images_ Solouki.PDF"*

### Project Goal
To classify patients into two categories — Alzheimer’s Disease (AD) and Mild Cognitive Impairment (MCI) — based on MRI brain images. The aim is to assist in early diagnosis and intervention for cognitive decline.

---

### **Project Description**  
The dataset consists of 1,654 grayscale MRI images labeled as either AD (Alzheimer’s Disease) or MCI (Mild Cognitive Impairment). The project includes image preprocessing, augmentation, model training, evaluation, and performance analysis. The goal is to build a convolutional neural network (CNN) that can accurately classify patients based on MRI scans, thereby aiding early detection of neurodegenerative diseases.

---

### **Language and Libraries Used**  
- **Language**: Python  
- **Libraries**:  
  - NumPy  
  - OpenCV (for image preprocessing)  
  - TensorFlow / Keras (for model development and training)  
  - Matplotlib (for data visualization and plotting results)

---

### **Methods and Models**

#### **1. Image Preprocessing**
- Images resized to **128×128** (based on the baseline paper’s recommendation).
- Grayscale conversion using `cv2.IMREAD_GRAYSCALE`.
- Instead of traditional **Min-Max normalization**, **Batch Normalization** (using the dataset’s mean and standard deviation) was applied to address the varying intensity of medical MRI images.

#### **2. Data Splitting**
- 95% for training/testing and 5% for testing.
- Of the 95% training data, 90% was used for training and 10% for validation.

#### **3. Data Augmentation**
- Initially, combined augmentation techniques degraded model accuracy.
- Applying augmentation techniques separately (rotation, zoom, shift, flip, crop) improved performance.
- Data augmentation preserved class balance and improved training diversity.

#### **4. Model Implementation**
- **CNN architecture** inspired by the baseline paper.
- Initial weights: **Glorot Uniform** initializer.
- Layers:
  - Convolutional layers (with 32 filters and kernel size 3×3)
  - **Batch Normalization**
  - **MaxPooling2D**
  - Fully connected layers: 128 → 64 → 2 neurons (output)
- **Activation functions**: ReLU (hidden layers), Softmax (output)
- **Loss Function**: Binary Cross-Entropy  
- **Optimizer**: Adam with a learning rate of 0.1  

#### **5. Evaluation & Performance**
- **Accuracy (Test)**: 82.29%  
- **Precision**: 85.62%  
- **Recall**: 69.08%  
- **F1 Score**: 76.47%  
- **AUC-ROC** curve used for evaluating classification performance.
- Confusion matrix was used to compute metrics like sensitivity and specificity.
- Observed overfitting signs led to reducing epochs from 25 to 20 for better generalization.

---
