1\.Machine Learning Approach 

The primary objec  ve of this project is to develop machine learning models that extract both con  nuous values (e.g., weight, volume) and categorical units (e.g., kg, liters) from product descrip  ons and images. The approach involves using a combina  on of regression techniques for predic  ng con  nuous values and classifica  on techniques for predic  ng categorical units. The en  re process consists of the following key steps: 

- Image Processing and Text Extrac  on: Preprocess images to extract textual informa  on using Op  cal Character Recogni  on (OCR) tools like EasyOCR. 
- Feature Engineering: Transform textual data (e.g., product descrip  ons) into numerical features using TF-IDF (Term Frequency-Inverse Document Frequency). Convert categorical variables (en  ty names) into numerical labels using label encoding. 
- Model Training and Evalua  on: Train machine learning models to predict con  nuous values and classify units using XGBoost and RandomForest algorithms. 
2. Machine Learning Models Used 
1. Value Predic  on (Regression Model) 
- Algorithm: RandomForest Regressor (RandomForestRegressor) 
- Features Used : 
- TF-IDF Vectorized Descrip  ons: Text data (product descrip  ons) transformed into numerical vectors using TF-IDF. 
- Encoded En  ty Name: En  ty names (e.g., product type) converted into numerical values via label encoding. 
- Training Process: 
- RandomForest Regressor is used to predict con  nuous values. 
- The model was trained with default hyperparameters (100 decision trees). 
- Evalua  on Metric: Mean Absolute Error (MAE), which measures the average absolute difference between predicted and actual values. 
2. Unit Predic  on (Classifica  on Model) 
- Algorithm: XGBoost Classifier (XGBClassifier) 
- Objec  ve Func  on: Mul  -class classifica  on (objec  ve='mul  :so  max'). 
- Features Used : 
  - TF-IDF Vectorized Descrip  ons: Same as in the regression model. 
  - Encoded En  ty Name: Similar label encoding applied to the en  ty names. 
- Training Process: 
- XGBoost Classifier was trained to predict categorical units (e.g., kg, liters). 
- Evalua  on Metric: Mul  -class log loss (eval\_metric='mlogloss'), which measures the performance of mul  -class classifica  on. 
3. Experiments 
1. Data Preprocessing 
- Image Preprocessing: Images were resized to 500x500 pixels and converted to grayscale to reduce complexity. EasyOCR was used to extract text from the images. 
- Textual Data Transforma  on: Product descrip  ons were vectorized using the TF-IDF technique to represent text as sparse matrices for memory efficiency. 
- En  ty Name Encoding: Categorical en  ty names were label-encoded to be used as numerical features in the machine learning models. 
2. Model Training 
- For value predic  on, RandomForest Regressor was trained using the transformed features.  
- For unit predic  on, XGBoost Classifier was trained using the same feature set to predict the product units, and its performance was evaluated using mul  -class log loss and F1-score. 
3. Memory Op  miza  on 
- Batch processing was applied during text extrac  on to manage memory more efficiently. Threads were used for parallelizing the extrac  on process. 
4. Inference and Predic  on 
- Both models (regression and classifica  on) were used to predict values and units for the test dataset. These predic  ons were combined into a final output. 
4. Conclusion 

The machine learning models were successfully trained to extract both con  nuous values and categorical units from product descrip  ons. The combined use of TF-IDF vectoriza  on for text features and label encoding for categorical variables provided an effec  ve representa  on of the data. 

- Value Predic  on: The RandomForest Regressor model performed well, with Mean Absolute Error providing an accurate measure of the predic  on performance. 
- Unit Predic  on: XGBoost Classifier yielded a balanced performance with an F1 score of 0.74, indica  ng a good trade-off between precision and recall. 

F1 Score = 0.74 

The results demonstrate the effec  veness of combining advanced feature engineering techniques 

with powerful machine learning models like RandomForest and XGBoost to solve complex predic  on tasks in digital marketplaces. Further op  miza  on and hyperparameter tuning could improve the models' performance even more. 
