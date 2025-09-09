# Employee Management System

**Employee Management System** is a desktop application built with C# and Windows Forms. It helps manage employee records including adding new employees, tracking active employees, and managing salary information. The system uses a local SQL Server database for data storage.

---

## Table of Contents

* [Features](#features)
* [Tech Stack](#tech-stack)
* [Prerequisites](#prerequisites)
* [Project Structure](#project-structure)
* [Database Setup](#database-setup)
* [How to Run](#how-to-run)
* [Usage](#usage)
* [Video](#video)
* [Screenshots](#screenshots)
* [Contributing](#contributing)
* [License](#license)
* [Author](#author)

---

## Features

* Add new employee records
* View total and active employee counts
* Manage employee salary details
* Simple validation and user prompts
* User login and registration system

## Tech Stack

* Language: C#
* UI: Windows Forms (WinForms)
* Database: Microsoft SQL Server LocalDB (AttachDB) / `.mdf` file
* IDE: Visual Studio (recommended)

## Prerequisites

* Windows OS
* Visual Studio 2022 (Community or higher) with .NET desktop development workload
* SQL Server Express LocalDB (installed with Visual Studio by default)

## Project Structure
/EmployeeManagementSystem
/EmployeeManagementSystem.sln
/EmployeeManagementSystem
  /bin
  /obj
  /Assets
  /Directory
  /Resources
  /Forms
    - AddEmployee.cs
    - RegisterForm.cs
    - Dashboard.cs
    - Salary.cs
  /Data
    - EmployeeData.cs
    - SalaryData.cs
  Program.cs
  App.config
  MainForm.cs
  Form1.cs
  README.md


## Database Setup

1. If an `.mdf` file is included in the `Data` folder, ensure it is set to be copied to the output directory:
   - Set property: **Copy to Output Directory → "Copy if newer"**

2. Sample connection string used in the project:

```csharp
SqlConnection con = new SqlConnection(@"Data Source=(LocalDB)\\MSSQLLocalDB;AttachDbFilename=|DataDirectory|\\EmployeeDatabase.mdf;Integrated Security=True;Connect Timeout=30");
```

Example table structure (adjust as needed):

```sql
CREATE TABLE EmployeeTbl (
  EmpId INT PRIMARY KEY,
  EmpName VARCHAR(100),
  EmpPosition VARCHAR(50),
  EmpStatus VARCHAR(20), -- Active/Inactive
  EmpAddress VARCHAR(255)
);

CREATE TABLE SalaryTbl (
  SalaryId INT PRIMARY KEY,
  EmpId INT,
  BasicSalary DECIMAL(18,2),
  Bonus DECIMAL(18,2),
  FOREIGN KEY (EmpId) REFERENCES EmployeeTbl(EmpId)
);
```

## How to Run

1. Open `EmployeeManagementSystem.sln` in Visual Studio.
2. Build the solution (Build → Build Solution).
3. Ensure the database `.mdf` file is located in the expected path, or update the connection string in your forms (look for `SqlConnection` instances).
4. Run the project (Start Debugging or Ctrl+F5).

## Usage

* Login using your username and password.
* Add new employees using the "Add Employee" form.
* Monitor total and active employee statistics on the dashboard.
* Manage salary records using the "Salary" section.

## Contributing

1. Fork the repository
2. Create a branch: `git checkout -b feature/YourFeature`
3. Commit your changes: `git commit -m "Add some feature"`
4. Push to the branch: `git push origin feature/YourFeature`
5. Open a Pull Request

Please use clear commit messages and update database schema if applicable.

## License

This project is licensed under the MIT License — see the LICENSE file for details.

## Author

Shubham Bhagwan Mukhekar  
Contact: mshubham2503@gmail.com

## Video

[Watch Demo Video](https://drive.google.com/file/d/1uT0UD4Lki7AvdWouwRLVOZilRlEUSFnb/view?usp=sharing)

## Screenshots

### Login Page  
![Login Page](./Screenshots/LoginPage.png)

### Dashboard  
![Dashboard](./Screenshots/Dashboard.png)

### Add Employee Form  
![Add Employee](./Screenshots/AddEmployee.png)

### Salary Management  
![Salary Form](./Screenshots/Salary.png)
