# DBMS-project
DBMS Project: FlexFit Gym Database Management System

create database FlexFit;
use FlexFit;
show databases;

CREATE TABLE plans (
    PlanID INT PRIMARY KEY AUTO_INCREMENT,
    PlanName ENUM('Basic', 'Standard', 'Premium', 'Couple', 'Student')
);
INSERT INTO plans (PlanName) VALUES
('Basic'),
('Standard'),
('Premium'),
('Couple'),
('Student');
SELECT * FROM plans;



CREATE TABLE Members (
    MemberID INT PRIMARY KEY,
    FirstName VARCHAR(50),
	LastName VARCHAR(50),
    PhoneNo VARCHAR(20),
    Age INT,
    Gender ENUM('Male', 'Female', 'Other'),
    PlanName ENUM('Basic', 'Standard', 'Premium', 'Couple', 'Student'),
    PlanID INT,
    FOREIGN KEY (PlanID) REFERENCES plans(PlanID) 
);
INSERT INTO Members (MemberID, FirstName, LastName, PhoneNo, Age, Gender, PlanName, PlanID) VALUES
(1, 'John', 'Doe', '1234567890', 30, 'Male', 'Basic', 1),
(2, 'Jane', 'Smith', '9876543210', 25, 'Female', 'Standard', 2),
(3, 'Michael', 'Johnson', '5683723727', 40, 'Male', 'Premium', 3),
(4, 'Emily', 'Davis', '8053083678', 35, 'Female', 'Standard', 2),
(5, 'Christopher', 'Brown', '5049444119', 28, 'Male', 'Basic', 1),
(6, 'Jessica', 'Wilson', '9344541826', 33, 'Female', 'Premium', 3),
(7, 'Matthew', 'Taylor', '7196402739', 45, 'Male', 'Standard', 2),
(8, 'Amanda', 'Martinez', '5864139699', 22, 'Female', 'Basic', 1),
(9, 'David', 'Anderson', '9778816901', 29, 'Male', 'Student', 5),
(10, 'Jennifer', 'Thomas', '7751815220', 31, 'Female', 'Basic', 1),
(11, 'James', 'Jackson', '9000228385', 27, 'Male', 'Standard', 2),
(12, 'Melissa', 'White', '6512792946', 32, 'Female', 'Premium', 3),
(13, 'Ryan', 'Harris', '8768380253', 26, 'Male', 'Basic', 1),
(14, 'Sarah', 'Clark', '2870815315', 24, 'Female', 'Standard', 2),
(15, 'Daniel', 'Lewis', '2251652275', 38, 'Male', 'Couple', 4),
(16, 'Laura', 'Turner', '6115114112', 36, 'Female', 'Basic', 1),
(17, 'Kevin', 'Martin', '8097248122', 34, 'Male', 'Standard', 2),
(18, 'Kimberly', 'Lee', '4665700669', 23, 'Female', 'Premium', 3),
(19, 'Justin', 'Perez', '7720334133', 41, 'Male', 'Basic', 1),
(20, 'Ashley', 'Nguyen', '1234567876', 39, 'Female', 'Premium', 3),
(21, 'Brandon', 'Robinson', '9876543456', 37, 'Male', 'Student', 5),
(22, 'Stephanie', 'Hall', '9872323575', 20, 'Female', 'Basic', 1),
(23, 'Andrew', 'Allen', '8765432345', 21, 'Male', 'Standard', 2),
(24, 'Nicole', 'King', '3456833467', 42, 'Female', 'Basic', 1),
(25, 'Robert', 'Scott', '7654322345', 43, 'Male', 'Premium', 3),
(26, 'Christina', 'Green', '6543234567', 44, 'Female', 'Standard', 2),
(27, 'William', 'Adams', '2345676543', 46, 'Male', 'Basic', 1),
(28, 'Megan', 'Baker', '3264786978', 47, 'Female', 'Premium', 3),
(29, 'Nicholas', 'Nelson', '6534354676', 48, 'Male', 'Basic', 1),
(30, 'Kayla', 'Rivera', '1237893456', 49, 'Female', 'Standard', 2),
(31, 'Zachary', 'Carter', '9876556789', 50, 'Male', 'Basic', 1),
(32, 'Vanessa', 'Torres', '1900956789', 51, 'Female', 'Premium', 3),
(33, 'Cody', 'Evans', '5798833961', 52, 'Male', 'Student', 5),
(34, 'Rebecca', 'Hughes', '3253267065', 53, 'Female', 'Basic', 1),
(35, 'Tyler', 'Long', '7226178674', 54, 'Male', 'Standard', 2),
(36, 'Brittany', 'Foster', '3758325044', 55, 'Female', 'Premium', 3),
(37, 'Austin', 'Diaz', '9647943412', 56, 'Male', 'Basic', 1),
(38, 'Hannah', 'Griffin', '6571131003', 57, 'Female', 'Standard', 2),
(39, 'Dylan', 'Russell', '7037798274 ', 58, 'Male', 'Basic', 1),
(40, 'Samantha', 'Diaz', '5201559505', 59, 'Female', 'Premium', 3),
(41, 'Jordan', 'Ward', '8243730048', 60, 'Male', 'Basic', 1),
(42, 'Maria', 'Bell', '8748020948', 61, 'Female', 'Standard', 2),
(43, 'Joshua', 'Price', '1804013581', 62, 'Male', 'Basic', 1),
(44, 'Lauren', 'Murphy', '3623178417', 63, 'Female', 'Premium', 3),
(45, 'Alex', 'Campbell', '5678323358', 64, 'Male', 'Basic', 1),
(46, 'Olivia', 'Foster', '8385367973', 65, 'Female', 'Standard', 2),
(47, 'Ethan', 'Richardson', '3279566109', 66, 'Male', 'Premium', 3),
(48, 'Grace', 'Diaz', '6158343963', 67, 'Female', 'Basic', 1),
(49, 'Noah', 'Bryant', '3210322449', 68, 'Male', 'Student', 5),
(50, 'Chloe', 'Sanders', '8001463499', 69, 'Female', 'Basic', 1);
SELECT * FROM Members;

