### **APOD & Iris Dataset Analysis Project**

---

#### **Overview**
This project consists of two main parts:

1. **Astronomy Picture of the Day (APOD) Collection & Analysis**  
   - Retrieve and store APOD data (images and videos) from NASA's API for a specified date range.
   - Process the data, including:  
     - Counting media types (images vs. videos).  
     - Identifying the longest explanation.  
     - Exporting data into a CSV file for further analysis.

2. **Iris Dataset Analysis**  
   - Load, clean, and analyze the Iris dataset to study relationships between flower species attributes.
   - Perform the following tasks:  
     - Correct erroneous entries.  
     - Engineer new features (e.g., `PetalRatio`, `SepalRatio`).  
     - Analyze correlations between features.  
     - Generate visualizations, including scatter plots and pair plots.

---

#### **Requirements**

- **Python Version**: 3.x  
- **Required Libraries**:
  - `requests`
  - `json`
  - `pandas`
  - `seaborn`
  - `matplotlib`
  - `scikit-learn`
  - `numpy`
  - `python-dateutil`

Install the required libraries using:
```bash
pip install requests pandas seaborn matplotlib scikit-learn numpy python-dateutil
```

---

### **Part 1: APOD Data Collection & Processing**

#### **1. APOD Data Retrieval**
##### **Main Functions**:
- `get_apod_data(api_key, query_date)`: Fetches APOD data for a specific date using NASA's API.
- `retrieve_apod_range(api_key, from_date, to_date, output_file)`: Collects APOD data for a specified date range and stores it in a JSON file.

##### **Process Flow**:
1. Data is fetched from NASA's APOD API using the provided API key.
2. The following attributes are stored:
   - **Date**: The date of the APOD.
   - **Title**: The title of the APOD.
   - **Media Type**: Whether it's an image or video.
   - **Image/Video Link**: A link to the media.
   - **Explanation**: A detailed description of the APOD.

##### **Outputs**:
- **JSON File**: `apod_results.json` containing all collected data.

---

#### **2. APOD Data Analysis**
##### **Main Functions**:
- `read_apod_data(file_name)`: Reads APOD data from the JSON file.
- `analyze_apod_media(file_name)`:  
  - Counts the number of images and videos.  
  - Identifies the APOD entry with the longest explanation.
- `write_apod_to_csv(file_name, csv_file)`: Exports APOD data to a CSV file.

##### **Process Flow**:
1. Load the APOD data from the JSON file.
2. Perform analysis:
   - Count the number of images and videos.
   - Find the date and length of the longest explanation.
3. Save the processed data into a CSV file for easy viewing.

##### **Outputs**:
- **CSV File**: `apod_summary.csv` summarizing the collected APOD data.

---

### **Part 2: Iris Dataset Analysis**

#### **1. Data Cleaning & Feature Engineering**
##### **Main Functions**:
- `load_and_analyze_iris(file_path)`:  
  - Loads the Iris dataset and provides basic statistics, such as column names and the number of species.  
- `correct_iris_errors(df)`:  
  - Fixes specific rows in the dataset to correct errors.  
- `add_features_and_save(df, output_file)`:  
  - Adds new features:  
    - **PetalRatio**: Petal length divided by petal width.  
    - **SepalRatio**: Sepal length divided by sepal width.  
  - Saves the enhanced dataset to a CSV file.

##### **Outputs**:
- **Corrected Dataset**: Saved as `iris_corrected.csv`.

---

#### **2. Data Analysis**
##### **Main Functions**:
- `calculate_correlations(df)`:  
  - Calculates correlations between numeric attributes in the dataset.  
  - Identifies the highest positive and negative correlations.  
- `scatter_with_regression(df, output_file)`:  
  - Generates a scatter plot of Sepal Ratio vs. Petal Ratio.  
  - Adds linear regression lines for each species.
- `create_pair_plot(df)`:  
  - Creates a pair plot to visualize relationships between attributes.

##### **Outputs**:
- **Scatter Plot**: Saved as `iris_scatter_with_regression.pdf`.  
- **Pair Plot**: Visualizes relationships across multiple features.

---

### **How to Run the Program**

1. **APOD Retrieval & Processing**:
   - Set your NASA API key in the program.
   - Specify the date range you want to collect data for.
   - Run the script:
     ```bash
     python script_name.py
     ```
   - View the collected data in `apod_results.json` and summary in `apod_summary.csv`.

2. **Iris Dataset Analysis**:
   - Ensure the Iris dataset file `iris.csv` is in the working directory.
   - Run the script:
     ```bash
     python script_name.py
     ```
   - View the enhanced dataset in `iris_corrected.csv`.  
   - Check the scatter and pair plots for visualization.

---
