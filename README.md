# Logistic Regression on 2 Datasets (Gradio + Flask)

## What is in this folder
| File | What it is |
|---|---|
| logistic_regression_friend.ipynb | Main notebook (code, graphs, Gradio UI, Flask UI) |
| heart.csv | Dataset 1: predicts heart disease (1 = Yes, 0 = No) |
| banknote.csv | Dataset 2: predicts if a banknote is forged (1 = Forged, 0 = Genuine) |
| README_friend.md | This file |

## Datasets
1. Heart Disease (Cleveland data): 303 patients, 8 features, target = HeartDisease
   Features: age, sex, cp (chest pain type), trestbps (resting blood pressure),
   chol (cholesterol), thalach (max heart rate), exang (exercise angina), oldpeak (ST depression)
2. Banknote Authentication (UCI): 1372 notes, 4 features, target = Class
   Features: Variance, Skewness, Curtosis, Entropy (taken from banknote images)

## How to run
1. Put all 4 files in one folder.
2. Install the libraries:
   pip install pandas scikit-learn matplotlib gradio flask jupyter
3. Open Jupyter Notebook and open logistic_regression_friend.ipynb
4. Click Kernel > Restart & Run All (or run the cells one by one from top to bottom).

## Using your own file path
In Step 2 of the notebook, change the path. In Windows, right-click the file,
choose "Copy as path" and paste it like this:
    path1 = r"C:\Users\YourName\Downloads\heart.csv"
(Keep the letter r before the quotes and remove the extra quotes Windows adds.)

## UIs
- Gradio: opens inside the notebook, or at http://127.0.0.1:7860
- Flask: open http://127.0.0.1:5000 in your browser
  (Pages: /heart and /banknote)

## What the notebook does
1. Loads the CSV with pandas
2. Draws a bar graph of the classes (matplotlib)
3. Splits data 80% train / 20% test
4. Scales the data and trains LogisticRegression
5. Prints accuracy and classification report
6. Draws a confusion matrix and a feature coefficient graph
7. Builds the Gradio and Flask apps for prediction

## Results (approximate)
- Heart Disease accuracy: about 84%
- Banknote accuracy: about 98%

## Test values
- Heart: 60, 1, 0, 140, 260, 110, 1, 3.0 -> Heart Disease
- Banknote: -3.5, -8.0, 9.0, -2.0 -> Forged
- Banknote: 3.6, 8.7, -2.8, -0.4 -> Genuine

## Note about the heart dataset
The original file has the target reversed (0 = disease). In heart.csv the column
HeartDisease is already fixed, so 1 = disease and 0 = no disease.

## Problems?
- "Address already in use" in Flask: restart the kernel or change port=5000 to port=5001.
- "File not found": check that the CSV files are in the same folder as the notebook, or fix the path.
