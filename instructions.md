# Instructions
1. This is a part of the project to validate user input to manage employee inventory - each employee record has five data elements,
   - Employee ID
   - Name
   - Department
   - Salary
   - Email
3. In this assignment, we will validate all user input
4. In addition, we will write a new function to generate email address from first and last names  
5. These validations will be coded in validations.py  

<details>
  <summary>
    ✅ Copy Code
  </summary>

- Create a new project in PyCharm and a folder of your choice
- Copy all the code from HW05 into the folder employees
   - main.py
   - functions.py
   - list_functions.py
   - multilist_functions.py
   - validations.py
- Download the data files
   - employees.txt https://github.com/suchialex/CINS3002-HW06/blob/main/employees.txt
   - employees.csv https://github.com/suchialex/CINS3002-HW06/blob/main/employees.csv
</details>


  
## In validations.py

<details>
  <summary>
    ✅ Modify validate_first_name()
  </summary>

  Parameters: This function doesn't accept any parameters  
  Return: It returns a string (the validated name)  
  
  Description:  
  The purpose of this function is to ask the user to provide a first name and check if it is a valid name - which is, 
  - all alphabetical characters
  - no numbers
  - no special characters except space
  - cannot be an empty string     
  If user enters a valid first name, we format the valid first name where the first character of each word is capitalized, and return this formatted valid name to the calling function.  
  If the user enters an invalid name, we print `Invalid: Cannot have numbers or special characters`, and ask user to provide first name again.  
  The whole process is repeated until the user enters a valid first name

  <details>
    <summary>Code Logic</summary>
    - Set a flag called valid to False<br>
    - Start a while loop by checking if valid is False<br>
    - Inside the while loop<br>
      &ensp; - Using an input statement to ask for employee first name, store it in a variable<br>
    &ensp; - Using the appropriate string methods, check if name is all alphabetical ignoring the spaces<br>
    &ensp; - If yes, set valid to True<br>
    &ensp; - If not, print Invalid First Name Entered<br>
    Outside the while loop, (the first name is valid, if you made it out of the while loop)<br>
    - Format first name to where the first letter of each word is capitalized and the rest of them are lowercase<br>
    - Return this formatted first name<br>
  </details>

  <details>
    <summary>💡 Hint: (For string testing)</summary>
  Replace " " to "" and then test using isalpha method<br>
  ⏩ 8-8d, 8-7b  
  Also for valid first name, good idea is to strip off any leading and trailing spaces before you convert first character of each word to uppercase.<br>
  ⏩ 8-2e, 8-2f  
  </details> 
  
</details>


## In main.py

<details>
  <summary>
    ✅ Test validate_first_name
  </summary>

  - Comment out the call to employee_operations inside main
  - call validate_first_name and store in a variable (may have to import the validations module)
  - print this variable and test code with the test cases provided
</details>


## In validations.py
<details>
  <summary>
    ✅ Modify validate_last_name()
  </summary>

  Parameters: This function doesn't accept any parameters  
  Return: It returns a string (the validated last name)  
  
  Description:  
  The purpose of this function is to ask the user to provide a last name and check if it is a valid name - which can be 
  - alphabetical
  - special characters
  - no numbers   
  If user enters a valid last name, we format the valid last name where the first character is capitalized, and return this formatted valid last name to the calling function.  
  If the user enters an invalid last name, we print `Invalid: Cannot have numbers`, and ask user to provide last name again.  
  The whole process is repeated until the user enters a valid last name

<details>
  <summary>Code Logic</summary>
  
  - Set a flag called valid to False
  - Start a while loop by checking if valid is False
  - Inside the while loop
    - Using an input statement to ask for employee last name, store it in a variable
    - Using the appropriate string methods, check if name is alphabetical or special characters, but not numeric
    - (💡You may try using regular expressions, 0r the map function along with other string testing methods or for loop or any() function)
    - If valid last name is entered, set valid to True
    - If not, print `Invalid: Cannot have numbers`
- Outside the while loop, (the last name is valid, if you made it out of the while loop)
- Format name to where the first letter capitalized and the rest of the characters are lowercase
- Return this formatted last name
</details>

  <details>
    <summary>📜 Testing:</summary>

  - If the user enters Wilkes2, it is invalid input because of the number
  - If the user enters mac donald, the returned last name should be Mac Donald
  - If the user enters o'brian the returned last name should be O'Brian
  </details> 

