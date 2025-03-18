
![surfer pic](https://github.com/Lanceowesalot/sqlalchemy_challenge/blob/main/SurfsUp/Images/Male%20Surfer.jpg)

# **Flask API & Climate Data Analysis**
This project provides an API to access historical climate data from a SQLite database. The Flask application allows users to query precipitation data, temperature observations, and summary statistics based on user-defined date ranges.

---

## **📌 Table of Contents**

1. [Project Overview](#project-overview)
2. [Dataset & Database](#dataset--database)
3. [Flask API Endpoints](#flask-api-endpoints)
4. [Setup & Installation](#setup--installation)
5. [Running the Application](#running-the-application)
6. [Usage & Query Examples](#usage--query-examples)
7. [Conclusion](#conclusion)

---

## **📖 Project Overview**
The purpose of this project is to provide an API interface for climate data analysis. The dataset is stored in an SQLite database and accessed using SQLAlchemy. The Flask application enables querying historical weather data, including precipitation records, temperature observations, and statistical summaries.

This project consists of:
- A **Flask API** (`app.py`) to serve data endpoints.
- A **Jupyter Notebook** (`climate_starter.ipynb`) for exploratory data analysis.
- A **SQLite database** (`hawaii.sqlite`) containing historical weather records.

---

## **📂 Dataset & Database**
The project utilizes a SQLite database (`hawaii.sqlite`) that contains two key tables:

- **Measurement Table:** Stores weather records with fields such as date, station ID, precipitation, and temperature observations.
- **Station Table:** Lists all available weather stations and their respective IDs.

The database is automatically mapped using SQLAlchemy's `automap_base()` to allow easy table access within the Flask application.

---

## **🚀 Flask API Endpoints**
The API provides the following endpoints:

| Route | Description |
|--------|-------------|
| `/` | Lists all available API endpoints. |
| `/api/v1.0/precipitation` | Returns the last 12 months of precipitation data. |
| `/api/v1.0/stations` | Lists all weather stations. |
| `/api/v1.0/tobs` | Returns temperature observations from the most active station for the past year. |
| `/api/v1.0/<start>` | Returns min, avg, and max temperatures from a given start date. |
| `/api/v1.0/<start>/<end>` | Returns min, avg, and max temperatures within a given date range. |

Each endpoint returns data in JSON format for easy integration with other applications.

---

## **⚙️ Setup & Installation**
### **Prerequisites**
Ensure you have the following installed:
- Python 3.x
- Flask (`pip install Flask`)
- SQLAlchemy (`pip install SQLAlchemy`)
- NumPy (`pip install numpy`)

### **Installation Steps**
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo-name.git
   cd climate-analysis
   ```

2. Set up a virtual environment (optional but recommended):
   ```bash
   python -m venv env
   source env/bin/activate  # Mac/Linux
   env\Scripts\activate     # Windows
   ```

3. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

---

## **▶️ Running the Application**
To start the Flask API, navigate to the project directory and run:

```bash
python app.py
```

Once the server starts, open a browser or use a tool like Postman to test the API endpoints.

---

## **📊 Usage & Query Examples**
### **Example 1: Fetch Precipitation Data**
- **URL:** `http://127.0.0.1:5000/api/v1.0/precipitation`
- **Response Format:**
  ```json
  {
      "2016-08-23": 0.0,
      "2016-08-24": 0.08,
      "2016-08-25": 0.08,
      "2016-08-26": 0.0,
      ...
  }
  ```

### **Example 2: Get List of Weather Stations**
- **URL:** `http://127.0.0.1:5000/api/v1.0/stations`
- **Response:**
  ```json
  ["USC00519397", "USC00513117", "USC00514830", "USC00517948", "USC00519523"]
  ```

### **Example 3: Query Temperature Observations**
- **URL:** `http://127.0.0.1:5000/api/v1.0/tobs`
- **Response Format:**
  ```json
  [
      {"2016-08-23": 81.0},
      {"2016-08-24": 79.0},
      {"2016-08-25": 80.0},
      {"2016-08-26": 81.0}
  ]
  ```

### **Example 4: Get Temperature Statistics**
- **Query Min, Avg, Max temperature from a start date**:
  - URL: `http://127.0.0.1:5000/api/v1.0/2017-01-01`
  - Response:
    ```json
    [62.0, 69.7, 78.0]
    ```

- **Query Min, Avg, Max temperature for a date range**:
  - URL: `http://127.0.0.1:5000/api/v1.0/2017-01-01/2017-01-10`
  - Response:
    ```json
    [60.0, 67.8, 77.0]
    ```

---

## **📌 Conclusion**
This project serves as a foundation for climate data analysis and API development. It allows users to retrieve and analyze historical weather data through a well-structured API. Further enhancements could include adding interactive visualizations and expanding the database with additional weather metrics.

