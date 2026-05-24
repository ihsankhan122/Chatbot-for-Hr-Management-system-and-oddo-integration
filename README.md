# Blimp HR Chatbot

This project is an HR chatbot built with **Streamlit** and **Gemini API**.

It includes two separate chatbot apps:

1. **Employee HR Chatbot** - for employee self-service HR questions.
2. **Admin HR Chatbot** - for HR/admin testing with employee selection.

The chatbot can answer HR-related questions about employee profile, payroll, attendance, bank details, personal details, emergency contact, and employment history.

The project initially started with mock employee data, but it is now connected with real Excel data for:

- Employee profile
- Employee record
- Bank details
- Personal details
- Emergency contact
- Attendance
- Payroll

Task report, performance, and tax calculator are currently still using demo/static responses.

---

## Files

- `app.py` - Employee HR Chatbot Streamlit app
- `app_admin.py` - Admin HR Chatbot Streamlit app
- `prompt.py` - chatbot system prompt and behavior rules
- `utils.py` - helper functions for employee, attendance, and payroll Excel data
- `requirements.txt` - Python dependencies
- `.env.example` - sample environment variable file
- `.env` - local environment variable file
- `README.md` - project setup and run instructions
- `employees details.xlsx` - real employee profile, bank, personal, and emergency data
- `att fy 23 to fy 26 (March-26).xlsx` - real attendance data
- `payroll all old.xlsx` - real payroll data
- `mock_data.py` - old mock employee records, kept for reference only

---

## Current Features

- Employee chatbot for self-service HR information
- Admin chatbot with employee selection
- Gemini API integration
- Local fallback responses if Gemini is unavailable
- Real employee Excel data support
- Real attendance Excel data support
- Real payroll Excel data support
- Latest attendance summary
- Month-wise attendance questions
- Latest payroll summary
- Month-wise payroll questions
- Clear unavailable-data messages for missing attendance/payroll months
- Roman Urdu and English question support
- Enter key and arrow button message submission
- Separate ports for employee and admin apps
- Odoo menu URL integration support
- Network access support using local IP address

---

## Current Data Sources

### Employee Data

```text
employees details.xlsx -> utils.py -> app.py / app_admin.py
Used for:

Employee number
Employee name
Status
Father name
Designation
Date of joining
Contract start
Contract end
Employment type
Bank details
Personal details
Emergency contact

Attendance Data
att fy 23 to fy 26 (March-26).xlsx -> utils.py -> app.py / app_admin.py

Used for:

Attendance status
Attendance month
Fiscal year
Present days
Remote / WFH days
Holiday days
Sick leave days
Casual leave days
Unpaid leave days
Late submitted days
Absent days
Total leave days
Overtime count
Total counted days

Attendance supports latest and month-wise questions.

Example:

March 2026 mein mere remote days kitne hain?
July 2024 attendance dikhao
4/23 attendance dikhao

If a requested attendance month is not available, the chatbot shows a clear message.

Example:

April 2026 attendance data is not available. Latest available month is March 2026.
Payroll Data
payroll all old.xlsx -> utils.py -> app.py / app_admin.py

Used for:

Fiscal year
Payroll month
Employee number
Employee name
Designation
Bank
Payment method
Basic salary
Basic actual
Medical allowance
Allowance
Bonus
Gross salary
Net salary
Deduction
Tax
Taxable income
Yearly income
Total
Total round
Total salary
Payment date
Pay period
Payslip status
Total days
Comments

Payroll supports latest and month-wise questions.

Example:

mera payroll dikhao
mera net salary kya hai?
July 2024 payroll dikhao
selected employee ka net salary kya hai?

If a requested payroll month is not available, the chatbot shows a clear message.

Example:

April 2027 payroll data is not available. Latest available month is ...
Attendance Codes

The attendance Excel file uses these codes:

P  = Present
R  = Remote / WFH
H  = Holiday
S  = Sick Leave
C  = Casual Leave
U  = Unpaid Leave
D  = Data Late Submitted
OT = Overtime

## Step-by-step Setup

### 1) Extract the Project

Unzip or open the project folder.

---

### 2) Open Terminal in Project Folder

Example:

```bash
cd hr_chatbot_mock

streamlit run app.py --server.port 8501 --server.address 0.0.0.0
streamlit run app_admin.py --server.port 8502 --server.address 0.0.0.0
d:\hr_chatbot_mock\venv\Scripts\Activate.ps1                                                                       
(venv) PS D:\hr_chatbot_mock> cd hr_chatbot_mock                          