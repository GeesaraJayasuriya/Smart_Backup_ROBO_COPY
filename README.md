# Smart_Backup_ROBO_COPY

SmartBackup Pro is a lightweight Windows backup automation tool developed using Batch scripting and Robocopy. 
The tool allows users to perform Full, Mirror, and Incremental backups through a simple interactive console interface.
The batch script is compiled into a secured executable using F2KO Bat To Exe Converter to prevent source code exposure and allow enterprise deployment.


## 🚀 Project Objective

To create a simple, dependency-free Windows backup solution that can be deployed across enterprise environments without installing additional software.


## 🛠 Technologies Used

- Windows Batch Scripting (.bat)

- Robocopy (Windows built-in utility)

- F2KO Bat To Exe Converter

- Windows Console Application

## ⚙ Features

- Folder selection

- Multiple backup modes:

  - Full Backup

  - Mirror Backup

  - Incremental Backup

- Automatic log file creation

- Error handling

- Admin privilege support (optional)

- EXE packaging for secure deployment



=====================SAMPLE CODE ========================


@echo off

title SmartBackup Pro

color 0A

 

echo ======================================

echo         SMARTBACKUP PRO

echo ======================================

 

set /p source=Enter Source Folder Path:

set /p destination=Enter Destination Folder Path:

 

echo.

echo Select Backup Mode:

echo 1 - Full Backup

echo 2 - Mirror Backup

echo 3 - Incremental Backup

set /p mode=Enter choice (1-3):

 

if "%mode%"=="1" (

    robocopy "%source%" "%destination%" /E /COPYALL /R:2 /W:2 /LOG:backup.log

)

 

if "%mode%"=="2" (

    robocopy "%source%" "%destination%" /MIR /R:2 /W:2 /LOG:backup.log

)

 

if "%mode%"=="3" (

    robocopy "%source%" "%destination%" /E /XO /R:2 /W:2 /LOG:backup.log

)

 

echo Backup Completed!

pause

==============================END=======================================
