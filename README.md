# Railway Management System (Python + MySQL)

## 📌 Overview
This is a command-line based **Railway Management System** built using **Python** and **MySQL**.
It allows you to manage railway data such as employees, trains, and stations, as well as run predefined queries for data analysis.

---

## 🚀 Features
- **Promote Employee** – Update an employee's designation in the database
- **Pre/Postpone Train** – Modify train departure times
- **Renovate Station** – Update station details
- **Run Queries** – Execute predefined SQL queries for reports
- **Database Integration** – All changes are stored in MySQL

---

## 🛠 Requirements
- Python 3.x
- MySQL Server
- Python Libraries:
  ```bash
  pip install pymysql
  ```

---

## ⚙️ Setup Instructions
1. **Clone or Download the Project**
   ```bash
    
   cd railway-management-system
   ```
2. **Create the MySQL Database**
   ```sql
   CREATE DATABASE railways;
   USE railways;
   ```
3. **Create Tables**
   Example table structures (modify as per your needs):
   ```sql
   CREATE TABLE RAILWAY_EMPLOYEES_A (
       EmployeeID INT PRIMARY KEY AUTO_INCREMENT,
       FirstName VARCHAR(50),
       LastName VARCHAR(50),
       Designation VARCHAR(50)
   );

   CREATE TABLE EMPLOYEES_CONTACT_NUMBERS (
       EmployeeID INT,
       ContactNumber VARCHAR(15),
       FOREIGN KEY (EmployeeID) REFERENCES RAILWAY_EMPLOYEES_A(EmployeeID)
   );

   CREATE TABLE TRAINS (
       TrainID INT PRIMARY KEY AUTO_INCREMENT,
       TrainName VARCHAR(50),
       DepartureTime TIME
   );

   CREATE TABLE STATIONS (
       StationID INT PRIMARY KEY AUTO_INCREMENT,
       StationName VARCHAR(50),
       Location VARCHAR(100)
   );
   ```
4. **Insert Sample Data**
   ```sql
   INSERT INTO RAILWAY_EMPLOYEES_A (FirstName, LastName, Designation)
   VALUES ('John', 'Doe', 'Clerk');

   INSERT INTO TRAINS (TrainName, DepartureTime)
   VALUES ('Express', '09:00:00');

   INSERT INTO STATIONS (StationName, Location)
   VALUES ('Central Station', 'City Center');
   ```

---

## ▶️ Running the Project
Update the database connection details in `railway.py`:
```python
con = pymysql.connect(
    host="localhost",
    user="root",
    password="your_password",
    db="railways"
)
```
Run the script:
```bash
python railway.py
```
Use the menu to perform operations:
```
1. Promote Employee
2. Pre/Postpone Train
3. Renovate Station
4. Queries
```

---

## 🧪 Testing
- **Promote Employee:** Choose option 1 and update a sample employee.
- **Pre/Postpone Train:** Choose option 2 to modify departure time.
- **Renovate Station:** Choose option 3 to update station details.
- **Queries:** Choose option 4 to view results of predefined queries.

---

## 📂 Project Structure
```
railway-management-system/
│
├── railway.py        # Main Python script
├── README.md         # Project documentation
└── requirements.txt  # Python dependencies
```

---



