# 👨‍💼 Employee Attendance Classification Agent

A Python-based AI Agent that analyzes employee attendance records and automatically classifies employees into **Safe Zone** and **Danger Zone** based on their check-in time.

The agent processes attendance data from a CSV file, applies business rules, generates a classified dataset, and exports the final results as a downloadable CSV report.

---

# 📌 Project Overview

Organizations often need to monitor employee attendance and identify late arrivals.

This Attendance Classification Agent automatically:

* Reads employee attendance records
* Checks employee arrival times
* Classifies employees based on attendance rules
* Generates a new attendance report
* Exports results as a CSV file

---

# 🚀 Features

✅ Automated attendance analysis

✅ CSV dataset processing

✅ Safe Zone detection

✅ Danger Zone detection

✅ Report generation

✅ CSV export

✅ Google Colab compatible

✅ Beginner-friendly AI Agent project

---

# 🛠️ Technologies Used

| Technology   | Purpose                 |
| ------------ | ----------------------- |
| Python       | Programming Language    |
| Pandas       | Data Processing         |
| Datetime     | Time Comparison         |
| CSV Files    | Data Storage            |
| Google Colab | Development Environment |

---

# 📂 Project Structure

```text
employee-attendance-agent/
│
├── attendance.csv
├── employee_attendance_report.csv
├── app.ipynb
├── requirements.txt
└── README.md
```

---

# ⚙️ Installation

Install required libraries:

```bash
pip install pandas
```

---

# 📊 Dataset Format

Input CSV:

```csv
Employee,CheckIn
Ajay,08:45
Rahul,09:10
Priya,08:30
Amit,09:20
```

---

# ▶️ Run The Project

### Upload Dataset

```python
from google.colab import files

uploaded = files.upload()
```

### Load Dataset

```python
import pandas as pd

file_name = list(uploaded.keys())[0]

df = pd.read_csv(file_name)
```

---

# 💻 Classification Logic

```python
from datetime import datetime

def classify_employee(time_str):

    check_time = datetime.strptime(
        str(time_str),
        "%H:%M"
    )

    cutoff = datetime.strptime(
        "09:00",
        "%H:%M"
    )

    if check_time < cutoff:
        return "SAFE ZONE"

    return "DANGER ZONE"
```

---

# Apply Classification

```python
df["Status"] = df["CheckIn"].apply(
    classify_employee
)
```

---

# Save Final Report

```python
output_file = "employee_attendance_report.csv"

df.to_csv(
    output_file,
    index=False
)
```

---

# Download Report

```python
from google.colab import files

files.download(
    "employee_attendance_report.csv"
)
```

---

# 🔄 Agent Workflow

```text
Employee Dataset
        │
        ▼
Load CSV File
        │
        ▼
Read Check-In Time
        │
        ▼
Compare With 09:00 AM
        │
        ▼
Before 09:00 ?
     /       \
   Yes       No
    │         │
    ▼         ▼
 SAFE      DANGER
  ZONE      ZONE
     \       /
      ▼     ▼
 Generate Report
        │
        ▼
 Export CSV
```

---

# 📊 Example

### Input Dataset

```csv
Employee,CheckIn
Ajay,08:45
Rahul,09:10
Priya,08:30
Amit,09:20
```

### Output Dataset

```csv
Employee,CheckIn,Status
Ajay,08:45,SAFE ZONE
Rahul,09:10,DANGER ZONE
Priya,08:30,SAFE ZONE
Amit,09:20,DANGER ZONE
```

---

# 🎯 Applications

* Employee Attendance Monitoring
* HR Analytics
* Workforce Management
* Attendance Compliance
* Employee Reporting
* Data Classification Tasks

---

# Advantages

* Fast Processing
* Automated Classification
* Easy to Use
* Scalable for Large Datasets
* CSV-Based Workflow
* Lightweight Implementation

---

# Limitations

* Requires Proper Time Format
* Uses Fixed 09:00 AM Rule
* No Database Integration
* No Real-Time Tracking

---

# Future Improvements

* Employee Dashboard
* Streamlit Web Application
* Attendance Visualization
* Email Notifications
* Monthly Reports
* Database Integration
* Real-Time Attendance Monitoring
* Machine Learning Predictions

---

# Learning Outcomes

After completing this project, you will understand:

* Python Programming
* CSV File Handling
* Data Processing with Pandas
* Time-Based Classification
* Rule-Based AI Agents
* Report Generation

---

# Resume Description

Developed an Employee Attendance Classification Agent using Python and Pandas. The system processes attendance datasets, classifies employees into Safe Zone and Danger Zone categories based on check-in times, and automatically generates downloadable CSV reports.

---

# 👨‍💻 Author

## Ajay Sagar

* Python Developer
* AI & Machine Learning Enthusiast
* B.Tech CSE Student

### Connect With Me

🔗 LinkedIn: https://www.linkedin.com/in/engineerajay

🚀 Building AI Projects and Learning New Technologies Every Day.

**Code the Future with Us..!**
