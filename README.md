# 🏨 Hotel Booking API Test Automation

![Postman](https://img.shields.io/badge/Postman-API_Testing-orange)
![Newman](https://img.shields.io/badge/Newman-CLI_Testing-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Overview

This project is a complete **API test automation suite** for the Restful Booker application.  
It validates core booking functionalities using **Postman collections** and **Newman CLI execution**.

The project demonstrates real-world **Software Quality Assurance (SQA)** practices including:
- Dynamic test data generation  
- Environment-based execution  
- API chaining  
- Automated assertions  
- CLI-based reporting  

---

## 🧪 Tech Stack

- **Postman** – API testing & scripting  
- **Newman** – CLI runner for automation  
- **JavaScript** – Test scripting  
- **Moment.js** – Date manipulation  

---

## 📁 Project Structure

```bash
├── collection/
│   └── Hotel Booking's API Test.postman_collection.json
│
├── environment/
│   └── DynamicVariable.postman_environment.json
│
├── reports/
│   └── newman-report.html
│
└── README.md
```
---

## 🚀 Features

### 🔁 Dynamic Data Handling
- Uses Postman dynamic variables:
  - `{{$randomFirstName}}`
  - `{{$randomLastName}}`
  - `{{$randomInt}}`
- Ensures unique data per execution

---

### 🔐 Authentication Flow
- Token generated using `/auth`
- Stored in environment variables
- Reused for secured endpoints

---

### 🔗 API Chaining
- Booking ID dynamically captured after creation
- Used in subsequent GET, UPDATE, DELETE requests

---

### 📊 Assertions Coverage
- Status code validation  
- Response time validation  
- Response size validation  
- Data integrity validation  

---

## 📡 API Endpoints Tested

| Method | Endpoint | Description |
|--------|--------|------------|
| GET | `/booking` | Fetch all booking IDs |
| POST | `/booking` | Create new booking |
| GET | `/booking/{id}` | Retrieve booking |
| POST | `/auth` | Generate auth token |
| PUT | `/booking/{id}` | Update booking |
| DELETE | `/booking/{id}` | Delete booking |

---

## 🔄 Test Workflow

GetBookingIDs
↓
CreateBooking
↓
GetBooking
↓
CreateToken
↓
UpdateBooking
↓
DeleteBooking


---

## ▶️ Execution Guide

### 1. Install Newman
```bash
npm install -g newman
```
### 2. Run the Collection
newman run "Hotel Booking's API Test.postman_collection.json" \
-e "DynamicVariable.postman_environment.json"

### 3. Generate HTML Report
newman run collection.json -e environment.json -r html

## 📊 Test Execution Summary

| Metric            | Value  |
| ----------------- | ------ |
| Total Requests    | 11     |
| Total Assertions  | 56     |
| Failed Tests      | 3      |
| Avg Response Time | ~510ms |

## ⚠️ Known Issues
| Scenario                | Expected  | Actual    |
| ----------------------- | --------- | --------- |
| Create Booking          | 201       | 200       |
| Delete Booking          | 200       | 201       |
| Delete Response Message | "Deleted" | undefined |

## 🔍 Analysis

These discrepancies indicate:

API behavior inconsistency
OR incorrect assertion expectations

## 📈 Learning Outcomes
Practical API automation workflow
Postman scripting with dynamic variables
Environment-based testing
CLI automation using Newman
Debugging failed API tests

## 🔧 Future Enhancements
CI/CD integration using GitHub Actions
JSON schema validation
Negative & edge case testing
Retry logic for unstable APIs
Advanced reporting dashboards

## 👨‍💻 Author

Zahid
CSE Graduate | Aspiring SQA Engineer | Cybersecurity Enthusiast

## ⭐ Conclusion

This project reflects a real-world API testing pipeline used in professional SQA environments.
It showcases both technical skills and testing strategy design, making it suitable for portfolio and job applications.
