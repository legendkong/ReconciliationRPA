# Reconciliation RPA :mechanical_arm::mage_man:
An RPA to improve the reconciliation process of ensuring that the balances in two accounts tally

## Wait... what is an RPA?
 <img src="https://github.com/legendkong/ReconciliationRPA/blob/main/RPA.png" width="800" height="300"><br>
Robotic process automation (RPA) is a software technology that makes it easy to build, deploy, and manage software robots that emulate humans actions interacting with digital systems and software. Just like people, software robots can do things like understand what’s on a screen, complete the right keystrokes, navigate systems, identify and extract data, and perform a wide range of defined actions. But software robots can do it faster and more consistently than people, without the need to get up and stretch or take a coffee break.

## What is the Reconciliation Process?
 1. It is a common process that is carried out in accounting firms/by accountants <br>
 2. Process of ensuring that the balances of two accounts tally <br>
    - This is to ensure that _**Money leaving the account = Money actually spent**_
    - E.g Comparing the full invoice report with each and every monthly invoice report
 
## The Reconciliation Process (Before RPA)
The accountant will have to manually carry out a few tasks <br>
  <li> Open up all the individual monthly invoice reports from each vendor
  <li>  Tally up the total in each of those monthly invoice reports
  <li>  Do the subtraction between the total sum stated for each month in the Full Invoice Report and the total that was tallied up in each monthly invoice report

## Problems with the Reconciliation Process
1. It is an inefficient process
   - Regquires alot of manual data entry and manipulations
   - Process is extremely time consuming
    
2. High chance of error
   - The task is very mundane and the fatigue it creates  result in the accountant making errors whilst carrying out calculations
    
## Improving the process by introducing RPA
<li> By automating the process, many of these above problems can be eliminated
<li> Man hours are freed up and employees can utilise their time more efficiently
<li> Accuracy of reports greatly increased - robots do not make errors when carrying out calculations
 

 
 # Building the Workflow 
 A Step-by-step process for building the RPA workflow
 
 ## Step 1 - Initializing UiPath Studio
   <p align="center">
   <img src="https://github.com/legendkong/ReconciliationRPA/blob/main/GIF/step1_openuipathstudioGIF.gif"><br>
   </p>
   <li> Open Uipath Studio <br>
   <li> Select create new project <br>
   <li> Select Blank Task<br>
   <li> Enter process name "Reconcile" <br>
   <li> Click Create <br>
    
## Step 2 - Selecting the Master File
   <p align="center">
   <img src="https://github.com/legendkong/ReconciliationRPA/blob/main/GIF/step2_selectingmasterfileGIF.gif"><br>
   </p>
   <li> Use "Use Excel File" Activity <br>
   <li> Set Reference as MasterFile <br>

## Step 3 - Creating the Reconcile Column
   <p align="center">
   <img src="https://github.com/legendkong/ReconciliationRPA/blob/main/GIF/step3_reconcile.gif"><br>
   </p>
   <li> Use "Write Cell" Activity <br>
   <li> Write "Reconcile" into F1 cell <br>
   <li> This is to create the Reconcile column in the Master File <br>
    
## Step 4 - Looping through each row in the Master File
   <p align="center">
   <img src="https://github.com/legendkong/ReconciliationRPA/blob/main/GIF/step4_foreach.gif"><br>
   </p>
   <li> Use "Excel for Each Row" Activity <br>
   <li> Select the MasterFile Sheet 1 as the sheet that we want to run the loop <br>
   
    
## Step 5 - Opening the individual monthly reports
   <p align="center">
   <img src="https://github.com/legendkong/ReconciliationRPA/blob/main/GIF/step5_openingindividualreport.gif"><br>
   </p>
   <li> Use a "Use Excel File" Activity inside the "Excel for Each Row" Activity <br>
   <li> Select the Invoices-Alpha-April.xslx file as the template that we will work with <br>    
   <li> Set the Reference as VendorRecord <br>   
    
    
## Step 6 - Summing up the Total in each Vendor Record
   <p align="center">
   <img src="https://github.com/legendkong/ReconciliationRPA/blob/main/GIF/step6_summingup.gif"><br>
   </p>
   <li> Use a "Write Cell" Activity <br>
   <li> We will be writing the summation formula into K1 cell to store the Total sum of the invoices inside each Vendor Record <br>    
    
## Step 7 - Filling up the Reconcile Column
   <p align="center">
   <img src="https://github.com/legendkong/ReconciliationRPA/blob/main/GIF/step7_fillingupreconcilecol.gif"><br>
   </p>
   <li> We will be using another "Write Cell" Activity <br>
   <li> We will write the subtraction formula in the cells in the Reconcile Column of the Master File <br>       
    
## Step 8 - Rewriting the File Path for the Vendor
   <p align="center">
   <img src="https://github.com/legendkong/ReconciliationRPA/blob/main/GIF/step8_rewritefilepath.gif"><br>
   </p>
   <li> Scroll back up to 1.2.1 <br>
   <li> Change the text values to the one above <br> 
    
## Step 9 - Running the workflow
   <p align="center">
   <img src="https://github.com/legendkong/ReconciliationRPA/blob/main/GIF/step9_run.gif"><br>
   </p>
   <li> Click run to automate the process <br>
   <li> The end! Well done! You now know what is an RPA. :technologist:  <br> 