</details>


## In main.py


<details>
  <summary>
    ✅ Test validate_last_name
  </summary>

  - Comment out any code inside main
  - call validate_last_name and store in a variable
  - print this variable and test code with the test cases provided
</details>


## In validations.py

<details>
  <summary>✅ Modify validate_department</summary>

- Department
  - cannot be numeric
  - cannot be special characters
  - cannot have spaces or be all spaces
- Keep asking the user to provide department, until a valid department is provided
- If valid department is provided,
  - and department is longer than four characters, get only the first four characters (💡 Hint: slice the string)
  - and department is less than four characters, get all of them
  - Also, regardless of user input, department will be all uppercase
  - return this string

<details>
  <summary>Code Logic</summary>
  
  - Set a flag called valid to False
  - Start a while loop by checking if valid is False
  - Inside the while loop
    - Using an input statement to ask for employee department, store it in a variable
  - Using the appropriate string methods, check if department is only alphabetical, but not numeric and special characters
  - If yes, set valid to True
  - If not, print Invalid Department Entered
  Outside the while loop, (the department is valid, if you made it out of the while loop)
  - Slice the valid department to get the first four characters and format it to be all lowercase
  - Return this formatted department
</details>
  
<details>
  <summary>💡 Testing</summary>

- If the user enters finance, the output must be FINA
- If the user enters hr, the output must be HR
- If the user enters human resources or f1naid or $acct, it is an invalid input

</details>
</details> 

## In main.py
<details>
  <summary>
    ✅ Test validate_department
  </summary>
  
  - You may comment out other validate functions if they are working correctly
  - call validate_department or validate_dept (whatever is the name of your function) and store in a variable
  - print the above variable and test code with the test cases provided
</details>

## In validations.py
<details>
  <summary>
    ✅ Modify validate_salary
  </summary>

  - Salary must be all numeric (no decimal points or dollar symbols allowed)
  - Salary must be between 35000 and 100000

<details>
  <summary>Code Logic</summary>

  - Set a flag called valid to False
  - Start a while loop by checking if valid is False
  - Inside the while loop
    - Using an input statement to ask for employee salary, store it in a variable
  - Using the appropriate string methods, check if salary is
    - only numeric
    - between 35000 and 100000
    - and is not empty
  - If yes, set valid to True
  - If not, print Invalid Salary Entered  
  Outside the while loop, return the salary
</details>

<details>
  <summary>💡 Testing</summary>

- If the user enters apple, the output must be Invalid Salary Entered
- If the user enters 30000, the output must be Invalid Salary Entered
- If the user enters 36000, the output must be 36000

</details>

</details>

## In main.py
<details>
  <summary>
    ✅ Test validate_salary
  </summary>

  - You may comment out other validate functions if they are working correctly
  - call validate_salary 
  - print the above variable and see if it is working correctly
</details>

## In validations.py
<details>
  <summary>
    ✅ Define a new function generate_email() 
  </summary>

  - This is a value-returning function
  - It accepts two strings, the valid first and last names
  - Email address is the first four characters of the last name and the first character of the first name concatenated with a string @company.com all in lowercase
  - So, if first name is `john` and last name is `mills`, the email address will be `millj@company.com`
  - Email address must be in lowercase
  - Return this email
</details>


## In main.py
<details>
  <summary>
    ✅ Test generate_email() 
  </summary>

  - You may comment out other code in main
  - Call generate_email and store in a variable
  - print this variable and check to see if it is working correctly
  - You may delete all validate functions in main and just call employee operations function (you may have to fix the import statement because multilist_functions is now in employees folder)

</details>

<details>
  <summary>
    ✅ After testing validations
  </summary>

  - If all the validation functions execute correctly, delete all the validate calls from main and uncomment the call to employee_operations
  - Make sure you are importing multilist_functions
  - Execute your code and make sure everything is working fine
</details>


<details>
  <summary>
    ✅ Bonus 2 pts: Modify generate_email() return unique email addresses
  </summary>
  
  - Inside generate_email(),
     - after the genrated email address is calculated, check it already exists for someone else
     - in that case, add a 1 to the end of the username
     - and if that email address exists too, then add a 2 at the end of the username
     - and if that email address exists too, then add a 3 at the end of the username
     - and so on, until a unique email address is generated 
     - For example if millj@company.com already exists, then create millj1@company.com, if that exists too, then create millj2@company.com
</details>
