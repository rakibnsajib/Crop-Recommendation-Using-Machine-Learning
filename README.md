# Crop Prediction App Using Machine Learning

This project is a Streamlit web application that predicts the suitable crop to grow based on soil and environmental conditions. The prediction is powered by a trained machine learning model created in this project, using a dataset from Kaggle. The app takes various input parameters such as nitrogen, phosphorus, potassium, temperature, humidity, pH level, and rainfall, and predicts the best crop to grow under the given conditions.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Model and Scaler](#model-and-scaler)
- [Contributing](#contributing)
- [License](#license)

## Overview

The Crop Prediction App allows users to input the following parameters:
- Nitrogen (N)
- Phosphorus (P)
- Potassium (K)
- Temperature
- Humidity
- pH Level
- Rainfall

Based on these inputs, the app uses a pre-trained RandomForest model to predict the best crop for cultivation. The app maps the model's output to one of the following 22 crops:

- Rice, Maize, Chickpea, Kidneybeans, Pigeonpeas, Mothbeans, Mungbean, Blackgram, Lentil, Pomegranate, Banana, Mango, Grapes, Watermelon, Muskmelon, Apple, Orange, Papaya, Coconut, Cotton, Jute, Coffee

## Features

- Interactive user interface using Streamlit.
- Input fields for soil nutrients and environmental conditions.
- Predicts the best crop for cultivation based on the inputs provided.
- Uses a `MinMaxScaler` for input scaling.

## Dataset

The dataset used in this project is the [Crop Recommendation Dataset](https://www.kaggle.com/datasets/atharvaingle/crop-recommendation-dataset) from Kaggle, consisting of the following features:
- N (Nitrogen)
- P (Phosphorus)
- K (Potassium)
- Temperature
- Humidity
- pH
- Rainfall
- Label (Crop)

### Dataset Summary:
- Shape: (2200, 8)
- No missing or duplicate values were found.

The dataset was explored using correlation matrices and heatmaps to understand the relationships between the features.

## Model Training

- **X** (features) were selected as the nitrogen, phosphorus, potassium, temperature, humidity, pH, and rainfall columns.
- **y** (label) was the crop (label) column.
- The dataset was split into training and testing sets with a ratio of 80/20.
- Features were scaled using a `MinMaxScaler`.

The following models were evaluated:

| Model                       | Accuracy      |
|------------------------------|---------------|
| LogisticRegression            | 91.82%        |
| GaussianNB                    | 99.55%        |
| SVC                           | 96.82%        |
| KNeighborsClassifier          | 96.82%        |
| DecisionTreeClassifier        | 98.86%        |
| ExtraTreeClassifier           | 93.41%        |
| **RandomForestClassifier**    | **99.32%**    |
| BaggingClassifier             | 98.64%        |
| GradientBoostingClassifier    | 98.18%        |
| AdaBoostClassifier            | 9.55%         |

The **RandomForestClassifier** was selected for deployment due to its high accuracy of 99.32%. The model and the `MinMaxScaler` were saved as `model.pkl` and `minmaxscaler.pkl`.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/rhsbd/Crop-Recommendation-Using-Machine-Learning.git
   cd crop-prediction-app
   ```

2. **Install the required dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

3. **Make sure you have the following files in the root directory:**
    - `Crop_recommendation.csv`
    - `model.pkl`
    - `minmaxscaler.pkl`

4. **Run the Streamlit app:**

    ```bash
    streamlit run app.py
    ```


## Usage

1. **Once the app is running**, open your browser and navigate to the address provided by Streamlit (usually [http://localhost:8501/](http://localhost:8501/)).

2. **Input the required parameters** for soil nutrients and environmental conditions.

3. **Click the "Predict Crop" button** to get the predicted crop.


## Model and Scaler
- model.pkl: A pre-trained RandomForest model that predicts the crop based on the input features.
- minmaxscaler.pkl: A pre-fitted MinMaxScaler that scales the input features before feeding them into the model for prediction.

The model predicts a number between 1-22, corresponding to the following crop list:


| Crop ID | Crop Name     |
|---------|---------------|
| 1       | Rice          |
| 2       | Maize         |
| 3       | Chickpea      |
| 4       | Kidneybeans   |
| 5       | Pigeonpeas    |
| 6       | Mothbeans     |
| 7       | Mungbean      |
| 8       | Blackgram     |
| 9       | Lentil        |
| 10      | Pomegranate   |
| 11      | Banana        |
| 12      | Mango         |
| 13      | Grapes        |
| 14      | Watermelon    |
| 15      | Muskmelon     |
| 16      | Apple         |
| 17      | Orange        |
| 18      | Papaya        |
| 19      | Coconut       |
| 20      | Cotton        |
| 21      | Jute          |
| 22      | Coffee        |


## Contributing

Feel free to fork the repository and submit pull requests if you would like to contribute. Any enhancements, bug fixes, or suggestions are welcome!

### How to Contribute

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a pull request

## License
This project is licensed under the MIT License - see the LICENSE file for details.


### Notes:
- Update the `git clone` URL to your actual repository.
- Replace any placeholder links for downloading files (`model.pkl`, `minmaxscaler.pkl`, etc.).
