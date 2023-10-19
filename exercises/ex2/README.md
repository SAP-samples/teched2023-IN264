# Configure the SAP Build Process Automation Project

In this exercise, you will configure a SAP Build Process Automation project which can trigger an approval process for the equipments and training requests for the newly onboarded employee in SuccessFactors.

## Pre-requisite
SAP Build Process Automation project “New Hire Onboarding Experience – Enterprise Automation Template” is given as a template

## Steps to configure the SAP Build Process Automation Project
After completing these steps you will have learnt the following.<br>

1)How to do a Save as New Project of the sample Employee Onboarding Process Project<br>
2)Add parallel branches to add new Training and Equipment determination rules<br>
3)Configure the decision to determine Equipments for the newly hired employee<br>
4) Configure the decision to determine Trainings for the newly hired employee<br>
5) Add Action to publish the approval event to Advanced Event Mesh (AEM) <br>
6) Release and Deploy<br>
7) Run the Process<br>

## 1)	How to do a Save as New Project of the sample Employee Onboarding Process Project
a.	Go to Lobby link https://in264-72e8h9xc.eu10.build.cloud.sap/lobby <br>
b.	Locate the Process Automation type of application with name “New Hire Onboarding Experience – Enterprise Automation Template” <br>
<br>![](/exercises/ex2/images/Save_as_New_1.png) <br>
c.	Click on More options and Choose “Save As New Project” <br>
  i.	Choose the option for Select Version as “Editable Version” <br>
  ii.	Give a different project name "New Hire Onboarding Experience - Enterprise Automation IN264-XXX" where XXX will be your last 3 digits of your user id , say for example, it will be "New Hire Onboarding Experience - Enterprise Automation IN264-000" if your user is 000  <br>
  iii Give description if required <br>  
  iv.	Click on “Save as new” <br>
<br>![](/exercises/ex2/images/Save_as_New_2.png) <br>
A new project is saved now. <br>

## 2)	Add parallel branches to add new Training and Equipment determination rules

a.	In the Overview tab, Click on “New Employee Equipment and Training Approval Process Template” <br>
b.	Remove the decision Equipment Determination <br>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_1.png) <br>
c.	Remove the decision Training Determination <br>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_2.png) <br>
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


## 3)	Configure the decision to determine Equipments for the newly hired employee
  a.	Click on Decision “Equipment Determination” <br>
  b.	Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Configure_Equipment_Determination_1.png) <br>
  c.	Click on “Rules” and “Equipment Determination” <br>
  <br>![](/exercises/ex2/images/Configure_Equipment_Determination_2.png) <br>
  d.	Check the row containing 'Leather Executive Laptop Bag' and click on "Copy Row" <br>
  <br>![](/exercises/ex2/images/Configure_Equipment_Determination_3.png) <br>
  e.	Check the same row again and now click on "Paste Row" and "Insert After" <br>
  <br>![](/exercises/ex2/images/Configure_Equipment_Determination_4.png) <br>
  f.	A new row will be created <br>
  g.  Now click on Job Title field and change from "CONTAINS ('Sales')" to "CONTAINS('Marketing')" <br>
  <br>![](/exercises/ex2/images/Configure_Equipment_Determination_5.png) <br>
  h.	Save it <br>
  i. So, now we have configured the decision to determine 'Leather Executive Laptop Bag' also as an equipment for a new employee with Job Title which contains 'Marketing', say for example, a Marketing Specialist or a Marketing Manager and so on.<br>
  
Equipment Determination decision is configured now 

## 4)	Configure the decision to determine Trainings for the newly hired employee

  a.	Click on Decision “Training Determination” <br>
  b.	Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Configure_Training_Determination_1.png) <br>
  c.	Click on “Rules” and “Training Determination” <br>
  <br>![](/exercises/ex2/images/Configure_Training_Determination_2.png) <br>
  d.	Check the row containing Training name as "Compliance and Reporting" and click on "Delete Row" <br>
  <br>![](/exercises/ex2/images/Configure_Training_Determination_3.png) <br>
  e.	This action will remove this row. <br>
  f.	Save it <br>
  g. So we have removed the training "Compliance and Reporting" for a new employee with Job Title containing 'Sales' , say for example, a Sales Manager or a Sales Representative and so on as this training is no more relevant for this role. 
  
Training Determination decision is configured now 

## 5)	Add Action to publish the approval event to Advanced Event Mesh (AEM) 

  a. Select the + icon after Approval Form in the Process to add Actions.
  <br>![](/exercises/ex2/images/Actions001.jpg) <br>
  b. Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Actions002.jpg) <br>
  a. Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Actions003.jpg) <br>
  a. Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Actions004.jpg) <br>
  a. Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Actions008.jpg) <br>
  a. Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Actions009.jpg) <br>
  a. Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Actions010.jpg) <br>

## 6)	Release and Deploy

## 7)	Run the Process


## Summary

Now that you have configured , released and deployed the SAP Build Process Automation project, Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
