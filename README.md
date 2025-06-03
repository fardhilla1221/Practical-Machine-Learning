# Machine Learning Exercise Prediction

## Project Overview

This project aims to predict the quality of barbell lifting exercises using data from wearable fitness devices. Using machine learning algorithms, we classify exercises into 5 categories based on accelerometer data from belt, forearm, arm, and dumbbell sensors.

## Background

Using devices such as Jawbone Up, Nike FuelBand, and Fitbit, it's now possible to collect large amounts of data about personal activity. This project focuses on predicting **how well** exercises are performed, not just how much.

### Exercise Classes:
- **Class A**: Exactly according to specification (correct)
- **Class B**: Throwing elbows to the front (mistake)
- **Class C**: Lifting dumbbell only halfway (mistake)  
- **Class D**: Lowering dumbbell only halfway (mistake)
- **Class E**: Throwing hips to the front (mistake)

## Dataset

The data comes from 6 participants who performed barbell lifts correctly and incorrectly in 5 different ways:

- **Training Data**: 19,622 observations with 160 variables
- **Testing Data**: 20 test cases for final prediction
- **Source**: [Human Activity Recognition](http://web.archive.org/web/20161224072740/http:/groupware.les.inf.puc-rio.br/har)

## Files in this Repository

```
├── Analysis.Rmd          # R Markdown source file
├── Analysis.html         # Compiled HTML report  
├── predictions.csv       # Final predictions for 20 test cases
├── data/
│   ├── pml-training.csv  # Training dataset
│   └── pml-testing.csv   # Testing dataset
└── README.md            # This file
```

## Methodology

### Data Preprocessing
1. **Missing Data Handling**: Removed variables with >95% missing values
2. **Feature Selection**: Eliminated near-zero variance predictors
3. **Data Cleaning**: Removed identification variables and timestamps

### Models Implemented
1. **Decision Tree** (rpart)
2. **Random Forest** (rf) 
3. **Gradient Boosting Machine** (gbm)

### Cross Validation
- **Method**: 3-fold cross-validation
- **Purpose**: Estimate out-of-sample error and prevent overfitting

## Results

| Model | Accuracy | Expected Error |
|-------|----------|----------------|
| Decision Tree | ~75% | ~25% |
| Random Forest | **>99%** | **<1%** |
| GBM | ~96% | ~4% |

**Best Model**: Random Forest with **>99% accuracy** and **<1% expected out-of-sample error**.

## Key Findings

- Random Forest significantly outperformed other models
- Most important predictors are sensor measurements from belt and dumbbell
- Cross-validation confirmed model reliability
- Successfully predicted all 20 test cases

## How to Reproduce

### Prerequisites
```r
# Required R packages
install.packages(c("caret", "randomForest", "rpart", "rpart.plot", 
                   "corrplot", "ggplot2", "dplyr", "gbm"))
```

## View Online

📊 **[View Full Analysis Report]([https://yourusername.github.io/ML-Exercise/Analysis.html](https://fardhilla1221.github.io/Practical-Machine-Learning/Analysis.html))**


## Technologies Used

- **R**: Statistical computing and analysis
- **RStudio**: Development environment
- **R Markdown**: Reproducible research document
- **Caret Package**: Machine learning framework
- **Random Forest**: Primary prediction algorithm

## Course Information

This project was completed as part of:
- **Course**: Practical Machine Learning  
- **Platform**: Coursera
- **Institution**: Johns Hopkins University

## Citation

Velloso, E.; Bulling, A.; Gellersen, H.; Ugulino, W.; Fuks, H. Qualitative Activity Recognition of Weight Lifting Exercises. Proceedings of 4th International Conference in Cooperation with SIGCHI (Augmented Human '13). Stuttgart, Germany: ACM SIGCHI, 2013.

## License

This project is licensed under the MIT License - see the original data source for their terms of use.

---

**Author**:  Fardhilla Martina Haris

**Date**: 03 June 2025  
**Contact**: fardhilla11@gmail.com
