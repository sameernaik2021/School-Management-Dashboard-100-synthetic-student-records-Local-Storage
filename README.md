🏫 School Management System

A basic, browser-based School Management System built with HTML, CSS, and vanilla JavaScript.

The application generates 100 synthetic student records and stores them entirely in the browser's Local Storage. No backend server or database is required.

📌 Features
📊 Dashboard

The dashboard provides an overview of the school data, including:

Total number of students

Average attendance

Students with paid fees

Students with pending fees

Average academic marks

Number of active students

Quick view of student records

👨‍🎓 Students

The Students section provides:

List of all students

Student ID

Student name

Gender

Class

Section

Attendance

Average marks

Fee status

Student details popup

Search functionality

Class filtering

Section filtering

Generate 100 new synthetic students

Clear locally stored data

📚 Academics

The Academics section displays:

Mathematics marks

Science marks

English marks

Social Science marks

Individual student average

Student grade

Average Mathematics score

Average Science score

Average English score

💰 Fees

The Fees section provides:

Total annual fees

Total amount collected

Total pending amount

Individual student fee information

Annual fee

Amount paid

Amount pending

Payment status

📅 Attendance

The Attendance section provides:

Average attendance

Number of students with attendance of 85% or above

Number of students below 85%

Individual student attendance

Attendance status

🛠️ Technologies Used

The project uses only standard web technologies:

HTML5 — Application structure

CSS3 — Styling and responsive layout

JavaScript (ES6+) — Application logic

Browser Local Storage — Local data persistence

No external frameworks or libraries are required.

📁 Project Structure

The simplest version of the application consists of a single file:

school-management/
│
└── index.html


The index.html file contains:

HTML
├── Sidebar navigation
├── Dashboard
├── Students
├── Academics
├── Fees
├── Attendance
└── Student details modal

CSS
├── Layout
├── Sidebar
├── Cards
├── Tables
├── Buttons
├── Forms
├── Modal
└── Responsive design

JavaScript
├── Synthetic data generation
├── Local Storage
├── Navigation
├── Search
├── Filtering
├── Dashboard calculations
├── Academic calculations
├── Fee calculations
├── Attendance calculations
└── Student details

🚀 Getting Started
1. Download or create the project

Create a directory:

school-management


Inside it, create:

index.html


Paste the complete application code into index.html.

2. Open the application

No web server is required for the basic version.

Simply open:

index.html


in a modern browser.

Recommended browsers:

Google Chrome

Microsoft Edge

Mozilla Firefox

Safari

💾 Local Storage

The application does not use a backend database.

Student data is stored in the browser using:

localStorage


The application uses the following Local Storage key:

school_management_students_v2


The student array is converted into JSON before being stored:

localStorage.setItem(
    STORAGE_KEY,
    JSON.stringify(students)
);


When the application starts, it reads the stored data:

const savedData =
    localStorage.getItem(STORAGE_KEY);


The JSON data is then converted back into a JavaScript array.

👨‍🎓 Synthetic Student Data

The application automatically generates 100 synthetic student records.

Example structure:

{
    "id": "STU0001",
    "firstName": "Aarav",
    "lastName": "Sharma",
    "fullName": "Aarav Sharma",
    "gender": "Male",
    "dateOfBirth": "2012-05-18",
    "class": 7,
    "section": "A",
    "rollNumber": 12,
    "attendance": 91.5,
    "subjects": {
        "mathematics": 87,
        "science": 91,
        "english": 84,
        "socialScience": 89
    },
    "averageMarks": 87.8,
    "grade": "A",
    "parent": {
        "name": "Riya Patel",
        "occupation": "Teacher",
        "phone": "9876543210"
    },
    "contact": {
        "email": "aarav.sharma1@example.edu",
        "phone": "9123456789"
    },
    "address": {
        "city": "Pune",
        "state": "Maharashtra",
        "country": "India"
    },
    "fees": {
        "annualFee": 50000,
        "paid": 50000,
        "pending": 0,
        "status": "Paid"
    },
    "admissionYear": 2024,
    "status": "Active"
}


