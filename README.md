
# InsightEngine

## Project Overview

**InsightEngine** is an innovative machine learning model designed to extract valuable product metrics from images. By leveraging advanced algorithms, this AI-powered tool efficiently retrieves continuous values (e.g., weight, volume) and categorical units (e.g., kg, liters) from product descriptions and images. The primary motive of this project is to enhance the accuracy and reliability of product data extraction, facilitating improved user experiences in digital marketplaces.

## Motive

In today’s digital marketplace, accurate product information is crucial for consumers and businesses alike. However, extracting this information from images and descriptions poses significant challenges. Traditional methods are often inefficient, leading to data inaccuracies and subpar user experiences. InsightEngine aims to address these issues by:

- **Improving Data Accuracy**: By utilizing machine learning techniques, we strive to enhance the precision of extracted product metrics, providing reliable data for consumers and retailers.
- **Enhancing User Experience**: Streamlining the process of finding and understanding product specifications improves shopping efficiency, ultimately leading to increased customer satisfaction.
- **Automating Data Extraction**: Automating the extraction of product metrics from images and descriptions minimizes manual effort, enabling businesses to focus on value-added activities.

## Key Objectives

1. **Develop Robust Machine Learning Models**: Create models capable of predicting continuous values and classifying categorical units from product descriptions and images.
2. **Utilize Advanced Feature Engineering**: Implement techniques such as Optical Character Recognition (OCR) and TF-IDF to effectively process and represent textual data.
3. **Optimize Performance**: Enhance model performance through memory optimization and efficient training processes, ensuring quick and accurate predictions.

## Methodology

The project follows a systematic approach involving several key steps:

1. **Image Processing and Text Extraction**: 
   - Utilize EasyOCR to preprocess images and extract textual information.

2. **Feature Engineering**: 
   - Transform textual data into numerical features using TF-IDF and convert categorical variables into numerical labels through label encoding.

3. **Model Training and Evaluation**:
   - Train machine learning models (RandomForest for regression and XGBoost for classification) to predict continuous values and classify units.

4. **Inference and Prediction**: 
   - Use the trained models to make predictions on the test dataset, combining outputs for a comprehensive result.

## Results

- **Value Prediction**: The RandomForest Regressor demonstrated strong performance with Mean Absolute Error as the evaluation metric, indicating effective prediction capabilities.
- **Unit Prediction**: The XGBoost Classifier achieved an F1 score of 0.74, highlighting a balanced performance in precision and recall.

## Conclusion

The successful training of machine learning models in **InsightEngine** illustrates the effectiveness of combining advanced feature engineering with powerful algorithms. This project showcases how intelligent data extraction can transform the digital marketplace, offering opportunities for future enhancements through further optimization and hyperparameter tuning.

## Future Work

- Implement additional feature engineering techniques to further improve model performance.
- Explore hyperparameter tuning for both models to enhance accuracy.
- Investigate real-time applications of the model in e-commerce settings.


