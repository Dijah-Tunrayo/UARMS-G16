# UARMS-G16
# University Academic Record Management System (UARMS)

## CS313 – Intermediate C++ Programming Project
**Ashesi University**

## 1. Project Overview

The **University Academic Record Management System (UARMS)** is a C++ application designed to manage university academic records and administrative information through a centralized MySQL database.

The system provides functionality for managing students, faculty, administrators, academic departments, programmes, courses, enrolments, grades, fees, payments, transcripts, and graduation records.

UARMS is developed using Object-Oriented Programming (OOP) principles in C++, with MySQL serving as its database management system. Users interact with the application through a console-based interface.

## 2. Project Objectives

The main objectives of UARMS are to:

- Simplify the management of university academic records.
- Provide centralized storage of student and academic information.
- Implement secure, role-based access for students, faculty, and administrators.
- Support course registration and grade management.
- Automate GPA calculations and transcript generation.
- Manage student fees, payments, and outstanding balances.
- Generate graduating student lists and academic performance reports.
- Demonstrate practical application of C++ OOP concepts and MySQL database integration.

## 3. Key Features

### User and Account Management
- Create and manage student, faculty, and administrator records.
- Authenticate users.
- Implement role-based access and permissions.
- Maintain user information and account records.

### Academic Structure Management
- Manage academic departments.
- Manage programmes of study.
- Create, update, and manage courses.
- Maintain relationships between departments, programmes, and courses.

### Student Academic Records
- Manage student enrolments.
- Record and manage student grades.
- Retrieve academic performance information.
- Maintain historical academic records.

### Financial Management
- Manage student fee records.
- Record student payments.
- Calculate outstanding balances.
- Retrieve student financial information.

### Reports and Transcripts
- Generate student transcripts.
- Calculate Grade Point Averages (GPA).
- Generate graduating student lists.
- Determine degree classifications using the university's approved academic rules.
- Produce academic and financial reports.

## 4. Technologies Used

| Technology | Purpose |
|---|---|
| C++17 | Main programming language |
| MySQL 8.4 LTS | Relational database management |
| MySQL Connector/C++ | Communication between C++ and MySQL |
| CMake | Project configuration and build management |
| Visual Studio 2022 | C++ development environment |
| Visual Studio Code | C++ development environment |
| Git | Version control |
| GitHub | Collaborative development and source-code hosting |
| MySQL Workbench | Database design and administration |

## 5. Object-Oriented Programming Concepts

The project applies the following OOP concepts:

- **Encapsulation:** Protecting data through access modifiers and controlled public methods.
- **Inheritance:** Using a common `Person` base class for `Student`, `Faculty`, and `Admin`.
- **Polymorphism:** Supporting different behaviours through overridden virtual methods.
- **Abstraction:** Separating essential functionality from implementation details.
- **Composition and Association:** Modelling relationships between academic, financial, and user-related entities.

## 6. System Architecture

UARMS consists of three main components:

1. **Console Interface:** Allows users to interact with the system through menus and prompts.
2. **Application Logic:** C++ classes and services handle authentication, academic operations, financial management, and report generation.
3. **Database Layer:** MySQL stores and retrieves system information through MySQL Connector/C++.

```text
             USER
               |
               v
      CONSOLE INTERFACE
               |
               v
       APPLICATION LOGIC
               |
      +--------+---------+
      |        |         |
   Users    Academics  Finance
      |        |         |
      +--------+---------+
               |
               v
       DATABASE CONNECTION
               |
               v
          MYSQL DATABASE
```

## 7. Project Directory Structure

```text
UARMS/
│
├── include/
│   ├── Person.h
│   ├── Student.h
│   ├── Faculty.h
│   ├── Admin.h
│   ├── AuthService.h
│   ├── DatabaseConnection.h
│   ├── Department.h
│   ├── Programme.h
│   ├── Course.h
│   ├── Enrollment.h
│   ├── Grade.h
│   ├── Fee.h
│   ├── Payment.h
│   ├── Transcript.h
│   ├── GraduationService.h
│   └── ReportGenerator.h
│
├── src/
│   ├── main.cpp
│   └── [Corresponding implementation files]
│
├── sql/
│   ├── 00_create_database.sql
│   ├── 01_users.sql
│   ├── 02_academic_structure.sql
│   ├── 03_courses_enrollment_grades.sql
│   ├── 04_fees_payments.sql
│   └── 05_reports.sql
│
├── uml/
│   ├── use_case_diagram.pdf
│   ├── class_diagram.pdf
│   └── database_diagram.pdf
│
├── reports/
│
├── presentation/
│
├── tests/
│
├── CMakeLists.txt
├── CMakePresets.json
├── .gitignore
└── README.md
```

## 8. Development Environment Setup

### Prerequisites

Install the following software:

- Visual Studio 2022 with the Desktop development with C++ workload.
- Visual Studio Code with the C/C++ and CMake Tools extensions.
- CMake 3.25 or newer.
- Git.
- MySQL Server 8.4 LTS.
- MySQL Workbench.
- MySQL Connector/C++ 9.7.0.