Note: All student information is synthetic/demo information. It is not intended to represent real students.

🔄 Generating New Students

The Generate 100 Students button creates a completely new dataset.

The existing Local Storage data is replaced.

The application asks for confirmation before replacing the data:

Generate a new set of 100 synthetic students?
Existing data will be replaced.


After confirmation, a new set of 100 students is generated.

🗑️ Clearing Data

The Clear Data button removes the application data from Local Storage.

Internally, the application executes:

localStorage.removeItem(
    STORAGE_KEY
);


After clearing the data, the application displays an empty state.

🔎 Student Search

The Students page supports searching by:

Student name

Student ID

Class

Parent/guardian name

Example:

STU0001


or:

Aarav


or:

Class 7


The search is performed locally in the browser.

🎓 Class and Section Filtering

Students can be filtered by:

Class
All Classes
Class 1
Class 2
Class 3
...
Class 12

Section
All Sections
Section A
Section B
Section C


Filters can be combined with the search field.

📊 Dashboard Calculations

The dashboard calculates statistics dynamically from the Local Storage dataset.

Total Students
Number of student records

Average Attendance
Sum of all attendance percentages
÷
Number of students

Average Marks
Sum of student average marks
÷
Number of students

Paid Fees

Number of students whose fee status is:

Paid

Pending Fees

Number of students whose fee status is:

Pending

📚 Academic Calculations

Each student contains marks for:

Mathematics
Science
English
Social Science


The average is calculated using:

(Mathematics + Science + English + Social Science) / 4


Grades are assigned according to the following logic:

Average	Grade
90–100	A+
80–89.9	A
70–79.9	B+
60–69.9	B
50–59.9	C
Below 50	D
💰 Fee Calculations

The synthetic annual fee is:

₹50,000


Each student has:

annualFee
paid
pending
status


For example:

{
    "annualFee": 50000,
    "paid": 35000,
    "pending": 15000,
    "status": "Pending"
}


The Fees page calculates:

Total Fees
Amount Collected
Amount Pending

📅 Attendance

Each synthetic student receives an attendance percentage between approximately:

72% - 99.9%


The application categorizes attendance as:

85% or above → Good
Below 85%   → Needs Attention

🔐 Data and Privacy

This application is designed as a local demo/prototype.

Student data is stored in:

Browser → Local Storage


It is not automatically uploaded to a server by this application.

However, Local Storage should not be treated as a secure database.

Do not use this implementation for real student Personally Identifiable Information (PII), confidential academic records, financial information, or other sensitive data without implementing appropriate security, authentication, authorization, encryption, backend storage, backups, and applicable privacy/compliance controls.

🧪 Inspecting Local Storage

In Google Chrome or Microsoft Edge:

Open the application.

Press:

F12


or:

Ctrl + Shift + I


Open:

Application


Select:

Storage
   └── Local Storage


Select the current website/file origin.

You should see:

school_management_students_v2


The value contains the JSON representation of the student dataset.

⚠️ Important Local Storage Limitations

Local Storage is useful for prototypes and small client-side applications, but it has limitations.

No server synchronization

Data exists only in the browser where it was created.

For example:

Chrome on Computer A
        ↓
    Local Storage
        ↓
      Data


The same application opened on another computer will not automatically have that data.

Clearing browser data can remove records

If the user clears site/browser storage, the Local Storage data may be deleted.

Therefore, Local Storage should not be considered a reliable backup mechanism.

No multi-user support

The current application does not provide:

Teacher accounts

Administrator accounts

Student accounts

Parent accounts

Role-based access control

🔒 Security Considerations

This project is intentionally a frontend-only demonstration.

For a production school management system, consider adding:

Backend API

Database

User authentication

Role-based authorization

Secure password hashing

HTTPS

Input validation

Server-side validation

