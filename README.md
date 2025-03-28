-- Uuendan isiku vanust (Id = 8)
UPDATE Person SET Age = 149 WHERE Id = 8;  

-- Lisan vanusepiirangu (vanus peab olema vahemikus 1-149)
ALTER TABLE Person ADD CONSTRAINT CK_Person_Age CHECK (Age > 0 AND Age < 150);  

-- Üritan lisada isiku vanusega 160 (see peaks ebaõnnestuma, sest vanusepiirang on seatud)
INSERT INTO Person (Id, Name, Email, GenderId, Age)  
VALUES (9, 'Test', 'Test', 2, 160);  

-- Kustutan isiku, kelle Id = 8  
DELETE FROM Person WHERE Id = 8;  

-- Lisan uue veeru "City" tabelisse Person
ALTER TABLE Person ADD City NVARCHAR(25);  

-- Lisan töötajatele uued veerud keskmise ja perekonnanime jaoks
ALTER TABLE Employees ADD MiddleName NVARCHAR(30);
ALTER TABLE Employees ADD LastName NVARCHAR(30);

-- Uuendan töötajate nimed
UPDATE Employees SET Name = 'Tom', MiddleName = 'Nick', LastName = 'Jones' WHERE Id = 1;  
UPDATE Employees SET Name = 'Pam', MiddleName = NULL, LastName = 'Anderson' WHERE Id = 2;  
UPDATE Employees SET Name = 'John', MiddleName = NULL, LastName = NULL WHERE Id = 3;  
UPDATE Employees SET Name = 'Sam', MiddleName = NULL, LastName = 'Smith' WHERE Id = 4;  
UPDATE Employees SET Name = NULL, MiddleName = 'Todd', LastName = 'Someone' WHERE Id = 5;  
UPDATE Employees SET Name = 'Ben', MiddleName = 'Ten', LastName = 'Sven' WHERE Id = 6;  
UPDATE Employees SET Name = 'Sara', MiddleName = NULL, LastName = 'Connor' WHERE Id = 7;  
UPDATE Employees SET Name = 'Valarie', MiddleName = 'Balerine', LastName = NULL WHERE Id = 8;  
UPDATE Employees SET Name = 'James', MiddleName = '007', LastName = 'Bond' WHERE Id = 9;  
UPDATE Employees SET Name = NULL, MiddleName = NULL, LastName = 'Crowe' WHERE Id = 10;  