The project uses the Microsoft Visual C++ (MSVC) x64 compiler and C++17.

### Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/UARMS.git
cd UARMS
```

Replace `YOUR_USERNAME` with the GitHub repository owner's username.

### Configure MySQL

1. Start your local MySQL Server.
2. Open MySQL Workbench.
3. Create the UARMS database.
4. Create the application database account.
5. Execute the SQL scripts in the following order:

```text
00_create_database.sql
01_users.sql
02_academic_structure.sql
03_courses_enrollment_grades.sql
04_fees_payments.sql
05_reports.sql
```

Each team member should maintain a local development database.

### Configure MySQL Connector/C++

1. Download and extract MySQL Connector/C++.
2. Locate the directory containing `mysql-concpp-config.cmake`.
3. Create a local `CMakeUserPresets.json` file.
4. Configure the `mysql-concpp_DIR` variable to point to the connector's CMake package directory.

The local preset file should not be committed to GitHub because installation paths may differ between team members.

### Build the Application

Open the project directory in Developer PowerShell for Visual Studio 2022.

Configure the project:

```bash
cmake --preset local-msvc
```

Build:

```bash
cmake --build --preset local-release
```

Run the application:

```powershell
.\out\build\local-msvc\Release\uarms.exe
```

The application requires a running MySQL Server and valid database connection credentials.

## 9. Team Responsibilities

The project is divided among three team members.

| Team Member | Responsibilities |
|---|---|
| Student A | People management, inheritance hierarchy, authentication, and access control |
| Student B | Academic structure, courses, enrolments, grades, database design, and database connectivity |
| Student C | Fees, payments, transcripts, GPA calculations, graduation reports, and application integration |

All team members are responsible for testing, reviewing code, integration, documentation, and final presentation preparation.

## 10. Git and Collaboration Workflow

The project uses Git and GitHub for collaborative development.

### Branch Structure

- `main` – Stable and integrated application.
- `feature/*` – New features and modules.
- `fix/*` – Bug fixes and corrections.

### Development Workflow

1. Pull the latest changes from `main`.
2. Create a feature branch.
3. Implement the assigned functionality.
4. Test the implementation.
5. Commit the changes.
6. Push the feature branch to GitHub.
7. Open a Pull Request.
8. Request another team member to review the changes.
9. Merge the approved Pull Request into `main`.

### Example Git Commands

```bash
git checkout main
git pull origin main

git checkout -b feature/student-management

git add .
git commit -m "feat: implement student management"

git push -u origin feature/student-management
```

Pull Requests must be reviewed before merging into `main`.

## 11. Database Design and Integrity

The system uses a relational database to maintain consistent academic and administrative records.

Database design considerations include:

- Primary keys and foreign keys.
- Appropriate relationships between entities.
- Referential integrity.
- Constraints to prevent invalid records.
- Transactions for operations that require multiple related updates.
- Indexing to improve query performance.
- Prepared statements to protect against SQL injection.
- Appropriate restrictions on deleting records with dependent academic history.

The database should be designed to support at least 10,000 student records while maintaining reliable query performance.

## 12. Security Considerations

The system should implement:

- Role-based access control.
- Secure password storage using password hashing.
- Prepared SQL statements.
- Input validation.
- Appropriate database permissions.
- Protection of sensitive student and academic information.
- Restricted access to grade modification and administrative operations.

Database credentials must not be committed to the GitHub repository.

## 13. Testing

Testing should cover the major system functionalities, including:

- User authentication and authorization.
- Student, faculty, and administrator management.
- Department and programme management.
- Course creation and enrolment.
- Grade entry and modification.
- GPA calculations.
- Fee and payment processing.
- Transcript generation.
- Graduating student reports.
- Database connection and error handling.
- Referential integrity and invalid operations.
- Performance with large numbers of student records.

## 14. Project Deliverables

The final submission will include:

1. UML Use Case Diagram.
2. UML Class Diagram.
3. Database Entity Relationship Diagram.
4. C++ source code.
5. MySQL database scripts and backup.
6. Project documentation and report.
7. Presentation slides.
8. Final zipped project submission.

## 15. Academic Information and Assumptions

GPA calculations, graduation eligibility, and degree classification must follow the applicable university-approved academic regulations.

Any grading scales, GPA formulas, or graduation thresholds used by the application should be confirmed against the relevant university requirements before implementation.

## 16. Contributors

This project is developed collaboratively by a three-member team as part of the CS313 Intermediate C++ Programming course at Ashesi University.

| Team Member | Role |
|---|---|
| Student Maame Aba Kwofie | People and Access Management |
| Student Franca Opokua Haligah | Academic Management and Database Infrastructure |
| Student Khadijah Mahrouf Yusif | Finance, Reporting and Integration |

---

**Project:** University Academic Record Management System (UARMS)  
**Course:** CS313 – Intermediate C++ Programming  
**Institution:** Ashesi University  
**Submission Deadline:** 7 December 2026  
**Presentation Period:** 8–11 December 2026