Audit logs

Database backups

Encryption where appropriate

Session management

Access controls

Data retention policies

Privacy/compliance controls

🌐 Production Architecture

A production version could use an architecture such as:

                    ┌───────────────────┐
                    │   Web Browser     │
                    │                   │
                    │ HTML/CSS/JS       │
                    └─────────┬─────────┘
                              │
                              │ HTTPS
                              ▼
                    ┌───────────────────┐
                    │   Backend API     │
                    │                   │
                    │ Authentication    │
                    │ Authorization     │
                    │ Business Logic    │
                    └─────────┬─────────┘
                              │
                              ▼
                    ┌───────────────────┐
                    │     Database      │
                    │                   │
                    │ Students          │
                    │ Academics         │
                    │ Fees              │
                    │ Attendance         │
                    └───────────────────┘


Possible technologies for a future production implementation include:

Frontend:
HTML / CSS / JavaScript
React / Vue / Angular

Backend:
Node.js
Python
Java
.NET

Database:
PostgreSQL
MySQL
SQL Server
MongoDB

🧩 Possible Future Features

The current application can be extended with:

Student Management

Add student

Edit student

Delete student

Student profile

Student photo

Admission management

Transfer certificate

Student ID card

Academics

Add/edit marks

Examination management

Report cards

Subject management

Teacher assignment

Class timetable

Grade reports

Attendance

Daily attendance

Monthly attendance

Attendance calendar

Attendance reports

Absence notifications

Fees

Record fee payment

Generate receipts

Fee installments

Fee discounts

Payment history

Outstanding fee reports

Administration

Teacher management

Staff management

User accounts

Roles and permissions

School settings

Reporting

Student reports

Attendance reports

Academic reports

Fee reports

Printable report cards

PDF export

CSV/Excel export

📱 Responsive Design

The interface includes responsive CSS for smaller screens.

The application can be used on:

Desktop

Laptop

Tablet

Mobile browser

For a production mobile application, the frontend could additionally be converted into a PWA or implemented using a mobile framework.

🐛 Troubleshooting
Students are not displayed

Open browser Developer Tools and check:

Console


Then refresh the page.

You can also clear the Local Storage entry:

school_management_students_v2


and reload the application.

Data disappeared

Possible causes include:

Browser site data was cleared.

Local Storage was manually deleted.

Browser privacy settings removed storage.

The application was opened under a different origin.

The browser is using private/incognito mode.

Sidebar is not changing pages

Make sure the complete JavaScript section from index.html is present.

The navigation uses:

data-page="dashboard"
data-page="students"
data-page="academics"
data-page="fees"
data-page="attendance"


and JavaScript event listeners to switch between sections.

📄 License

This project can be used as a learning/demo project.

Before using it for a real school or organization, review and adapt the code, security architecture, privacy controls, data handling, and applicable legal/compliance requirements.

👨‍💻 Project Summary

Project: School Management System

Version: 1.0

Type: Frontend prototype

Storage: Browser Local Storage

Data: 100 synthetic students

Backend: None

Database: None

Authentication: None

Framework: None

Languages:

HTML5
CSS3
JavaScript

⭐ Current Application Flow
Open index.html
      │
      ▼
Check Local Storage
      │
      ├── Data exists ──────► Load students
      │
      └── No data ──────────► Generate 100 students
                                      │
                                      ▼
                              Save to Local Storage
                                      │
                                      ▼
                              Display Dashboard
                                      │
                ┌─────────────────────┼─────────────────────┐
                ▼                     ▼                     ▼
            Students              Academics              Fees
                │                     │                     │
                └─────────────────────┼─────────────────────┘
                                      ▼
                                  Attendance

🎯 Purpose

This project is intended to demonstrate how a simple school management interface can be built entirely on the client side using HTML, CSS, JavaScript, synthetic data generation, and browser Local Storage.

It is suitable as a starting point for learning frontend development and for prototyping a larger school management application.
