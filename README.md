# Zhongli_Housing_Price_Forecast_Map
This repository contains a Python-based web application for predicting house prices in Zhongli District, Taoyuan City.
The machine learning part using 
The application is divided into two main parts:
Some essential data will use Selenium for web scraping and Flask for the web interface.

## [Housing_Price Predict HTML Demo](https://xkllkx.github.io/Zhongli_Housing_Price_Forecast_Map/loan-prediction-web/templates/form.html)
The machine learning model is built using **sklearn**, and the database used by the model includes:
1. Real transaction data of Zhongli District from 2021 to 2022 (a total of 6362 records)
- Longitude and latitude coordinates of each address (used for distance calculation and map display)
- Neighborhood of each address (used for map display)
2. Buildings within one-kilometer radius (a total of 500*n records)
- Quantity categories:
  + Schools (kindergartens, elementary schools, junior high schools, high schools, universities, universities of science and technology)
  + Hospitals, clinics
  + Parks, gyms (National Sports Centers)
  + supermarkets, hypermarkets (RT-Mart, Carrefour), vegetable markets, night markets
  + hardware stores
  + Restaurants, cafes, convenience stores
  + Gas stations
  + factories (processing zones)
  + Cram schools
  + parking lots
  + banks, ATMs
  + Museums, art galleries, tourist attractions, cinemas, libraries
  + Transportation facilities (buses, MRT)
- Categorized by the closest distance:
  + Department stores
  + business districts
  + Transportation facilities (highways, buses, MRT, high-speed rail, trains)
  + Night markets, vegetable markets, supermarkets
  + convenience stores
  + schools
  + cinemas, libraries, museums, art galleries
    
When using the user interface, the user will be asked to input information such as the address, land type, building type, and more. The corresponding data will be retrieved via web scraping and Google Maps API, and then fed into the model to generate a house price prediction.

## [Housing_Price Map HTML Demo](https://xkllkx.github.io/Zhongli_Housing_Price_Forecast_Map/loan-prediction-web/templates/big_map_try.html)
In addition to displaying real transaction data on the map, the application also includes features such as price color maps, heat maps, and neighborhood boundaries using polygon measurements. The map functionalities are handled using **folium**, and the entire user web interface is connected via **Flask**.

# How to use this repo
## Prerequisites
### Installation
- download ChromeDriver
```bash
pip install Flask pandas numpy joblib selenium
```
- Make sure the following CSV files are in the project directory:
  - viliage_UID.csv
  - chungli_ML.csv
  - detail.csv (this will be generated by the script)
  - Ensure the pre-trained model house_price_predict_2022_05_28.pkl is in the project directory.

### Housing_Price Predict
1. Start the Flask server
```bash
python app.py
```
2. Access the web application
- Open your web browser and go to target URL.

3. Enter the required details in the form:
- Web Interface Usage
  - Address
  - Land Type
  - Building Type
  - Use
  - Compartment
  - Management
  - Note
  - Balcony
  - Elevator

4. Click on the "Submit" button to get the prediction.
