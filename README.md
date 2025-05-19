# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
mkdir my-folder
![Screenshot 2025-05-19 132458](https://github.com/user-attachments/assets/f7c4be9d-5888-407a-98e6-244047442e7d)
Remove the directory "my-folder"


## COMMAND AND OUTPUT
rmdir my-folder
![Screenshot 2025-05-19 132519](https://github.com/user-attachments/assets/2fe20dee-25ad-4ab9-8733-3bc6ce9317ae)



Create the file Rose.txt


## COMMAND AND OUTPUT
COPY CON Rose.txt
![Screenshot 2025-05-19 132519](https://github.com/user-attachments/assets/4fcfa06a-45a3-4343-87a0-60be61542ac3)


Create the file hello.txt using echo and redirection


## COMMAND AND OUTPUT
echo “hello world” > hello.txt
type hello.txt
![Screenshot 2025-05-19 135518](https://github.com/user-attachments/assets/8873414d-4903-487e-a928-21f34e9dfc52)

Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
copy hello.txt hello1.txt

![Screenshot 2025-05-19 133131](https://github.com/user-attachments/assets/7d89d3be-e891-485f-a496-bdfe0953e132)
Remove the file hello1.txt


## COMMAND AND OUTPUT
del hello1.txt
![Screenshot 2025-05-19 133210](https://github.com/user-attachments/assets/6a2a9e20-c162-493f-aff2-2e7919208b2f)

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
dir hello1.txt
![Screenshot 2025-05-19 133434](https://github.com/user-attachments/assets/c6bf37c0-dc7b-4f29-9a8f-9cb7c7cb494d)

List out all the associated file extensions 

## COMMAND AND OUTPUT
assoc | more
![Screenshot 2025-05-19 133403](https://github.com/user-attachments/assets/91e9a540-14b3-488a-abab-f47437195b9b)


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
fc hello.txt Rose.txt
![Screenshot 2025-05-19 133649](https://github.com/user-attachments/assets/a928bb8e-33e3-4a03-8e9b-fc86a4ba1088)

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

## OUTPUT
Open Notepad with filename 1.bat and type the following batch script
@echo off
set name=John
echo Hello, %name%!
pause

![Screenshot 2025-05-19 133927](https://github.com/user-attachments/assets/5ff9b08c-bf2b-4c9d-b3f7-404e357d1183)



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.



## OUTPUT
@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause

![Screenshot 2025-05-19 134112](https://github.com/user-attachments/assets/f4a6096b-64b2-4f82-bfcd-01acc44931ff)





Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.




## OUTPUT
Open Notepad with filename 3.bat and type the following and execute 3.bat
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause

![Screenshot 2025-05-19 134151](https://github.com/user-attachments/assets/d5f49244-2720-4239-b45f-cf007e96f8ae)




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

## OUTPUT

@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause

![Screenshot 2025-05-19 134236](https://github.com/user-attachments/assets/7084bd0a-8d69-4f24-80b1-ef1e39fdc974)

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.


## OUTPUT
Open Notepad with filename 5.bat and type the following and execute 5.bat

@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause

![Screenshot 2025-05-19 134445](https://github.com/user-attachments/assets/bed5fb24-acc2-4977-9aa6-2463adb055a7)


# RESULT:
The commands/batch files are executed successfully.

