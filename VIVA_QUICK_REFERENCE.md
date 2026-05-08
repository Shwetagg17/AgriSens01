# AgriSens - Quick Reference for Viva

## PROJECT SUMMARY (30 seconds)
AgriSens is a smart farming assistant that uses ML and DL to:
1. Recommend crops based on soil/environmental conditions (99.5% accuracy)
2. Detect plant diseases from leaf images (38 disease classes)
3. Provide real-time weather information

---

## KEY TECHNICAL DETAILS

### Crop Recommendation
- **Algorithm**: Random Forest Classifier
- **Accuracy**: 99.5%
- **Input Features**: 7 (N, P, K, Temperature, Humidity, pH, Rainfall)
- **Output**: 22 crop types
- **Model File**: RF.pkl

### Disease Detection
- **Algorithm**: Convolutional Neural Network (CNN)
- **Architecture**: 5 Conv blocks + Dense layers
- **Input**: 128x128 RGB images
- **Output**: 38 disease classes across 14 crops
- **Model File**: trained_plant_disease_model.keras

### Weather Forecast
- **API**: OpenWeatherMap
- **Method**: Geolocation-based
- **Data**: Temperature, Humidity, Wind, Description

---

## ALGORITHM EXPLANATIONS

### Random Forest (1 minute)
- **Type**: Ensemble learning (bagging)
- **How**: Creates 20 decision trees on different data samples
- **Prediction**: Majority vote from all trees
- **Why Best**: Highest accuracy, handles non-linearity, robust

### CNN Architecture (1 minute)
- **5 Convolutional Blocks**: Extract features (edges → patterns → complex features)
- **Max Pooling**: Reduces size, prevents overfitting
- **Dropout**: 25% and 40% to prevent overfitting
- **Dense Layers**: 1500 neurons → 38 neurons (classification)
- **Softmax**: Converts to probabilities

---

## DATASETS

### Crop Dataset
- **Size**: 2,200 samples
- **Features**: 7 numerical features
- **Classes**: 22 crops
- **Split**: 70% train, 30% test

### Disease Dataset
- **Training**: 70,295 images
- **Validation**: 17,572 images
- **Classes**: 38 diseases
- **Crops**: 14 types

---

## WORKFLOWS

### Crop Recommendation Flow
1. User enters 7 parameters
2. Input validation
3. Load RF model
4. Predict crop
5. Display result

### Disease Detection Flow
1. User uploads image
2. Resize to 128x128
3. Preprocess (normalize)
4. Load CNN model
5. Predict disease class
6. Map to disease name
7. Display result

---

## TECHNOLOGIES USED

**Frontend**: HTML, CSS, JavaScript
**Backend**: Python, Streamlit
**ML**: scikit-learn, TensorFlow/Keras
**APIs**: OpenWeatherMap
**Data**: Pandas, NumPy

---

## KEY ACHIEVEMENTS
✅ 99.5% crop recommendation accuracy
✅ 38 disease classes detection
✅ Real-time weather integration
✅ User-friendly interface
✅ Comprehensive solution

---

## LIMITATIONS
- Limited to 22 crops
- 38 diseases (can expand)
- Weather needs location permission
- Image quality affects disease detection

---

## FUTURE SCOPE
- Fertilizer recommendation
- Pest detection
- Yield prediction
- Mobile app
- IoT sensor integration
- Extended weather forecast

---

## COMMON VIVA QUESTIONS

**Q: Why Random Forest?**
A: Highest accuracy (99.5%), handles non-linear data, ensemble method reduces overfitting, robust to outliers.

**Q: Why CNN for images?**
A: Automatically learns features, handles spatial relationships, proven for image classification, hierarchical feature extraction.

**Q: How accurate is the system?**
A: Crop recommendation: 99.5%, Disease detection: High accuracy on validation set (87K+ images).

**Q: Real-world application?**
A: Yes, helps farmers make data-driven decisions, early disease detection, cost-effective, scalable.

**Q: Can it handle new data?**
A: Models generalize well, but can be retrained with new crops/diseases. Input validation ensures data quality.

**Q: How to improve accuracy?**
A: More training data, hyperparameter tuning, feature engineering, ensemble methods, transfer learning.

---

## QUICK STATS
- **Crops Supported**: 22
- **Diseases Detected**: 38
- **Crop Accuracy**: 99.5%
- **Training Images**: 70,295
- **Model Parameters**: Millions (CNN)
- **Trees in RF**: 20

---

## PROJECT STRUCTURE
```
AgriSens/
├── AgriSens-web-app/     (Frontend)
├── CROP-RECOMMENDATION/  (ML Model + Streamlit App)
├── PLANT-DISEASE-IDENTIFICATION/ (CNN Model + Streamlit App)
└── Datasets/            (Training Data)
```

---

**Remember**: Be confident, explain clearly, and demonstrate understanding of both ML/DL concepts and practical implementation!

