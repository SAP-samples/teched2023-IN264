# Exercise 2 - Create and Configure the SAP Build Process Automation Project for Equipment and Training Approval Workflow

## Overview
In this exercise, you will configure a SAP Build Process Automation project which can trigger an approval process for the equipments and training requests for the newly onboarded employee in SuccessFactors.

## Pre-requisite
SAP Build Process Automation project “New Hire Onboarding Experience – Template” is given as a template.

## Exercise steps
After completing these steps you will have learnt the following.<br>

1) [How to do a Save as New Project of the sample Employee Onboarding Process Project](#1how-to-do-a-save-as-new-project-of-the-sample-employee-onboarding-process-project)<br>
2) [Add parallel branches to add new Training and Equipment determination rules](#2add-parallel-branches-to-add-new-training-and-equipment-determination-rules)<br>
3) [View the decision to determine Equipments for the newly hired employee](#3view-the-decision-equipments-for-the-newly-hired-employee)<br>
4) [View the decision to determine Trainings for the newly hired employee](#4view-the-decision-trainings-for-the-newly-hired-employee)<br>
5) [Configure approval form inputs to the data from equipment and training decisions](#5-configure-approval-form-inputs-to-the-data-from-equipment-and-training-decisions) <br>
6) [Consume Actions project to publish the approval event to Advanced Event Mesh(AEM)](#6consume-actions-project-to-publish-the-approval-event-to-advanced-event-meshaem) <br>
7) [Release and Deploy](#7release-and-deploy)<br>
8) [Get the Process Instance ID](#8get-the-process-instance-id)<br>

### 1)	How to do a Save as New Project of the sample Employee Onboarding Process Project
a.	Go to [SBPA Lobby](https://in264-72e8h9xc.eu10.build.cloud.sap/lobby) <br>
b.	Locate the Process Automation type of application with name “New Hire Onboarding Experience – Template” <br>
<br>![](/exercises/ex2/images/NewProject01.jpg) <br>
c.	Click on Options (3 dots ...) and Choose “Save As New Project” <br>
  i.	Choose the option for Select Version as “1.0.0” <br>
  ii.	Give a different project name "New Hire Onboarding Experience - IN264-XXX" where XXX will be your last 3 digits of your user id , say for example, it will be "New Hire Onboarding Experience - IN264-000" if your user is 000  <br>
  iii Leave the description as it is <br>  
  iv.	Click on “Save as new” <br>
<br>![](/exercises/ex2/images/NewProject1.0.jpg)<br>
A new project is saved now. <br>
<b>Note</b> : It might take little time for the first time project creation

### 2)	Add parallel branches to add new Training and Equipment determination rules

a.	Click on the project created and in the Overview tab and click on “New Employee Equipment and Training Approval Process” <br>
b.	Note that the template process looks as below and contains artifacts <br>
- An API Trigger called Workflow Trigger to start the process. <br>
- Equipment Determination decsion to determine equipments for the new employee. <br>
- Training Determination decsion to determine trainings for the new employee. <br>
- An approval form to approve Equipment and Training Details. <br>
- 2 email notifications for approval and rejection flows. <br>
<br>![](/exercises/ex2/images/NewProject03.png) <br>
c. The decisions Equipment determination and Training determination are created in  a sequential manner for you in the template project where the execution will happen sequentially in the order . As part of this step in the exercise, we will remove the sequential decisions and add the two decisions in parallel branches to determine the equipments and training so that execution will happen in parallel as there is no dependency between the two decisions and processing will be faster. <br>
      i) Remove the decision Equipment Determination <br>
         <br>![](/exercises/ex2/images/Add_Parallel_Gateway_1.png) <br>
      ii) Remove the decision Training Determination <br>
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
  Job Title <br>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_6.png) <br>
i.	Click on the + next to Training determination branch and add Decision->Training Determination <br>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_7.png) <br>
j.	Map the inputs of the decision from the Process Inputs <br>
    Job Title <br>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_8.png) <br>
Now we have created  parallel branches to determine equipments and trainings for the new hire. <br>


### 3)	View the decision Equipments for the newly hired employee
  a.	Click on Decision “Equipment Determination” <br>
  b.	Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Configure_Equipment_Determination_1.png) <br>
  c.	Click on “Rules” and “Equipment Determination” <br>
  <br>![](/exercises/ex2/images/Configure_Equipment_Determination_2.png) <br>
  d. Click on Full Screen mode <br>
  e.	Check the rows containing rules and note the rules to determine the equipments based on the employee job title are already defined. <br>
  <br>![](/exercises/ex2/images/EquipmentDecisionView.jpg) <br>
  f. Do not change anything and close the rule editor window.

### 4)	View the decision Trainings for the newly hired employee

  a.	Click on Decision “Training Determination” <br>
  b.	Click on Edit Decision <br>
  <br>![](/exercises/ex2/images/Configure_Training_Determination_1.png) <br>
  c.	Click on “Rules” and “Training Determination” <br>
  <br>![](/exercises/ex2/images/Configure_Training_Determination_2.png) <br>
  d. Click on Full Screen mode <br>
  e.	Check the rows and note the rules to determine the trainings based on the employee job title are already defined. <br>
  <br>![](/exercises/ex2/images/TrainingDecisionView.jpg) <br>
  f. Do not change anything and close the rule editor window.