CREATE TABLE BasicPlan AS
SELECT *
FROM members
WHERE PlanName = 'Basic';
SELECT * FROM BasicPlan;


CREATE TABLE StandardPlan AS
SELECT *
FROM members
WHERE PlanName = 'Standard';
SELECT * FROM StandardPlan;


CREATE TABLE PremiumPlan AS
SELECT *
FROM members
WHERE PlanName = 'Premium';
SELECT * FROM PremiumPlan;


CREATE TABLE CouplePlan AS
SELECT *
FROM members
WHERE PlanName = 'Couple';

ALTER TABLE CouplePlan
ADD COLUMN PartnerName VARCHAR(100),
ADD COLUMN PartnerAge INT,
ADD COLUMN PartnerGender ENUM('Male', 'Female', 'Other');

TRUNCATE TABLE CouplePlan;

INSERT INTO CouplePlan (MemberID, FirstName, LastName, PhoneNo, Age, Gender, PlanName, PlanID, PartnerName, PartnerAge, PartnerGender) 
VALUES (15, 'Daniel', 'Lewis', '2251652275', 38, 'Male', 'Couple', 5, 'Camille', 36, 'Female');
SELECT * FROM CouplePlan;

CREATE TABLE StudentPlan AS
SELECT *
FROM members
WHERE PlanName = 'Student';
SELECT * FROM StudentPlan;


CREATE TABLE Trainers (
    TrainerID INT PRIMARY KEY,
    Name VARCHAR(100),
    PhoneNo VARCHAR(20),
    PlanName ENUM('Standard', 'Premium', 'Couple', 'Student'),
    PlanID INT,
    Specialization ENUM('Pilates', 'Boot camp', 'Strength training', 'HIIT', 'Yoga', 'Zumba'),
    Age INT,
    Gender VARCHAR(10),
    FOREIGN KEY (PlanID) REFERENCES plans(PlanID) 
);

