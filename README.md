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

System design image
![design image](https://github.com/fardinbarashi/PsTo-do/blob/main/Design.jpg)

## Installation Process
 - Databas and Tables

## Create Table MonitorObjects and WorkLoadMonitorObjects 

This section presents the structure and purpose of the MonitorObjects and WorkLoadMonitorObjects tables, designed for monitoring system objects and related workloads so that PsTo-Do can work.

# Table MonitorObjects 
Below is a list of columns in the table MonitorObjects, along with their purpose and examples:

    ID (Primary Key)
        Purpose: Unique identifier for each record, can not be null
        Example: 1

    ObjectName
        Purpose: Name of the object being monitored
        Example: Microsoft Root Authority Cert

    ObjectExpireDate
        Purpose: Expiration date of the object, can not be null
        Example: 2022-03-24 00:00:00.000

    ObjectTemplate
        Purpose: Type of template associated with the object
        Example: WebServer

    ObjectDescription
        Purpose: Description of the object
        Example: This is a Certification

    TeamsChannel
        Purpose: Team channel associated with the object, can not be null
        Example: add teamchannels address

    TeamMailbox
        Purpose: Email address associated with the team responsible for the object, can not be null
        Example: Team@something@contoso.com

    TeamMessage
        Purpose: Specific message for the team regarding the object, can not be null
        Example: Servername within system X in Sandbox contains objectsname that is going to expire. Check FAQ for solution.

    SuperUserMailbox
        Purpose: Email address associated with the superusers of the object
        Example: user@something@contoso.com

    SuperUserMessage
        Purpose: Specific message for the superusers regarding the object
        Example: This is information that Object in Servername is going to expire. For more information, contact TeamMailbox.

    FirstAlertDate
        Purpose: Number indicating the amount of days that will trigger the first alert when it is comparing to ObjectExpireDate
        Example: 45

    SecondAlertdate 
        Purpose: Number indicating the amount of days that will trigger the Second alert when it is comparing to ObjectExpireDate
        Example: 30

    ThirdAlertdate 
        Purpose: Number indicating the amount of days that will trigger the Third alert when it is comparing to ObjectExpireDate
        Example: 15

Run the code in MS T-SQL 
```
-- Create Table MonitorObjects Start
CREATE TABLE MonitorObjects (
 ID bigint PRIMARY KEY NOT NULL,
 ObjectName varchar(MAX) NULL,
 ObjectExpireDate datetime NOT NULL,
 ObjectTemplate varchar(MAX) NULL,
 ObjectDescription varchar(MAX) NULL,
 TeamsChannel varchar(MAX) NOT NULL,
 TeamMailbox varchar(MAX) NOT NULL,
 TeamMessage varchar(MAX) NOT NULL,
 SuperUserMailbox varchar(MAX) NULL,
 SuperUserMessage varchar(MAX) NULL,
 FirstAlertDate int(MAX) NOT NULL,
 SecondAlertdate int(MAX) NULL,
 ThirdAlertdate int(MAX) NULL
);
-- Create Table MonitorObjects End

```
## Table WorkLoadMonitorObjects 
Below is a list of columns in the table WorkLoadMonitorObjects, along with their purpose and examples:

    ID (bigint PRIMARY KEY NOT NULL)
        Purpose: Unique identifier for each record'
        Example: 15

    ObjectName (varchar(MAX) NULL)
        Purpose: Name of the object associated with the alert
        Example: Microsoft Root Authority Cert

    NotifiedFirstAlertdate (Bit NULL)
        Purpose: Flag indicating if the first alert has been sent (1: sent, 0: not sent)
        Example: 0

    NotifiedSecondAlertdate (Bit NULL)
        Purpose: Flag indicating if the second alert has been sent (1: sent, 0: not sent)
        Example: 0

    NotifiedThirdAlertdate (Bit NULL)
        Purpose: Flag indicating if the third alert has been sent (1: sent, 0: not sent)
        Example: 0

    WhenFirstAlertdate (datetime NULL)
        Purpose: Timestamp of when the first alert was sent
        Example: 2022-03-24 00:00:00.000

    WhenSecondAlertdate (datetime NULL)
        Purpose: Timestamp of when the second alert was sent
        Example: 2022-03-24 00:00:00.000

    WhenThirdAlertdate (datetime NULL)
        Purpose: Timestamp of when the third alert was sent
        Example: 2022-03-24 00:00:00.000

Run the code in MS T-SQL
```
-- Create Table WorkLoadMonitorObjects Start
CREATE TABLE WorkLoadMonitorObjects (
 ID bigint PRIMARY KEY NOT NULL,
 ObjectName varchar(MAX) NULL,
 NotifiedFirstAlertdate Bit NULL,
 NotifiedSecondAlertdate Bit NULL,
 NotifiedThirdAlertdate Bit NULL,
 WhenFirstAlertdate datetime NULL,
 WhenSecondAlertdate datetime NULL,
 WhenThirdAlertdate datetime NULL
);
-- Create Table WorkLoadMonitorObjects End
```
