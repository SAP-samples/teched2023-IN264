# Exercise 2 - Create and Configure the SAP Build Process Automation Project for Equipment and Training Approval Workflow

## Overview
In this exercise, you will configure a SAP Build Process Automation project which can trigger an approval process for the equipments and training requests for the newly onboarded employee in SuccessFactors.

## Pre-requisite
SAP Build Process Automation project “New Hire Onboarding Experience – Enterprise Automation Template” is given as a template.

## Exercise steps
After completing these steps you will have learnt the following.<br>

1) How to do a Save as New Project of the sample Employee Onboarding Process Project<br>
2) Add parallel branches to add new Training and Equipment determination rules<br>
3) Configure the decision to determine Equipments for the newly hired employee<br>
4) Configure the decision to determine Trainings for the newly hired employee<br>
5) Configure Actions inputs to the data from equipment and training decisions <br>
6) Release and Deploy<br>
7) Get the Process Instance ID<br>

### 1)	How to do a Save as New Project of the sample Employee Onboarding Process Project
a.	Go to Lobby link https://in264-72e8h9xc.eu10.build.cloud.sap/lobby <br>
b.	Locate the Process Automation type of application with name “New Hire Onboarding Experience – Template” <br>
<br>![](/exercises/ex2/images/NewProject01.jpg) <br>
c.	Click on More options and Choose “Save As New Project” <br>
  i.	Choose the option for Select Version as “1.0” <br>
  ii.	Give a different project name "New Hire Onboarding Experience - IN264-XXX" where XXX will be your last 3 digits of your user id , say for example, it will be "New Hire Onboarding Experience - IN264-000" if your user is 000  <br>
  iii Give description if required <br>  
  iv.	Click on “Save as new” 
<br>![](/exercises/ex2/images/NewProject1.0.jpg) <br>
A new project is saved now. <br>

### 2)	Add parallel branches to add new Training and Equipment determination rules

a.	Click on the project created and in the Overview tab and click on “New Employee Equipment and Training Approval Process” <br>
b.	Note that the template process looks as below and contains artifacts <br>
- An API Trigger called Workflow Trigger to start the process. <br>
- An approval form to approve Equipment and Training Details. <br>
- 2 email notifications for approval and rejection flows. <br>
- An Action to publish the Manager Approval Event to Advanced Event Mesh. <br>
<br>![](/exercises/ex2/images/NewProject03.jpg) <br>

d.	Add a Branch <br>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_3.png) <br>
e.	Give the step name as “Determine Equipments and Trainings” <br>
f.	Give branches as <br>
    i.	Equipment determination <br>
    ii.	Training determination <br>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_4.png) <br>
g.	Click on the + next to Equipment determination branch and add Decision->Equipment Determination <br>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_5.png) <br>
h.	Map the inputs of the decision from the Process Inputs <br>
  i.	Job Title <br>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_6.png) <br>
i.	Click on the + next to Training determination branch and add Decision->Training Determination <br>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_7.png) <br>
j.	Map the inputs of the decision from the Process Inputs <br>
    i.	Job Title <br>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_8.png) <br>
Now we have created  parallel branches to determine equipments and trainings for the new hire. <br>


### 3)	View the decision Equipments for the newly hired employee
  a.	Click on Decision “Equipment Determination” <br>
  b.	Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Configure_Equipment_Determination_1.png) <br>
  c.	Click on “Rules” and “Equipment Determination” <br>
  <br>![](/exercises/ex2/images/Configure_Equipment_Determination_2.png) <br>
  d.	Check the rows containing rules and note the rules to determine the equipments based on the employee job title are already defined. <br>
  <br>![](/exercises/ex2/images/EquipmentDecisionView.jpg) <br>
  e. Do not change anything and close the rule editor window.

### 4)	View the decision Trainings for the newly hired employee

  a.	Click on Decision “Training Determination” <br>
  b.	Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Configure_Training_Determination_1.png) <br>
  c.	Click on “Rules” and “Training Determination” <br>
  <br>![](/exercises/ex2/images/Configure_Training_Determination_2.png) <br>
  d.	Check the rows and note the rules to determine the trainings based on the employee job title are already defined. <br>
  <br>![](/exercises/ex2/images/TrainingDecisionView.jpg) <br>
  e. Do not change anything and close the rule editor window.

### 5)	Configure Actions inputs to the data from equipment and training decisions

  a. Click on the Action Project and check the data under Input tab. Note that most of the fields are already mapped to the Process Inputs.
  <br>![](/exercises/ex2/images/NewAction01.jpg) <br>
  b. Now we will map the equipment data to the Actions project. For the Action, click on the Input tab , expand the "context", expand the Equipment list, click on input field in Equipments and select Equipment Determination - Equipments. Note that the Equipment list data is automatically getting populated with the data from the decision. <br>
  <br>![](/exercises/ex2/images/NewAction02.jpg) <br>
  c. Now we will map the training data to the Actions project. For the Action, click on the Input tab,  expand the Trainings list, click on input field in Trainings and select TrainingDetermination - Trainings. <br>
  <br>![](/exercises/ex2/images/NewAction03.jpg) <br>
  d. Not that the Training list data is automatically mapped with the data from the decision. Save the changes <br>
  <br>![](/exercises/ex2/images/Actions010.jpg) <br>

### 6)	Release and Deploy
  a. Click on the Release button in the Process Builder.
  <br>![](/exercises/ex2/images/Release001.jpg) <br>
  b. Click on Release button on the Release Projext pop-up window.
  <br>![](/exercises/ex2/images/Release002.jpg) <br>
  c. Click on Deploy <br>
  <br>![](/exercises/ex2/images/Release003.jpg) <br>
  d. Click on "Next" in the Overview Page of the deployment wizard <br>
  <br>![](/exercises/ex2/images/ReleaseWizard004.jpg) <br>
  e. Choose the destination as AEM in the destination in the Runtime Variables tab and click Next <br>
  <br>![](/exercises/ex2/images/ReleaseAEM.jpg) <br>
  f. Click on "Deploy" in the Triggers page of deployment wizard <br>
  <br>![](/exercises/ex2/images/Release005.jpg) <br>
  g. Note that the project is deployed <br>
  <br>![](/exercises/ex2/images/Release006.jpg) <br>

### 7)	Get the Process Instance ID

  a. From the Lobby screen click Monitor.
  <br>![](/exercises/ex2/images/GetInstance001.jpg) <br><br>
  b. Click Processes and Workflows under Manage section and search with the text IN264-XXX for your Project.
  <br>![](/exercises/ex2/images/NewInstance01.jpg) <br><br>
  c. Note the instance ID and keep it handly for later exersices. <br>
  <br>![](/exercises/ex2/images/NewInstance02.jpg) <br><br>

## Summary

Now that you have configured , released and deployed the SAP Build Process Automation project, Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