INSERT INTO Trainers (TrainerID, Name, PhoneNo, PlanName, PlanID, Specialization, Age, Gender)
VALUES
(1, 'Sonia Dailey', '7048571096', 'Standard', 2, 'Zumba', 30, 'Female'),
(2, 'David Miller', '9276356499', 'Premium', 3, 'Yoga', 38, 'Male'),
(3, 'Sophia Garcia', '6758014676', 'Premium', 3, 'Pilates', 32, 'Female'),
(4, 'Daniel Martinez', '2664245272', 'Premium', 3, 'Boot camp', 40, 'Male'),
(5, 'Emily Brown', '3100894721', 'Premium', 3, 'Pilates', 40, 'Female'),
(6, 'Michael Davis', '9381389554', 'Premium', 3, 'Strength training', 45, 'Male'),
(7, 'Jessica Wilson', '9636032615', 'Premium', 3, 'Boot camp', 35, 'Female'),
(8, 'Nichole Lewis', '8122409578', 'Couple', 4, 'HIIT', 35, 'Male'),
(9, 'Alex Johnson', '9231475436', 'Student', 5, 'Yoga', 28, 'Male');
SELECT * FROM Trainers;

CREATE TABLE Classes (
    ClassID INT PRIMARY KEY AUTO_INCREMENT,
    Specialization ENUM('Pilates', 'Boot camp', 'Strength training', 'HIIT', 'Yoga', 'Zumba'),
    TrainerID INT,
    Duration INT,
    FOREIGN KEY (TrainerID) REFERENCES Trainers(TrainerID)
);
INSERT INTO Classes (Specialization, TrainerID, Duration)
VALUES
('Zumba', 1, 45),
('Yoga', 2, 60), 
('Pilates', 3, 90),  
('Boot camp', 4, 90), 
('Pilates', 5, 90),
('Strength training', 6, 60), 
('Boot camp', 7, 90), 
('HIIT', 8, 60), 
('Yoga', 9, 60);  
SELECT * FROM Classes;


CREATE TABLE Payments (
    PaymentID INT PRIMARY KEY AUTO_INCREMENT,
    MemberID INT,
    PaymentDate DATE,
    PaymentStatus ENUM('Paid', 'Unpaid'),
    PlanID INT,
    FOREIGN KEY (MemberID) REFERENCES members(memberID),
    FOREIGN KEY (PlanID) REFERENCES plans(PlanID)
);

INSERT INTO Payments (MemberID, PaymentDate, PaymentStatus, PlanID) 
VALUES
(1, '2024-01-23', 'Paid', 1),  
(2, CURDATE(), 'Unpaid', 2), 
(3, '2024-04-14', 'Paid', 3),  
(4, '2024-03-01', 'Paid', 2),  
(5, CURDATE(), 'Unpaid', 1), 
(6, '2024-02-25', 'Paid', 3),  
(7, CURDATE(), 'Unpaid', 2),  
(8, '2024-02-12', 'Paid', 1), 
(9, '2024-01-18', 'Paid', 5),  
(10, '2024-01-10', 'Paid', 1),  
(11, '2024-02-04', 'Paid', 2), 
(12, CURDATE(), 'Unpaid', 3),  
(13, CURDATE(), 'Unpaid', 1),  
(14, '2024-03-02', 'Paid', 2), 
(15, '2024-03-05', 'Paid', 4),  
(16, '2024-03-17', 'Paid', 1),  
(17, '2024-02-16', 'Paid', 2), 
(18, '2024-02-04', 'Paid', 3),  
(19, '2024-01-05', 'Paid', 1),  
(20, '2024-01-09', 'Paid', 3), 
(21, CURDATE(), 'Unpaid', 5),  
(22, '2024-01-15', 'Paid', 1),  
(23, '2024-01-26', 'Paid', 2), 
(24, CURDATE(), 'Unpaid', 1),  
(25, CURDATE(), 'Unpaid', 3),  
(26, '2024-02-20', 'Paid', 2), 
(27, '2024-04-23', 'Paid', 1),  
(28, '2024-03-17', 'Paid', 3),  
(29, '2024-02-06', 'Paid', 1), 
(30, '2024-01-08', 'Paid', 2),  
(31, '2024-02-16', 'Paid', 1),  
(32, '2024-01-18', 'Paid', 3), 
(33, '2024-02-11', 'Paid', 5),  
(34, CURDATE(), 'Unpaid', 1),  
(35, '2024-03-19', 'Paid', 2), 
(36, '2024-02-04', 'Paid', 3),  
(37, '2024-01-27', 'Paid', 1),  
(38, CURDATE(), 'Unpaid', 2), 
(39, '2024-01-25', 'Paid', 1),  
(40, '2024-01-20', 'Paid', 3),  
(41, '2024-02-22', 'Paid', 1), 
(42, CURDATE(), 'Unpaid', 2),  
(43, '2024-04-28', 'Paid', 1),  
(44, '2024-03-01', 'Paid', 3), 
(45, '2024-02-17', 'Paid', 1),  
(46, '2024-01-18', 'Paid', 2),  
(47, '2024-01-10', 'Paid', 3), 
(48, '2024-01-17', 'Paid', 1),  
(49, CURDATE(), 'Unpaid', 5),  
(50, '2024-02-01', 'Paid', 1); 
SELECT * FROM Payments;

