# DataBase
DB Intro

CREATE TABLE  Towns(
Id INT PRIMARY KEY IDENTITY,
[Name] VARCHAR(20) NOT NULL
)

CREATE  TABLE Addresses(
Id INT PRIMARY KEY IDENTITY,
AddressText VARCHAR(20) NOT NULL,
TownId INT	FOREIGN KEY REFERENCES Towns(Id)
)

CREATE TABLE Departments(
Id INT PRIMARY KEY IDENTITY,
[Name] VARCHAR(30) NOT NULL
)

CREATE TABLE Employees (
Id INT PRIMARY KEY IDENTITY,
FirstName VARCHAR(30), 
MiddleName VARCHAR(30),
LastName VARCHAR(30), 
Jobtitle VARCHAR(30)NOT NULL,
DepartmentId INT FOREIGN KEY REFERENCES Departments(Id),
HireDate DATETIME NOT NULL,
Salary DECIMAL(15,2)NOT NULL,
AddressId INT FOREIGN KEY REFERENCES Addresses(Id)
)

INSERT INTO Towns ([Name])
VALUES('Sofia'),('Plovdiv')

--•	Departments: Engineering, Sales, Marketing, Software Development, Quality Assurance
INSERT INTO Departments ([Name])
VALUES ('Engineering'),
('Sales'),
('Marketing'),
('Software Development'),
('Quality Assurance')

-- eMPLOYEES -> Name	Job Title	Department	Hire Date Salary
INSERT INTO Employees(FirstName, Jobtitle, DepartmentId, HireDate, Salary)
VALUES('Ivan Ivanov Ivanov', '.NET Developer', 4 , 01/02/2013, 3500.00),
('Petar Petrov Petrov', 'Senior Engineer', 1 , 02/03/2004, 4000.00),
('Maria Petrova Ivanova', 'Intern', 5 , 28/08/2016, 525.25),
('Georgi Teziev Ivanov', 'CEO', 2, 09/12/2007, 3000.00),
('Peter Pan Pan', 'Intern', 3, 28/08/2016, 599.88)

SELECT * FROM Towns
SELECT * FROM Departments
SELECT * FROM  Employees

SELECT * FROM  Towns
ORDER BY Name

SELECT * FROM Departments
ORDER BY Name

SELECT * FROM Employees 
ORDER BY Salary DESC

SELECT Name FROM Towns
ORDER BY Name

SELECT Name FROM Departments
ORDER BY Name

SELECT FirstName, LastName , Jobtitle ,Salary FROM Employees
ORDER BY Salary DESC

UPDATE Employees 
SET Salary += Salary * 0.10;

SELECT Salary FROM Employees

UPDATE Employees
SET Salary -= Salary * 0.03
SELECT Salary FROM Employees

TRUNCATE TABLE Employees
--truncate we delete the content of the table not the thable itself, We shorten tghee content of the table, the delete some of the content

TRUNCATE Table Towns

Relations between the tables into the DB
We can communicate with DB server using  SQL -> Structured query language
