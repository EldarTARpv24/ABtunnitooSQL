# ABtunnitooSQL
-- Loon andmebaasi
CREATE DATABASE Tarpv24;

-- Loon tabeli Gender
CREATE TABLE Gender  
(  
    Id INT NOT NULL PRIMARY KEY,  
    Gender NVARCHAR(10) NOT NULL  
);  

-- Loon tabeli Person
CREATE TABLE Person  
(  
    Id INT NOT NULL PRIMARY KEY,  
    Name NVARCHAR(25),  
    Email NVARCHAR(30),  
    GenderId INT  
);  

-- Lisan välisvõtme Person tabelisse
ALTER TABLE Person ADD CONSTRAINT tblPerson_GenderId_FK  
FOREIGN KEY (GenderId) REFERENCES Gender(Id);  

-- Loon tabeli Department
CREATE TABLE Department  
(  
    Id INT PRIMARY KEY,  
    DepartmentName NVARCHAR(50),  
    Location NVARCHAR(50),  
    DepartmentHead NVARCHAR(50)  
);  

-- Loon tabeli Employees
CREATE TABLE Employees  
(  
    Id INT PRIMARY KEY,  
    Name NVARCHAR(50),  
    Gender NVARCHAR(10),  
    Salary NVARCHAR(50),  
    DepartmentId INT  
);  