Show Tables;

/*ALL SQL QUERIES*/
SELECT FirstName, LastName, PlanName FROM Members;
SELECT COUNT(*) AS TotalTrainers FROM Trainers;
UPDATE Members SET PhoneNo = '9528294733' WHERE MemberID = 10;
SELECT AVG(Age) AS AverageAge FROM Members;
SELECT * FROM Members WHERE MemberID NOT IN (SELECT MemberID FROM Payments WHERE PaymentStatus = 'Paid');
SELECT MAX(Age) AS OldestAge FROM Members;
SELECT * FROM Trainers WHERE Specialization = 'Yoga';
SELECT SUM(Duration) AS TotalDuration FROM Classes;
SELECT TrainerID, COUNT(*) AS TotalClasses FROM Classes GROUP BY TrainerID;
SELECT COUNT(*) AS TotalMaleMembersUnder40
FROM Members
WHERE Gender = 'Male' AND Age < 40;
SELECT *
FROM Members
WHERE Age BETWEEN 20 AND 30
AND MemberID IN (SELECT MemberID FROM Payments WHERE PaymentStatus = 'Paid');
SELECT AVG(Duration) AS AverageDuration FROM Classes;
SELECT COUNT(*) AS FemaleMembers FROM Members WHERE Gender = 'Female';
SELECT COUNT(*) AS TotalPaymentsInJanuary
FROM Payments
WHERE YEAR(PaymentDate) = 2024 AND MONTH(PaymentDate) = 1;
SELECT FirstName, LastName
FROM Members
WHERE MemberID IN (SELECT MemberID FROM Payments WHERE PaymentStatus = 'Paid')
AND PlanName = 'Premium';
SELECT PlanName, COUNT(*) AS TotalMembers
FROM Members
GROUP BY PlanName;
SELECT FirstName, LastName, PhoneNo
FROM Members
WHERE LastName LIKE 'D%';
SELECT * FROM Classes ORDER BY Duration DESC;
SELECT *
FROM Members
WHERE PlanName = 'Student';
SELECT t.Name AS TrainerName, c.Specialization
FROM Trainers t
JOIN Classes c ON t.TrainerID = c.TrainerID
ORDER BY TrainerName;
SELECT PlanName, COUNT(*) AS TotalPayments
FROM Payments p
JOIN Plans pl ON p.PlanID = pl.PlanID
GROUP BY PlanName;

ALTER TABLE CouplePlan
ADD COLUMN PartnerName VARCHAR(100),
ADD COLUMN PartnerAge INT,
ADD COLUMN PartnerGender ENUM('Male', 'Female', 'Other');

TRUNCATE TABLE CouplePlan;

INSERT INTO CouplePlan (MemberID, FirstName, LastName, PhoneNo, Age, Gender, PlanName, PlanID, PartnerName, PartnerAge, PartnerGender) 
VALUES (15, 'Daniel', 'Lewis', '2251652275', 38, 'Male', 'Couple', 5, 'Camille', 36, 'Female');
SELECT * FROM CouplePlan;
