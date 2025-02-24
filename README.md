# Crop Management System

## Overview
The **Crop Management System** is a data-driven web application built using **Streamlit** and **MySQL**, designed to efficiently manage and analyze agricultural records. The system enables users to insert, view, and manage crop records, with support for both manual and bulk data entry. It has been tested on a dataset of **20 million records**, ensuring scalability and performance.

## Features
- **Manual Data Entry**: Users can input individual crop records, including crop type, planting date, harvest date, growth stage, pest control measures, and yield prediction.
- **Bulk Data Insertion**: Generate and insert large-scale crop records using **Faker** for realistic data simulation.
- **Database Connectivity**: Uses **MySQL** for persistent storage, supporting large datasets efficiently.
- **Data Visualization**: Users can view and interact with the top records in the database.
- **Live Updates**: The app refreshes dynamically using **Streamlit's rerun functionality**.

## Technology Stack
- **Frontend**: Streamlit (Python-based UI framework)
- **Backend**: MySQL (Database)
- **Libraries Used**:
  - `pandas`: Data manipulation and display
  - `mysql.connector`: MySQL database connectivity
  - `faker`: Synthetic data generation
  - `datetime` & `random`: Handling dates and randomized values

## Installation
### Prerequisites
Ensure you have the following installed:
- Python (>=3.7)
- MySQL Server
- Required Python libraries (install using `pip`)

### Setup
1. **Clone the repository**:
   ```sh
   git clone https://github.com/your-repo/crop-management.git
   cd crop-management
   ```

2. **Install dependencies**:
   ```sh
   pip install streamlit pandas mysql-connector-python faker
   ```

3. **Configure MySQL Database**:
   - Update `DB_CONFIG` in `app.py` with your MySQL credentials.
   - Create a database named `crop_management` and execute the following SQL to create the necessary table:
     ```sql
     CREATE TABLE crops (
         id INT AUTO_INCREMENT PRIMARY KEY,
         crop_name VARCHAR(50),
         planting_date DATE,
         harvest_date DATE,
         growth_stage VARCHAR(50),
         pest_control_measures TEXT,
         yield_prediction INT
     );
     ```

4. **Run the application**:
   ```sh
   streamlit run app.py
   ```

## Usage
- Open the Streamlit web interface.
- Use the **Insert Data** tab to manually add crop records.
- Use the **Bulk Insert** option to generate and insert large amounts of data.
- View the inserted data under the **View Database** tab.

## Performance Optimization
- Uses **batch inserts** (10,000 records per batch) to improve MySQL write performance.
- Retrieves **1,000,000 records** but displays only the top 10 to optimize memory usage.
- Implements **connection pooling** to efficiently manage database connections.

## Future Enhancements
- **Data Analytics Dashboard**: Visualizing yield predictions and pest control effectiveness.
- **Machine Learning Integration**: Predictive modeling for crop yields based on historical data.
- **API Integration**: REST API endpoints for third-party integrations.

