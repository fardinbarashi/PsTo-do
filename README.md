# PsTo-Do

Table of Contents

Welcome  PsTo-Do App! This innovative and user-friendly application is designed to simplify your daily tasks and help you stay organized. If you want to monitor licenses or other objects this solution will help your organization.
This app uses .Net as front and powershell code as backend.
Keep reading to learn more about the app, its features, system requirements, and installation process.

Description
PsTo-do is a application built to enhance productivity and improve time management. It offers a range of features, including:
    Task management: Create, edit, and organize tasks using an intuitive interface.
    Notifications: Stay on top of your schedule with customizable reminders and alerts with teams and mail.
    Collaboration: Share and assign tasks to team members, and track progress in real-time.


Whether you're an individual looking to optimize your workflow or a team striving for seamless collaboration, PsTo-do has you covered.

System Requirements
See design image
![design image](https://github.com/fardinbarashi/PsTo-do/blob/main/Design.jpg))

Installation Process
 - Databas and Tables
 Run SQL-Query in MS-SQL
## Create Table MonitorObjects
Run the code in MS T-SQL 
```
-- Create Table MonitorObjects Start
CREATE TABLE MonitorObjects (
 ID bigint PRIMARY KEY NOT NULL,
 ServerName varchar(MAX) NULL,
 ExpireDate datetime NOT NULL,
 FirstAlertdate int NOT NULL,
 SecondAlertdate int NULL,
 ThirdAlertdate int NULL,
 ObjectName varchar(MAX) NULL,
 Enviroment varchar(MAX) NULL,
 Template varchar(MAX) NULL,
 Description varchar(MAX) NULL,
 Office varchar(MAX) NULL,
 System varchar(MAX) NULL,
 SharePointUrl varchar(MAX) NULL,
 Message varchar(MAX)
);
-- Create Table MonitorObjects End
```
 
