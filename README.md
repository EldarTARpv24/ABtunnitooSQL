-- Kuvan kõik Person tabeli andmed
SELECT * FROM Person;  

-- Kuvan kõik Gender tabeli andmed
SELECT * FROM Gender;  

-- Kuvan kõik inimesed, kes elavad Gotham-is  
SELECT * FROM Person WHERE City = 'Gotham';  

-- Kuvan kõik inimesed, kes EI ela Gotham-is  
SELECT * FROM Person WHERE City <> 'Gotham';  
SELECT * FROM Person WHERE City != 'Gotham';  

-- Kuvan kõik inimesed, kelle vanus on 100, 50 või 20  
SELECT * FROM Person WHERE Age IN (100, 50, 20);  

-- Kuvan kõik inimesed, kelle nimi algab 'N' tähega  
SELECT * FROM Person WHERE City LIKE 'N%';  

-- Kuvan kõik inimesed, kelle e-posti aadress sisaldab '@' sümbolit  
SELECT * FROM Person WHERE Email LIKE '%@%';  

-- Kuvan kõik inimesed, kelle e-posti aadress EI sisalda '@' sümbolit  
SELECT * FROM Person WHERE Email NOT LIKE '%@%';  

-- Kuvan kõik inimesed, kelle e-posti aadressis on ainult üks täht enne ja pärast '@'  
SELECT * FROM Person WHERE Email LIKE '_@_.com';  

-- Kuvan kõik inimesed, kelle nimi EI alga tähtedega 'W', 'A' või 'S'  
SELECT * FROM Person WHERE Name LIKE '[^WAS]%';  

-- Kuvan kõik inimesed, kes elavad Gotham-is või New York-is ja kelle vanus on vähemalt 40  
SELECT * FROM Person WHERE (City = 'Gotham' OR City = 'New York') AND Age >= 40;  

-- Kuvan ainult esimesed 3 kirjet  
SELECT TOP 3 * FROM Person;  

-- Kuvan ainult vanuse ja nime esimesest kolmest kirjest  
SELECT TOP 3 Age, Name FROM Person;  

-- Kuvan 50% tabeli Person kirjetest  
SELECT TOP 50 PERCENT * FROM Person;  

-- Kuvan kõik andmed tabelist Person, sorteerides vanuse järgi  
SELECT * FROM Person ORDER BY CAST(Age AS INT);  

-- Kuvan vanuse summa  
SELECT SUM(CAST(Age AS INT)) FROM Person;  

-- Kuvan väikseima vanuse  
SELECT MIN(CAST(Age AS INT)) FROM Person;  

-- Kuvan suurima vanuse  
SELECT MAX(CAST(Age AS INT)) FROM Person;  

-- Kuvan iga linna kohta vanuse summa  
SELECT City, SUM(CAST(Age AS INT)) AS TotalAge FROM Person GROUP BY City;  

-- Kuvan unikaalsed töötajate nimed ja osakonna ID-d  
SELECT DISTINCT Name, DepartmentId FROM Employees;  

-- Kuvan kõigi töötajate palkade summa  
SELECT SUM(CAST(Salary AS INT)) FROM Employees;  

-- Kuvan väikseima palga  
SELECT MIN(CAST(Salary AS INT)) FROM Employees;  

-- Kuvan iga töötaja esimese olemasoleva nime (Eesnimi, Keskmine nimi või Perekonnanimi)  
SELECT Id, COALESCE(FirstName, MiddleName, LastName) AS Name FROM Employees;  

-- Kuvan kõik töötajad  
SELECT * FROM Employees;  

-- Kuvan kõik osakonnad  
SELECT * FROM Department;  
