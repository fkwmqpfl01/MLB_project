# MLB_project

I participated in the Google Machine Learning Bootcamp 2024 and worked on the Gemma Sprint project. 

## Electric Vehicle Charging Station Locator
This project demonstrates a Python-based system for finding the nearest electric vehicle (EV) charging station from a user-specified bus stop using natural language input and geolocation data. It utilizes Keras with a JAX backend for potential NLP integration (using the Gemma Language Model), geospatial distance calculations, and data handling with pandas.

## Table of Contents
1. Installation
2. Project Overview
3. Data Preparation
4. System Workflow
5. Dependencies
6. How to Run

## Installation  
To run this project, you'll need to install several Python libraries. Install the required libraries using the following commands:

```
pip install pandas geopy keras keras-nlp jax
```
If using Kaggle data, ensure you configure your Kaggle API credentials properly.

## Kaggle API Configuration
1. Obtain your API credentials by following these steps:

- Log into your Kaggle account.
- Go to "Account" and select "Create API Token."
- This will download a kaggle.json file containing your KAGGLE_USERNAME and KAGGLE_KEY.
2. Set your Kaggle API credentials in the environment variables before running the code:
```
os.environ["KAGGLE_USERNAME"] = "your_username"
os.environ["KAGGLE_KEY"] = "your_key"
```
## Project Overview
This project consists of several components:

1. Data Loading: Loads data from CSV files containing EV charging station locations and bus stop locations.
2. Natural Language Processing (NLP): Uses Keras NLP (optionally with JAX backend) and the Gemma model to extract the bus stop name from user input.
3. Geospatial Search: Uses the geodesic distance method from geopy to find the nearest charging station to the identified bus stop.
## Data Preparation
To use this system, you will need two CSV files:

1. EV Charging Station Data (station.csv)  
   Contains columns such as:  
- 충전소명 (Charging Station Name)
- 위도경도 (Latitude, Longitude)
- 주소 (Address)
2. Bus Stop Data (bus_stop.csv)    
   Contains columns such as:
- 정류장명 (Bus Stop Name)
- 위도 (Latitude)
- 경도 (Longitude)  

Ensure the data is correctly formatted and encoded (preferably cp949 for Korean characters).

## System Workflow
1. Load Data: The system reads in the EV charging station and bus stop data from the provided CSV files.

2. User Input: The user is prompted to input a sentence that includes a bus stop name (in Korean).

3. NLP Model (Gemma): Using the pre-trained GemmaCausalLM model, the system extracts the bus stop name from the user input. (Note: In the current implementation, this step is commented out and requires a properly configured Gemma model).

4. Bus Stop Identification: Once the bus stop is identified from the user's input, the system searches for the bus stop's coordinates in the bus stop dataset.

5. Nearest Charging Station Calculation: The geodesic function from geopy calculates the distance between the bus stop and all nearby charging stations. The nearest station is selected and its information (name, address, and distance) is displayed to the user.

## Dependencies
- Pandas: For reading and handling CSV files (pip install pandas).
- Geopy: For calculating geographical distances between two points (pip install geopy).
- Keras: For potential NLP tasks and modeling (pip install keras).
- Keras-NLP: To leverage pre-trained NLP models for extracting bus stop names (pip install keras-nlp).
- JAX: (Optional) For using JAX as a backend for Keras (pip install jax).

## How to Run
1. Clone the Repository
```
git clone https://github.com/your-repository.git
cd your-repository
```
2. Prepare Your Data

Ensure you have two CSV files (station.csv and bus_stop.csv) and place them in the directory.
Modify the paths in the code to point to your data files.
3. Run the Script
```
python main.py
```
4. Input a Query

The system will prompt you to enter a location description including a bus stop name in Korean (e.g., 가까운 서울역 정류장을 알려주세요). 

5. View Output  

The system will extract the bus stop name and print the nearest EV charging station, along with the distance and address.

## Example
```
근처 정류장 이름을 포함해 위치를 입력하세요: 서울역 근처 충전소
가장 가까운 충전소는 '서울충전소'이며, 주소는 서울특별시 중구 태평로입니다. 거리: 1.34 km
```

## Future Improvements
Integrating the Gemma language model fully to enhance natural language understanding.
Expanding to support different languages or multi-lingual inputs.
Implementing a GUI or web-based frontend for ease of use.

### Contributors
fkwmqpfl01


#Google #GoogleMachineLearningBootcamp #GemmaSprint
