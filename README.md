# Assignment 6 
# Data-Driven and Cross-Browser Automated Testing

## Overview
This project demonstrates **automated functional testing** using a **Data-Driven Testing (DDT)** approach and **cross-browser testing in the cloud**.  
The assignment is divided into two parts:

- **Task 1:** Data-Driven Automated Testing using Excel
- **Task 2:** Cross-Browser Testing using BrowserStack

All tests are implemented in **Python** using **Selenium WebDriver** and **pytest**.

---

## Tested Website
- **URL:** https://the-internet.herokuapp.com/login
- **Description:**  
  A web application containing a login form with username and password fields and validation messages for successful and unsuccessful login attempts.

---

## Technologies and Tools Used

### Programming Language
- Python 3

### Test Automation
- Selenium WebDriver
- Pytest

### Data-Driven Testing
- Excel (.xlsx)
- openpyxl

### Cross-Browser Cloud Testing
- BrowserStack (Automate)
- Browsers used:
  - Google Chrome (latest)
  - Microsoft Edge (latest)

---

## Project Structure

```text
.
├── test_login_ddt.py              # Task 1: Local Data-Driven tests
├── test_login_browserstack.py     # Task 2: Cloud cross-browser tests
├── testdata_login.xlsx            # Excel file with test data and expected results
├── testdata_login_results.xlsx    # Generated Excel file with actual results
├── README.md

```

## Excel Test Data
``` testdata_login.xlsx```

The Excel file contains test input data and expected results.
Each row represents a single test case.

Required columns:
* test_id 
* username 
* password 
* expected_text 
* expected_result (PASS / FAIL)

The automated tests read data dynamically from this file.
Adding new rows automatically creates new test executions without changing the code.

```testdata_login_results.xlsx```

This file is generated automatically after test execution and contains:

* Original test data 
* actual_result (PASSED / FAILED)
* actual_text (actual message displayed on the UI)

## Task 1: Data-Driven Automated Testing
### Description

Test data is stored externally in an Excel file. The same test logic is executed multiple times using different data sets. Assertions compare actual results with expected results from Excel. Execution results are logged and written back to a new Excel file. Execution Tests are executed locally using Google Chrome in automated mode.

### Run Task 1
```pytest -v test_login_ddt.py```

## Task 2: Cross-Browser Testing in Cloud
### Description

The same data-driven tests are executed on a cloud-based platform. Tests run in automated mode using Selenium Remote WebDriver. Tests are executed on at least two different browsers

### Cloud Platform 
* BrowserStack Automate

### Browsers Used

* Chrome (latest)

* Edge (latest)

### Evidence Collected

* Screenshots from BrowserStack dashboard 
* Video recordings of test execution 
* Execution logs from BrowserStack sessions 
* Environment Variables (BrowserStack)

Before running cloud tests, set the following environment variables:

```PowerShell (Windows)
$env:BROWSERSTACK_USERNAME="your_browserstack_username"
$env:BROWSERSTACK_ACCESS_KEY="your_browserstack_access_key"
```

### Run Task 2 (Cloud Tests)
```pytest -v test_login_browserstack.py```


BrowserStack will automatically create sessions, record videos, and store logs.

### Dependencies Installation

Install all required dependencies using pip:

```pip install selenium pytest openpyxl webdriver-manager python-dotenv```
