# SQL Injection Playground with Detection Engine
## 📌 Abstract

This project demonstrates a basic **SQL Injection (SQLi) playground** using:
- A vulnerable **Flask web application**, and
- A **detection engine** written in Python.

The application is intentionally insecure to simulate SQL Injection attacks. It allows learners to explore how SQLi vulnerabilities occur, how they are detected, and how to prevent them. The project includes a detection script that sends test payloads and logs suspicious behavior.


## 🔧 Tools and Technologies Used

- Python 3
- Flask Web Framework
- SQLite Database
- Requests Library
- HTML (Jinja2) Templates
- FPDF (for generating reports)

---

## 🧩 System Overview

### 1. Vulnerable Flask Web App
- Contains a basic login form.
- Uses **raw, unparameterized SQL queries** (vulnerable to SQL Injection).
- Authenticates users with insecure SQL statements.

### 2. SQLi Detector (Python Script)
- Sends a variety of malicious SQL payloads.
- Detects:
  - SQL syntax errors
  - Time delays (for time-based SQLi)
- Logs results to `sqli_log.txt`.
## 🚀 How It Works

1. Launch the Flask app locally:  
   URL: `http://127.0.0.1:5000/`

2. The user interacts with the login form using normal or malicious inputs.

3. The detection engine sends predefined payloads and checks responses:
   - If a payload returns a success or an error message, it's flagged.
   - If a delay is detected (e.g., `sleep(5)`), it logs time-based SQLi.



## 📝 Sample Log Output

[SQLi Detected] Payload: ' OR '1'='1
[TIME-BASED SQLi] Payload: ' OR sleep(5)-- | Delay: 5.02s
