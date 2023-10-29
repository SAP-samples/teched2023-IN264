# Exercise 2 - Create and Configure the SAP Build Process Automation Project for Equipment and Training Approval Workflow

## Overview
In this exercise, you will be setting up a SAP Build Process Automation (SBPA) project to manage the approval workflow for equipment and training of newly hired employees in SuccessFactors. This workflow will be initiated by an Integration Flow from Cloud Integration. Once the manager approves the equipment and training for the new hires, SBPA publishes an event to the SAP Integration Suite, advanced event mesh topic `SBPA/NewHire/{EmployeeId}/Approval` for further integration.

## Prerequisite
SAP Build Process Automation (SBPA) project “**New Hire Onboarding Experience – Template**” is given as a template.

## Exercise steps
Run through the exercise steps in the given order:

1) [Create a new project based on the given "New Hire Onboarding Experience – Template" project and save it](#1create-a-new-project-based-on-the-given-new-hire-onboarding-experience--template-project-and-save-it)<br>
2) [Add parallel branches to add new Equipment and Training determination rules](#2add-parallel-branches-to-add-new-equipment-and-training-determination-rules)<br>
3) [View the Equipment Determination decision for the newly hired employee](#3view-the-equipment-determination-decision-for-the-newly-hired-employee)<br>
4) [View the Training Determination decision for the newly hired employee](#4view-the-training-determination-decision-for-the-newly-hired-employee)<br>
5) [Configure approval form inputs to the data from equipment and training decisions](#5-configure-approval-form-inputs-to-the-data-from-equipment-and-training-decisions) <br>
6) [Consume Actions project to publish the approval event to Advanced Event Mesh(AEM)](#6consume-actions-project-to-publish-the-approval-event-to-advanced-event-meshaem) <br>
7) [Release and Deploy](#7release-and-deploy)<br>
8) [Get the Process Instance ID](#8get-the-process-instance-id)<br>

### 1)	Create a new project based on the given "New Hire Onboarding Experience – Template" project and save it
  a.	Open the [SBPA Lobby](https://in264-72e8h9xc.eu10.build.cloud.sap/lobby) and log in using the user ID and password provided to you by the instructors.<br>
  b.	Locate the **Process Automation** application with the name “**New Hire Onboarding Experience – Template**”.<br>
  c.	Click on the **Options (3 dots ...)** and select “**Save As New Project**” option.
  <br>![](/exercises/ex2/images/NewProject01.jpg) <br><br/>
  d.  Provide the following details:
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   
  - Select Version: **1.0.0**
  - Project Name: **New Hire Onboarding Experience - IN264-XXX**
  - Description: **An event-driven enterprise automation scenario where you react and respond to a new hire business event using SAP Integration Suite and includes human interactions to achieve an end-to-end employee onboarding business process using SAP Build Process Automation.**
<br/><br/>Press the **"Save as new"** button to save the new project.
<br><img src="/exercises/ex2/images/NewProject1.0.jpg" width=75% height=75%><br>

>  Note: It might take little time for the project creation, so kindly wait.

### 2)	Add parallel branches to add new Equipment and Training determination rules

a.	Click on the created project and in the **Overview** tab, click on “**New Employee Equipment and Training Approval Process**” artifact.
<br>![](/exercises/ex2/images/Artifacts_List.jpg) <br>

b.	Kindly note that the template process appears as shown below and includes various artifacts: <br>
- An API Trigger called Workflow Trigger to start the process. <br>
- Equipment Determination decsion to determine equipments for the new employee. <br>
- Training Determination decsion to determine trainings for the new employee. <br>
- An approval form to approve Equipment and Training Details. <br>
- Separate Email notifications for approval and rejection flows. <br>
<br>![](/exercises/ex2/images/NewProject03.png) <br>

c. The '**Equipment Determination**' and '**Training Determination**' decisions are initially set up sequentially in the template project, executed in the specified order. In this step of the exercise, we will reconfigure the setup by incorporating both decisions into parallel branches. This adjustment will enable the determination of equipment and training to occur simultaneously, improving processing speed as there is no interdependency between the two decisions. <br><br>
      i) Remove the '**Equipment Determination**' decision.
         <br>![](/exercises/ex2/images/Add_Parallel_Gateway_1.png) <br>
      ii) Remove the '**Training Determination**' decision.
          <br>![](/exercises/ex2/images/Add_Parallel_Gateway_2.png) <br>
d.	Add a Branch.
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_3.png) <br>

e.	Give the step name as <b>Determine Equipments and Trainings</b>. <br>
  	Give branches as: <br>
    i.	<b>Equipment Determination</b> <br>
    ii.	<b>Training Determination</b>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_4.png) <br>

