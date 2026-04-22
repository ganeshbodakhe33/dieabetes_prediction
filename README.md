# CheqDiabetes - Diabetes Prediction Web Application


This project is a web application that predicts the likelihood of an individual having diabetes based on several diagnostic measurements. It uses a K-Nearest Neighbors (KNN) machine learning model trained on the Pima Indians Diabetes Database. The model is deployed using a Flask web server.

## Features

-   Simple web interface to input diagnostic measures.
-   Real-time prediction of diabetes risk.
-   Displays the probability of having diabetes as a percentage.
-   Built with Python, Scikit-learn, and Flask.

## Model Details

-   **Model:** K-Nearest Neighbors (KNN) Classifier
-   **Dataset:** `diabetes.csv` (Pima Indians Diabetes Database)
-   **Features:** The model uses the following 8 features for prediction:
    1.  Pregnancies
    2.  Glucose
    3.  Blood Pressure
    4.  Skin Thickness
    5.  Insulin
    6.  BMI (Body Mass Index)
    7.  Diabetes Pedigree Function
    8.  Age

## Technology Stack

-   **Backend:** Python, Flask
-   **Machine Learning:** Scikit-learn, Pandas, NumPy
-   **Deployment:** Gunicorn

## Project Structure

```
.
├── app.py              # Main Flask application file
├── model.py            # Script to train the model and create the .pkl file
├── testing5.pkl        # Pre-trained and serialized KNN model
├── diabetes.csv        # Dataset for training the model
├── requirements.txt    # Python dependencies
├── Procfile            # Specifies commands for the app on startup (for Heroku)
├── LICENSE             # Apache 2.0 License
└── templates/
    ├── index.html      # Home page with the input form
    └── result.html     # Page to display the prediction result
```

## Setup and Local Execution

To run this project on your local machine, follow these steps:

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/ganeshbodakhe33/dieabetes_prediction.git
    cd dieabetes_prediction
    ```

2.  **Create and activate a virtual environment (recommended):**
    ```sh
    python -m venv venv
    # On Windows
    venv\Scripts\activate
    # On macOS/Linux
    source venv/bin/activate
    ```

3.  **Install the required dependencies:**
    ```sh
    pip install -r requirements.txt
    ```

4.  **Run the Flask application:**
    ```sh
    python app.py
    ```

5.  **Access the application:**
    Open your web browser and navigate to `http://127.0.0.1:5000`.

## How It Works

The application workflow is as follows:
1.  The user accesses the homepage, which is rendered from `templates/index.html`.
2.  The user fills in the form with their health metrics and clicks "Predict".
3.  The form data is sent via a POST request to the `/predict` endpoint in `app.py`.
4.  The Flask app receives the data, formats it into a Pandas DataFrame, and feeds it into the pre-trained KNN model (`testing5.pkl`).
5.  The model's `predict_proba` method calculates the probability of the positive class (diabetes).
6.  The result is formatted into a percentage and rendered on the `templates/result.html` page, informing the user of their diabetes risk.

## License

This project is licensed under the Apache License 2.0. See the [LICENSE](LICENSE) file for more details.
