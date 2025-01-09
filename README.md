# 30 Days DevOps Challenge - Weather Dashboard

Day 1: Building a weather data collection system using AWS S3 and OpenWeather API


# Weather Dashboard

The **Weather Dashboard** is a Python-based application that fetches real-time weather data for multiple cities and stores it in an AWS S3 bucket. This project utilizes AWS Lambda for automation and includes integration with GitHub for version control.

## Features
- Fetches current weather data for cities like Philadelphia, Seattle, and New York.
- Stores weather data in AWS S3 buckets for long-term storage.
- Allows easy tracking and management of weather information.
- Integrates seamlessly with AWS Lambda for automation.
- Supports GitHub for version control and collaboration.

## Setup and Installation
To set up the project locally, follow these steps:

### Prerequisites
1. **Python**: Ensure Python 3.x is installed on your system.
2. **AWS CLI**: Install and configure the AWS Command Line Interface with your credentials.
3. **Git**: Install Git for version control.
4. **VS Code or any text editor**: For editing files.

### Steps
1. **Clone the repository**:
   ```bash
   git clone https://github.com/<your-username>/Weather-Dashboard.git
   cd Weather-Dashboard

2. **Set up the environment: Create a .env file to store environment variables**:
    ```bash
    echo "AWS_BUCKET_NAME=weather-dashboard-${RANDOM}" >> .env

3. **Install required packages: Install dependencies listed in requirements.txt**:
   ```bash
   pip install -r requirements.txt

4. **Run the application: Execute the weather dashboard script:**
   ```bash
   python src/weather_dashboard.py

 
## Technical Architecture

The application consists of multiple interconnected components to ensure efficient weather data management. Here's an overview:

1. **Weather Data Fetching**:
   - Uses a weather API (e.g., OpenWeatherMap) to fetch current weather data for specified cities.
   - Parses and formats the weather data for easy consumption and storage.

2. **AWS S3 Integration**:
   - Creates an S3 bucket dynamically (name generated using environment variables).
   - Uploads weather data files in JSON format to the S3 bucket.
   - Ensures IAM policies provide necessary permissions for bucket creation, data upload, and public read access.

3. **Automation via AWS Lambda**:
   - A Lambda function (`gd_notifications.py`) is used to handle periodic tasks or events triggered by changes in S3 or external triggers.
   - Code versioned locally and managed in GitHub, with deployment via AWS.

4. **Version Control**:
   - GitHub is used to manage the project repository.
   - Features like `.gitignore` ensure sensitive files (e.g., `.env`) are not tracked in version control.

5. **Error Handling**:
   - Includes detailed error messages for issues like `AccessDenied` or `IllegalLocationConstraintException` to aid debugging.

---

### File Structure
Weather-Dashboard/
│
├── src/
│   ├── weather_dashboard.py  # Main application code
│   └── gd_notifications.py   # Lambda function code
│
├── .env                      # Environment variables (not tracked by Git)
├── requirements.txt          # Python dependencies
├── README.md                 # Project description
└── .gitignore                # Ignored files for Git

### How It Works
1. Fetches weather data from a public API (e.g., OpenWeatherMap).
2. Saves the data in an S3 bucket named weather-dashboard-* using randomized suffixes.
3. Integrates with AWS Lambda for additional automation features.

### Common Errors and Fixes
1. Access Denied (AWS): Ensure your IAM policy has the necessary permissions for creating and managing S3 buckets.
2. IllegalLocationConstraintException: Verify the S3 bucket region matches your AWS CLI configuration

 ---

## What I Learned

Working on this project provided valuable insights into various tools and technologies:
1. **AWS Services**:
   - Gained hands-on experience with AWS S3 for data storage and AWS IAM for managing permissions.
   - Learned to create, manage, and debug AWS Lambda functions.
   - Understood how to work with the AWS CLI for seamless cloud interactions.

2. **Git and GitHub**:
   - Improved my understanding of version control.
   - Learned to handle common Git errors, such as merge conflicts and rejected pushes.
   - Mastered pushing changes, creating branches, and writing meaningful commit messages.

3. **Python Programming**:
   - Deepened my understanding of working with APIs and handling JSON data.
   - Improved error handling and debugging skills in Python.

4. **Automation**:
   - Learned how to use environment variables and automate tasks for efficient workflow.

5. **Debugging**:
   - Resolved issues like S3 bucket creation errors (`IllegalLocationConstraintException`) and permission errors (`AccessDenied`).
   - Understood the importance of aligning S3 bucket regions with AWS configurations.

---  


  