f.	Click on the **+** button, next to **Equipment Determination** branch and add **Decision -> Equipment Determination**.

> Note: Set the step name as **Equipment Determination**.

![](/exercises/ex2/images/Add_Parallel_Gateway_5.png) <br>

g.	Map the following **Inputs** of the decision from the <b>Process Inputs</b>: <br>
  - <b>Job Title</b>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_6.png) <br>

h.	Click on the **+** button, next to **Training Determination** branch and add **Decision -> Training Determination**. <br>

> Note: Set the step name as **Training Determination**.

![](/exercises/ex2/images/Add_Parallel_Gateway_7.png) <br>

i.	Map the following **Inputs** of the decision from the <b>Process Inputs</b>: <br>
  - <b>Job Title</b>
<br>![](/exercises/ex2/images/Add_Parallel_Gateway_8.png) <br>

> Note: Now, we have created  parallel branches to determine equipments and trainings for the new hire. <br>

### 3)	View the Equipment Determination decision for the newly hired employee
  a.	Click on the “**Equipment Determination**” decision. <br>
  b.	Click on the "**Edit Decision**" button.
  <br>![](/exercises/ex2/images/Configure_Equipment_Determination_1.png) <br>
  c.	Click on the “**Rules**” and then “**Equipment Determination**”.
  <br>![](/exercises/ex2/images/Configure_Equipment_Determination_2.png) <br>
  d.  Click on the **Full Screen mode** which is to the left of close window **(X)** and as highlighted in the above screenshot. <br>
  e.	Examine the rows that contain the rules and make a note of the rules that are used for equipment determination based on the employee's job title.<br>

   > [!IMPORTANT]  
   > We have established rules for new hire job titles that include **Sales**, **Marketing**, **Analyst**, or **Consultant**, along with a **default** rule that does not match any of the mentioned job titles.
   > Accordingly, equipments are determined for the new employee.

  <br>![](/exercises/ex2/images/EquipmentDecisionView.jpg) <br>
  f. Do not change anything and close the rule editor window.

### 4)	View the Training Determination decision for the newly hired employee

  a.	Click on the “**Training Determination**” decision. <br>
  b.	Click on the **Edit Decision** button.
  <br>![](/exercises/ex2/images/Configure_Training_Determination_1.png) <br>
  c.	Click on “**Rules**” and then “**Training Determination**”.
  <br>![](/exercises/ex2/images/Configure_Training_Determination_2.png) <br>
  d. Click on the **Full Screen mode** which is to the left of close window **(X)** and as highlighted in the above screenshot. <br>
  e.	Examine the rows that contain the rules and make a note of the rules that are used for training determination based on the employee's job title.<br>

   > [!IMPORTANT]  
   > We have established rules for new hire job titles that include **Sales**, **Marketing**, **Analyst**, or **Consultant**, along with a **default** rule that does not match any of the mentioned job titles.
   > Accordingly, trainings are determined for the new employee.

  <br>![](/exercises/ex2/images/TrainingDecisionView.jpg) <br>
  f. Do not change anything and close the rule editor window.

### 5)	 Configure approval form inputs to the data from equipment and training decisions

  a. Click on the Approval Form and check the data under **Input** tab. Note that most of the fields are already mapped to the **Process Inputs**.
  <br>![](/exercises/ex2/images/Forms1.jpg) <br>
  b. Map the equipment data to the appproval form. For the Approval Form, click on the **Input** tab , expand the **Equipment for new hire** list, click on input field in **Equipments** and select **Equipment Determination - Equipments**.  Any data that is not mapped automatically needs to  be mapped manually as per the screenshot. Save the changes.
  <br>![](/exercises/ex2/images/FormMapping1.jpg) <br>
  c. Map the training data to the approval form. For the Approval Form, click on the **Input** tab,  expand the **Trainings for new hire** list, click on input field in **Trainings** and select **TrainingDetermination - Trainings**.Any data that is not mapped automatically needs to  be mapped manually as per the screenshot. Save the changes. <br>
  <br>![](/exercises/ex2/images/FormMapping2.jpg) <br>

