For this tutorial you will need the following tools<b/>

* Browser (Prefarably Mozilla)
* Burpsuite
* SQLMap

1. Try and login using the following credentials:<b/>

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
   
2. <b>Try and login using the following credentials:</b>

   | Field     | Value    |
   | --------- |:--------:|
   | USERNAME  | '        |
   | PASSWORD  | admin    |  

RESULTS: The web page will return all the user content
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/step-3.png "STEP 2")
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/result-3.png "RESULT 2")
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/step-4-sqlmap.png "STEP 2")
   ![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/payroll_app/result-4-1.png "RESULT 2")
