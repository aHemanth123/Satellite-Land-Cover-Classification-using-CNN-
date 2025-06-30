# 🛰️ Satellite Land Cover Classification using CNN (EuroSAT Dataset)

This project performs land cover classification on satellite images using **Transfer Learning with ResNet50**, applied to the **EuroSAT RGB dataset**. The model classifies satellite images into one of 10 classes such as Forest, River, Residential, etc., with a robust deep learning pipeline that includes data augmentation and regularization techniques.

 

## 📂 Dataset

- **Source**: [EuroSAT RGB Dataset](https://github.com/phelber/eurosat)
- **Classes**:  
  `AnnualCrop`, `Forest`, `HerbaceousVegetation`, `Highway`, `Industrial`, `Pasture`, `PermanentCrop`, `Residential`, `River`, `SeaLake`
- **Images**: 27,500 RGB images (2750 per class)  
- **Format**: `.jpg`, 64x64 resolution  
- **Structure**:

EuroSAT_RGB_/2750/  
├── AnnualCrop/   
│   ├── AnnualCrop_1.jpg  
│   ├── AnnualCrop_2.jpg  
│   └── ...  
├── Forest/  
│   ├── Forest_1.jpg   
│   ├── Forest_2.jpg   
│   └── ...    
├── HerbaceousVegetation/    
│   ├── HerbaceousVegetation_1.jpg  
│   └── ...   
├── Highway/    
│   ├── Highway_1.jpg   
│   └── ...    
├── Industrial/   
│   ├── Industrial_1.jpg      
│   └── ...   
├── Pasture/      
│   ├── Pasture_1.jpg   
│   └── ...   
├── PermanentCrop/    
│   ├── PermanentCrop_1.jpg   
│   └── ...  
├── Residential/   
│   ├── Residential_1.jpg    
│   └── ...   
├── River/   
│   ├── River_1.jpg   
│   └── ...   
└── SeaLake/   
    ├── SeaLake_1.jpg   
    └── ...   





---

## 🧠 Model Architecture

- **Base**: Pretrained `ResNet50` (ImageNet weights)
- **Modifications**:
- Global Average Pooling
- Dense Layer with L2 regularization
- Dropout for regularization
- Batch Normalization
- Final Softmax output layer for 10-class classification

---

## 🛠️ Techniques Used

### ✅ Data Handling
- `ImageDataGenerator` with real-time augmentation
- Image normalization (rescale 1/255)
- Data splitting using `validation_split`

### ✅ Regularization & Overfitting Prevention
- Data Augmentation (rotation, shift, brightness, flip)
- Dropout layers
- L2 Regularization
- Batch Normalization
- EarlyStopping (monitoring validation loss)
- ReduceLROnPlateau (adaptive learning rate)

### ✅ Inference Pipeline
- Manual image preprocessing (flip, brightness, grayscale)
- Single image prediction with visualization
- Top class prediction with confidence score 