### 6)	Consume Actions project to publish the approval event to Advanced Event Mesh(AEM)
Action is a feature in SAP Build Process Automation to connect processes with external systems, be it SAP or non-SAP systems.<br>
[Learn how to create an action project](https://developers.sap.com/tutorials/spa-business-partner-action-create.html)<br> 
This is not needed to be done as part of this exercise, the required Action project is already created for you and you will be consuming it here in the process to publish the approval event to Advanced Event Mesh in this part of the exercise. <br>

  a. Click on the **+** button, next to the **Approve** in the Approval form , click "**Actions**" and click "**Browse Library**".
  <br>![](/exercises/ex2/images/ActionsNew001.jpg) <br>
  b. Select the "**Publish Manager Approval Event**". This Action is already published and available in the Library.
  <br>![](/exercises/ex2/images/ActionsNew002.jpg) <br>
  c. Note that the Action is added to the process. To add a destination for the Action, under label **Destination variable**, select **AEM**. This destination variable is already created and is a placeholder for destination mapping during deployment time.
  <br>![](/exercises/ex2/images/ActionsNew008.jpg) <br>
  d. Map the Action inputs with the **Process Inputs**. For the Action, click on the **Input** tab , click on input field in **employeeId** and select **Process Inputs - Employee ID**.
  <br>![](/exercises/ex2/images/ActionsNew009.jpg) <br>
  e. Save the changes. Note that the **employeeID** is now mapped.
  <br>![](/exercises/ex2/images/Actions010.jpg) <br>
  f. For the Action Project, expand **context** and check the data under **Input** tab. We need to map the inputs to the **Process Inputs** as shown below. 
  > NOTE: All the inputs data in Actions needs to be mapped correctly else the end to end execution of the scenario could fail.
  
  ![](/exercises/ex2/images/ActionMapping1.jpg) <br>
  <br>![](/exercises/ex2/images/ActionMapping2.jpg) <br>
  <br>![](/exercises/ex2/images/ActionMapping4.jpg) <br>
  g. Map the equipment data to the Actions project. For the Action, click on the **Input** tab , expand the **context**, expand the **Equipment** list, click on input field in **Equipments** and select **Equipment Determination - Equipments**. Any data that is not mapped automatically needs to  be mapped manually as per the screenshot.
  <br>![](/exercises/ex2/images/ActionMapping3.jpg) <br>
  h. Map the training data to the Actions project. For the Action, click on the **Input** tab,  expand the **Trainings** list, click on input field in **Trainings** and select **TrainingDetermination - Trainings**.
  <br>![](/exercises/ex2/images/ActionMapping5.jpg) <br>
  i. Map the **Manager Comment** field to **comments** from the Approval Form outputs. 
  > **Save the changes**
  
  ![](/exercises/ex2/images/ActionMapping6.jpg) <br>

### 7)	Release and Deploy
The destination “**AEM**” is already created in BTP cockpit and added in settings for you to use it directly<br>
Please refer to the following link to know on 
[How to Create Destination in the SAP BTP Cockpit](https://developers.sap.com/tutorials/cp-cf-create-destination.html)<br>
The created destination is then added to the Settings to use it in the project <br>

  a. Click on the **Release** button in the Process Builder.
  <br>![](/exercises/ex2/images/Release001.jpg) <br>
  b. Click on **Release** button on the Release Project pop-up window.
  <br>![](/exercises/ex2/images/Release002.jpg) <br>
  c. Click on **Deploy**
  <br>![](/exercises/ex2/images/Release003.jpg) <br>
  d. Click on **Next** in the Overview Page of the deployment wizard.
  <br>![](/exercises/ex2/images/ReleaseWizard004.jpg) <br>
  e. Choose the destination as **AEM** in the destination in the Runtime Variables tab and click **Next**.
  <br>![](/exercises/ex2/images/ReleaseAEM.jpg) <br>
  f. Click on **Deploy** in the Triggers page of deployment wizard.
  <br>![](/exercises/ex2/images/Release005.jpg) <br>
  g. Note that the project is deployed.
  <br>![](/exercises/ex2/images/Release006.jpg) <br>

### 8)	Get the Process Instance ID

  a. From the [SBPA Lobby](https://in264-72e8h9xc.eu10.build.cloud.sap/lobby), click Monitoring.
  <br>![](/exercises/ex2/images/Monitor01.png) <br><br>
  b. Click "**Processes and Workflows**" under "**Manage**" section.
  <br>![](/exercises/ex2/images/Monitor02.jpg) <br><br>
  c. Search with the text "**IN264-XXX**" for your Project and select it.<br> 
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   
   <br>![](/exercises/ex2/images/Monitor03.jpg) <br><br>
  d.Note the **Instance ID** and keep it handly for next exercise. Also ensure that the "**ID:**" text should not get copied.
    <br>![](/exercises/ex2/images/Monitor04.jpg) <br><br>

## Summary

At the end of this exercise, you should have configured, released and deployed the SAP Build Process Automation (SBPA) project to manage the approval workflow for equipment and training of newly hired employee.

Continue to - [Exercise 3 - Create the subscription flow that triggers the SAP Build Process Automation (SBPA) equipment and training approval workflow ](/exercises/ex3/README.md)
