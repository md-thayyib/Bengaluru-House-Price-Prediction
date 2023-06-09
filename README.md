# House Price Prediction Project

This is a Flask-based web application that predicts house prices in bengaluru based on location, total square footage, number of bedrooms (BHK), and number of bathrooms.

## Setup and Installation

To run this project locally, follow these steps:

1. Clone the repository:

   ```
   $ git clone https://github.com/md-thayyib/Bengaluru-House-Price-Prediction.git
   $ cd Bengaluru-House-Price-Prediction
   ```

2. Install the required dependencies:

   ```
   $ pip install -r requirements.txt
   ```

3. Run the Flask server:

   ```
   $ python server/server.py
   ```

   This will start the Flask server on your local machine.

4. Open your web browser and go to `http://localhost:5000` to access the application.

## You have to options. Either you can use api end points or you can open `app.html` file to view the ui. 

## APP UI
<img src='client/Screenshot 2023-05-23 at 13.28.09.png'>

To use the ui app
open the html file in a browser

`client/app.html`


## API Endpoints

The following API endpoints are available:

### 1. Get Location Names

- Endpoint: `/get_location_names`
- Method: `GET`
- Description: Returns a list of available locations for house prediction.
- Response format: JSON

### 2. Predict Home Price

- Endpoint: `/predict_home_price`
- Method: `POST`
- Description: Predicts the price of a house based on the provided parameters.
- Request format: JSON
- Parameters:
  - `total_sqft` (float): Total square footage of the house.
  - `location` (string): Location of the house.
  - `bhk` (int): Number of bedrooms (BHK) in the house.
  - `bath` (int): Number of bathrooms in the house.
- Response format: JSON
- Response example:

  ```json
  {
    "estimated_price": 1000000
  }
  ```

## Utility Functions

Several utility functions are provided in the `util.py` module to support the prediction functionality.

### 1. `get_estimated_price(location, sqft, bhk, bath)`

Calculates the estimated price of a house based on the provided location, total square footage, number of bedrooms (BHK), and number of bathrooms.

- Parameters:
  - `location` (string): Location of the house.
  - `sqft` (float): Total square footage of the house.
  - `bhk` (int): Number of bedrooms (BHK) in the house.
  - `bath` (int): Number of bathrooms in the house.
- Returns:
  - `estimated_price` (float): Estimated price of the house.

### 2. `load_saved_artifacts()`

Loads the saved model and data artifacts required for the prediction.

## Data Columns and Model

The prediction model uses the following data columns:

- `sqft`: Total square footage of the house.
- `bath`: Number of bathrooms in the house.
- `bhk`: Number of bedrooms (BHK) in the house.
- `location_1`: Binary feature indicating if the house is located in `location_1`.
- `location_2`: Binary feature indicating if the house is located in `location_2`.
- ...

The model file (`banglore_home_prices_model.pickle`) and the data columns file (`columns.json`) are stored in the `model` directory.

## Example Usage

You can test the utility functions by running `util.py` directly. Here are some example usages:

```python
load_saved_artifacts()
print(get_location_names())
print(get_estimated_price("1st Phase JP Nagar", 1000, 3, 3))
print(get_estimated_price("1st Phase JP Nagar", 1000, 2, 2))
print(get_estimated_price("Kalhalli", 1000, 2, 2))  # other location
```

## Note:
- You can find the Jupyter notebook and the data used to train the model inside the notebook folder.
- If you want to host the app in a cloud you can do it by selecting any cloud and follow the procedure to do that. Then change the host names accordingly



### How I completed this

Credit for this project goes to [codebasics](https://www.youtube.com/@codebasics).
1. I followed codebasics' tutorial and learned all the concepts required for this project.
2. I reproduced the Jupyter notebook (.ipynb) and all the script files (.py) on my own without copying and pasting the code.
3. Once the project was successfully executed, I copied the HTML, JavaScript, and CSS files.
4. I utilized ChatGPT to customize the HTML file according to my requirements.

