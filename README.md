
# InsightEngine

## Project Overview

**InsightEngine** is an innovative machine learning model designed to extract valuable product metrics from images. By leveraging advanced algorithms, this AI-powered tool efficiently retrieves continuous values (e.g., weight, volume) and categorical units (e.g., kg, liters) from product descriptions and images. The primary motive of this project is to enhance the accuracy and reliability of product data extraction, facilitating improved user experiences in digital marketplaces.


## Key Objectives

1. **Develop Robust Machine Learning Models**: Create models capable of predicting continuous values and classifying categorical units from product descriptions and images.
2. **Utilize Advanced Feature Engineering**: Implement techniques such as Optical Character Recognition (OCR) and TF-IDF to effectively process and represent textual data.
3. **Optimize Performance**: Enhance model performance through memory optimization and efficient training processes, ensuring quick and accurate predictions.

## The dataset consists of the following columns:

**index**: An unique identifier (ID) for the data sample
**image_link:** Public URL where the product image is available for download. Example link - https://m.media-amazon.com/images/I/71XfHPR36-L.jpg To download images use download_images function from src/utils.py. See sample code in src/test.ipynb.
**group_id:** Category code of the product
**entity_name:** Product entity name. For eg: “item_weight”
**entity_value:** Product entity value. For eg: “34 gram” Note: For test.csv, you will not see the column entity_value as it is the target variable.

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

## Output Format:
The output file should be a csv with 2 columns:

index: The unique identifier (ID) of the data sample. Note the index should match the test record index.
prediction: A string which should have the following format: “x unit” where x is a float number in standard formatting and unit is one of the allowed units (allowed units are mentioned in the Appendix). The two values should be concatenated and have a space between them. For eg: “2 gram”, “12.5 centimetre”, “2.56 ounce” are valid. Few invalid cases: “2 gms”, “60 ounce/1.7 kilogram”, “2.2e2 kilogram” etc. Note: Make sure to output a prediction for all indices. If no value is found in the image for any test sample, return empty string, i.e, “”. If you have less/more number of output samples in the output file as compared to test.csv, your output won’t be evaluated.

## File Descriptions:
## source files

**src/sanity.py:** Sanity checker to ensure that the final output file passes all formatting checks. Note: the script will not check if less/more number of predictions are present compared to the test file. See sample code in src/test.ipynb
**src/utils.py:** Contains helper functions for downloading images from the image_link.
**src/constants.py:** Contains the allowed units for each entity type.
**sample_code.py:** We also provided a sample dummy code that can generate an output file in the given format. Usage of this file is optional.

## Dataset files

**dataset/train.csv:** Training file with labels (entity_value).
**dataset/test.csv:** Test file without output labels (entity_value). Generate predictions using your model/solution on this file's data and format the output file to match sample_test_out.csv (Refer the above section "Output Format")
**dataset/sample_test.csv:** Sample test input file.
**dataset/sample_test_out.csv:** Sample outputs for sample_test.csv. The output for test.csv must be formatted in the exact same way. Note: The predictions in the file might not be correct
## Constraints
1. You will be provided with a sample output file and a sanity checker file. Format your output to match the sample output file exactly and pass it through the sanity checker to ensure its validity. Note: If the file does not pass through the sanity checker, it will not be evaluated. You should recieve a message like Parsing successfull for file: ...csv if the output file is correctly formatted.

2. You are given the list of allowed units in constants.py and also in Appendix. Your outputs must be in these units. Predictions using any other units will be considered invalid during validation.

## Evaluation Criteria
Submissions will be evaluated based on F1 score, which are standard measures of prediction accuracy for classification and extraction problems.

Let GT = Ground truth value for a sample and OUT be output prediction from the model for a sample. Then we classify the predictions into one of the 4 classes with the following logic:

1. True Positives - If OUT != "" and GT != "" and OUT == GT
2. False Positives - If OUT != "" and GT != "" and OUT != GT
3. False Positives - If OUT != "" and GT == ""
4. False Negatives - If OUT == "" and GT != ""
5. True Negatives - If OUT == "" and GT == ""
Then, F1 score = 2PrecisionRecall/(Precision + Recall) where:

1. Precision = True Positives/(True Positives + False Positives)
2. Recall = True Positives/(True Positives + False Negatives)
## Submission File
Upload a test_out.csv file in the Portal with the exact same formatting as sample_test_out.csv

## Appendix
```bash
entity_unit_map = {
  "width": {
    "centimetre",
    "foot",
    "millimetre",
    "metre",
    "inch",
    "yard"
  },
  "depth": {
    "centimetre",
    "foot",
    "millimetre",
    "metre",
    "inch",
    "yard"
  },
  "height": {
    "centimetre",
    "foot",
    "millimetre",
    "metre",
    "inch",
    "yard"
  },
  "item_weight": {
    "milligram",
    "kilogram",
    "microgram",
    "gram",
    "ounce",
    "ton",
    "pound"
  },
  "maximum_weight_recommendation": {
    "milligram",
    "kilogram",
    "microgram",
    "gram",
    "ounce",
    "ton",
    "pound"
  },
  "voltage": {
    "millivolt",
    "kilovolt",
    "volt"
  },
  "wattage": {
    "kilowatt",
    "watt"
  },
  "item_volume": {
    "cubic foot",
    "microlitre",
    "cup",
    "fluid ounce",
    "centilitre",
    "imperial gallon",
    "pint",
    "decilitre",
    "litre",
    "millilitre",
    "quart",
    "cubic inch",
    "gallon"
  }
}
```
