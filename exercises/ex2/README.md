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
5) Configure Actions inputs to the data from equipment and training decisions <br>
6) Release and Deploy<br>
7) Get the Process Instance ID<br>

## 1)	How to do a Save as New Project of the sample Employee Onboarding Process Project
a.	Go to Lobby link https://in264-72e8h9xc.eu10.build.cloud.sap/lobby <br>
b.	Locate the Process Automation type of application with name “New Hire Onboarding Experience – Template” <br>
<br>![](/exercises/ex2/images/NewProject01.jpg) <br>
c.	Click on More options and Choose “Save As New Project” <br>
  i.	Choose the option for Select Version as “Editable Version” <br>
  ii.	Give a different project name "New Hire Onboarding Experience - IN264-XXX" where XXX will be your last 3 digits of your user id , say for example, it will be "New Hire Onboarding Experience - IN264-000" if your user is 000  <br>
  iii Give description if required <br>  
  iv.	Click on “Save as new” <br>
<br>![](/exercises/ex2/images/NewProject02.jpg.png) <br>
A new project is saved now. <br>

## 2)	Add parallel branches to add new Training and Equipment determination rules

a.	Click on the project created and in the Overview tab, Click on “New Employee Equipment and Training Approval Process” <br>
b.	Note that the template process looks as below <br>
<br>![](/exercises/ex2/images/NewProject03.jpg) <br>

It has an API Trigger called Workflow Trigger to start the process. <br>
It has an API Trigger called Workflow Trigger to start the process. <br>
It has an approval form to approve Equipment and Training Details. <br>
It has 2 email notifications for approval and rejection flows. <br>
It has has an Action to publish the Manager Approval Event to Advanced Event Mesh. <br>

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

## 5)	Configure Actions inputs to the data from equipment and training decisions

  a. After the Approval Form in the process, click on "+" , click Actions and click Browse Library.
  <br>![](/exercises/ex2/images/Actions001.jpg) <br>
  b. Select the "Publish Manager Approval Event". This Action is already published and available in Library.
  <br>![](/exercises/ex2/images/Actions002.jpg) <br>
  c. Note that the Action is added to the process. To add a destination for the Action, under label "Destination variable", select "Create Destination Variable" <br>
  <br>![](/exercises/ex2/images/Actions003.jpg) <br>
  d. Add the following details to the destination pop-up - Identifier : AEM, Description : Advanced Event Mesh Destination, Type : Destination and click Create <br>
  <br>![](/exercises/ex2/images/Actions004.png) <br>
  e. Note that the destination is now updated under the "Destination variable" in "General" Tab for the Action <br>
  <br>![](/exercises/ex2/images/Actions008.jpg) <br>
  f. Now we will map the Action inputs with the Process Inputs. For the Action, click on the Input tab , click on input field in employeeId and selection Process Inputs - Employee ID <br>
  <br>![](/exercises/ex2/images/Actions009.jpg) <br>
  g. Save the changes <br>
  <br>![](/exercises/ex2/images/Actions010.jpg) <br>

## 6)	Release and Deploy
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

## 7)	Get the Process Instance ID

  a. From the Lobby screen click Monitor.
  <br>![](/exercises/ex2/images/GetInstance001.jpg) <br><br>
  b. Click Processes and Workflows under Manage section and select your Project.
  <br>![](/exercises/ex2/images/GetInstance002.jpg) <br><br>
  c. Note the instance ID and keep it handly for later exersices. <br>
  <br>![](/exercises/ex2/images/GetInstance003.jpg) <br><br>

## Summary

Now that you have configured , released and deployed the SAP Build Process Automation project, Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
