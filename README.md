# Potato-Disease-Classification-
A computer vision system that automatically identifies potato plant diseases from leaf images using convolutional neural networks. This project helps farmers and agricultural specialists quickly diagnose potato plant health issues for timely intervention.

## Project Overview

This system classifies potato plants into three categories:
- **Healthy**: Normal, disease-free potato plants
- **Early Blight**: Fungal infection causing dark spots with target-like rings
- **Late Blight**: Serious fungal disease that can destroy entire crops

The model achieves **93.06% accuracy** on test data, making it suitable for real-world agricultural applications.

## Problem Statement

Potato diseases can cause significant crop losses if not detected early. Traditional diagnosis requires:
- Expert knowledge from agricultural specialists
- Time-consuming manual inspection
- Potential for human error in early disease stages
- Limited availability of experts in remote agricultural areas

This automated system provides immediate, accurate disease assessment to support timely agricultural decisions.

## Dataset Information

**Source**: Kaggle Potato Plant Diseases Dataset
- **Total Images**: 2,152 high-resolution plant images
- **Image Size**: 200x200x3 (RGB)
- **Classes**: 3 disease categories

### Class Distribution
- **Early Blight**: 1,000 images (46.5%)
- **Late Blight**: 1,000 images (46.5%) 
- **Healthy**: 152 images (7.0%)

**Data Challenge**: Significant class imbalance with healthy plants being underrepresented, reflecting real-world agricultural datasets where disease samples are more commonly collected.

### Key Architecture Decisions
- **Progressive Filter Increase**: 32→64→128 for hierarchical feature learning
- **Heavy Dropout (0.7)**: Prevents overfitting on limited dataset
- **Moderate Depth**: 3 conv blocks balance complexity with training efficiency
- **Softmax Output**: Multi-class probability distribution

## 📈 Training Strategy

### Data Splitting (80-10-10)
- **Training**: 1,720 images (80%)
- **Validation**: 216 images (10%)  
- **Test**: 216 images (10%)

### Training Configuration
- **Optimizer**: Adam (learning_rate=0.001)
- **Loss Function**: Sparse Categorical Crossentropy
- **Epochs**: 7 (optimal convergence point)
- **Batch Processing**: Efficient memory management

### Data Quality Assurance
- **Leakage Detection**: Automated similarity analysis between splits
- **Stratified Splitting**: Maintains class distribution across all sets
- **Image Preprocessing**: Normalized to [0,1] range for stable training

## Performance Results

### Final Model Performance
- **Test Accuracy**: 93.06%
- **Training Accuracy**: 97.03%
- **Validation Accuracy**: 95.83%
- **Overfitting Control**: 1.19% train-val gap

## Technologies Used
- **Framework**: TensorFlow/Keras
- **Image Processing**: OpenCV, PIL
- **Data Analysis**: NumPy, Pandas
- **Visualization**: Matplotlib, Seaborn
- **ML Utilities**: Scikit-learn

## Applications

### Agricultural Use Cases
- **Field Diagnosis**: Real-time disease detection using mobile devices
- **Crop Monitoring**: Large-scale automated plant health assessment  
- **Early Warning**: Preventive disease management systems
- **Extension Services**: Supporting agricultural consultants in remote areas

### Economic Impact
- **Reduced Crop Losses**: Early intervention prevents disease spread
- **Cost Efficiency**: Automated screening reduces expert consultation needs
- **Scalability**: Single system can monitor thousands of plants
- **Accessibility**: Brings expert-level diagnosis to rural farming communities