### 5)	 Configure approval form inputs to the data from equipment and training decisions

  a. Click on the Approval Form and check the data under Input tab. Note that most of the fields are already mapped to the Process Inputs.
  <br>![](/exercises/ex2/images/Forms1.jpg) <br>
  b. Map the equipment data to the appproval form. For the Approval Form, click on the Input tab , expand the "Equipment for new hire" list, click on input field in Equipments and select Equipment Determination - Equipments.  Any data that is not mapped automatically needs to  be mapped manually. Save the changes.
  <br>![](/exercises/ex2/images/FormMapping1.jpg) <br>
  c. Now we will map the training data to the approval form. For the Approval Form, click on the Input tab,  expand the "Trainings for new hire" list, click on input field in Trainings and select TrainingDetermination - Trainings.Any data that is not mapped automatically needs to  be mapped manually. Save the changes. <br>
  <br>![](/exercises/ex2/images/FormMapping2.jpg) <br>

### 6)	Consume Actions project to publish the approval event to Advanced Event Mesh(AEM)
Action is a feature in SAP Build Process Automation to connect processes with external systems, be it SAP or non-SAP systems.<br>
[Learn how to create an action project](https://developers.sap.com/tutorials/spa-business-partner-action-create.html)<br> 
This is not needed to be done as part of this exercise, the required Action project is already created for you and you will be consuming it here in the process to publish the approval event to Advanced Event Mesh in this part of the exercise. <br>

  a. Click on the + next to Approve in the Approval form , click Actions and click Browse Library <br>.
  <br>![](/exercises/ex2/images/ActionsNew001.jpg) <br>
  b. Select the "Publish Manager Approval Event". This Action is already published and available in Library.
  <br>![](/exercises/ex2/images/ActionsNew002.jpg) <br>
  c. Note that the Action is added to the process. To add a destination for the Action, under label "Destination variable", select "Create Destination Variable" <br>
  <br>![](/exercises/ex2/images/ActionsNew003.jpg) <br>
  d. Add the following details to the destination pop-up - Identifier : AEM, Description : Advanced Event Mesh Destination, Type : Destination and click Create <br>
  <br>![](/exercises/ex2/images/ActionsNew004.png) <br>
  e. Note that the destination is now updated under the "Destination variable" in "General" Tab for the Action <br>
  <br>![](/exercises/ex2/images/ActionsNew008.jpg) <br>
  f. Now we will map the Action inputs with the Process Inputs. For the Action, click on the Input tab , click on input field in employeeId and selection Process Inputs - Employee ID. <br>
  <br>![](/exercises/ex2/images/ActionsNew009.jpg) <br>
  g. Save the changes. Note that the employeeID is now mapped. <br>
  <br>![](/exercises/ex2/images/Actions010.jpg) <br>
  h. For the Action Project, expand "context" and check the data under Input tab. We need to map the inputs to the Process Inputs as shown below. IMPORTANT NOTE: All the inputs data in Actions needs to be mapped correctly else the end to end execution of the scenario could fail.<br>
  <br>![](/exercises/ex2/images/ActionMapping1.jpg) <br>
  <br>![](/exercises/ex2/images/ActionMapping2.jpg) <br>
  <br>![](/exercises/ex2/images/ActionMapping4.jpg) <br>
  i. Map the equipment data to the Actions project. For the Action, click on the Input tab , expand the "context", expand the Equipment list, click on input field in Equipments and select Equipment Determination - Equipments. Any data that is not mapped automatically needs to  be mapped manually. <br>
  <br>![](/exercises/ex2/images/ActionMapping3.jpg) <br>
  j. Map the training data to the Actions project. For the Action, click on the Input tab,  expand the Trainings list, click on input field in Trainings and select TrainingDetermination - Trainings. Any data that is not mapped automatically needs to  be mapped manually.<br>
  <br>![](/exercises/ex2/images/ActionMapping5.jpg) <br>
  k. Map the "Manager Comment" field to "comments" from the Approval Form outputs. Save the changes <br>
  <br>![](/exercises/ex2/images/ActionMapping6.jpg) <br>

### 7)	Release and Deploy
The destination “AEM” is already created in BTP cockpit and added in settings for you to use it directly<br>
Please refer to the following link to know on 
[How to Create Destination in the SAP BTP Cockpit](https://developers.sap.com/tutorials/cp-cf-create-destination.html)<br>
The created destination is then added to the Settings to use it in the project <br>

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

### 8)	Get the Process Instance ID

  a. From the Lobby screen click Monitor.
  <br>![](/exercises/ex2/images/GetInstance001.jpg) <br><br>
  b. Click Processes and Workflows under Manage section and search with the text IN264-XXX for your Project.
  <br>![](/exercises/ex2/images/NewInstance01.jpg) <br><br>
  c. Note the instance ID and keep it handly for later exersices. <br>
  <br>![](/exercises/ex2/images/NewInstance02.jpg) <br><br>

## Summary

Now that you have configured , released and deployed the SAP Build Process Automation project, Continue to - [Exercise 3 - Create the subscription flow that triggers the SAP Build Process Automation (SBPA) equipment and training approval workflow ](../ex3/README.md)
