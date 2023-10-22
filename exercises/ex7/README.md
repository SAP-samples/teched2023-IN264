# Exercise 7 - Verify Scenario Success

In the last part of the exercise, you will verify and check as part of testing whether the scenario has demonstrated successful implementation, meeting the intended requirements and functioning as expected.

## Exercise steps

Run through the exercise steps in the given order.

**7.1** [**Check the Cloud Integration Monitoring**](#71-check-the-cloud-integration-monitoring)
<br/>**7.2** [**Check your Email Inbox for Welcome Email along with the Survey Link**](#72-check-your-email-inbox-for-welcome-email-along-with-the-survey-link)
<br/>**7.3** [**Approve the Equipment and Training requirements of newly hired employee in SAP Build Process Automation Inbox**](#73-approve-the-equipment-and-training-requirements-of-newly-hired-employee-in-sap-build-process-automation-inbox)
<br/>**7.4** [**Check your Email and navigate to the created Purchase Requisition in SAP S/4Hana Cloud system**]()

### 7.1 Check the Cloud Integration Monitoring

In this section, you will check the cloud integration monitoring page to ensure that your integration flows receiving the data event messages, processing it and getting completed successfully.

1. Open the [SAP Integration Suite tenant](https://in264-72e8h9xc.integrationsuite.cfapps.eu10-002.hana.ondemand.com/shell/home) and log in using the user ID and password provided to you by the instructors.
<br><img src="/exercises/ex7/images/IS_Login.png" width=50% height=50%>

2. From the navigation pane on the left side, switch to the **Monitor --> Integrations** area.
   >Hint: By clicking on the burger icon on the top left corner, you can expand the navigation pane.
   
   <br><img src="/exercises/ex7/images/CI_Monitor_Navigate.png" width=90% height=90%>

3. You can see the multiple tiles providing a rich variety of monitoring options. For this exercise, we will monitor messages that have been processed. Click on the tile under <b>Monitor Message Processing</b> to look at **All Artifacts** from past one hour.
<br><img src="/exercises/ex7/images/CI_Monitor_Messages.png" width=90% height=90%>

4. In this view, you can filter your integration messages by using the <b>ID</b> field. Here, to filter through the multiple messages that could have been processed in the last hour, you can use the added employee ID i.e. **IN264-XXX**.
   > [!IMPORTANT]
   > Replace **XXX** with the participant number that is assigned to you.

   Here, you would see the complete messages for the following two integration flows:
   * **SAP SFSF New Hire Onboarding Process Approval Workflow using SAP Build Process Automation - IN264-XXX**
   * **SAP SFSF New Hire Welcome Email with Survey Link - IN264-000**
   
   <br><img src="/exercises/ex7/images/CI_Monitor_Messages_Filter.png" width=90% height=90%>

> [!Note]
> If the status does not reflect as **Completed** for any of the mentioned integration flows, please reach out to one of the session instructors for troubleshooting.

### 7.2 Check your Email Inbox for Welcome Email along with the Survey Link

In this section, you check your email inbox for the welcome email, which includes the survey link as a confirmation of the successful completion of your integration flow.

1. Open the email inbox that is associated with the Email ID you provided while adding a new employee in SAP SuccessFactors.

2. You should have received an email from saprover123@gmail.com. In case you do not see it in the inbox, check your spam or junk email folder.
<br><img src="/exercises/ex7/images/Welcome_Email.png" width=100% height=100%>

3. The email also has a link to survey. Click on the link and observe that the onboarding experience survey has been contextualized to you as a specific individual who has been newly hired in the organization, with team and manager specific questions getting reflected (these items were selected in SuccessFactors while adding the new employee). Fill the entire surveyif you like else leave it fatre  checking the few screens.
<br><img src="/exercises/ex7/images/Survey.png" width=100% height=100%>

### 7.3 Approve the Equipment and Training requirements of newly hired employee in SAP Build Process Automation Inbox

In the previous section, you were in the role of the newly hired employee. In the following exercise, you will be switching roles, and acting as the hiring manager.

In the scenario, the hiring manager will need to approve equipment and training requirements of newly hired employee. To make this whole process a smooth experience for the manager, we make use of SAP Build Process Automation.

In this section, you (as a hiring manager) will check the SAP Build Process Automation inbox for the Equipment and Training Approval form as result of the successful completion of your integration flow.

1. Open the [SAP Build Process Automation - My Inbox](https://in264-72e8h9xc.sap-process-automation.cfapps.eu10.hana.ondemand.com/comsapspaprocessautomation.comsapspainbox/inbox.html) and log in using the user ID and password provided to you by the instructors. You will find a task waiting for your approval.
<br><img src="/exercises/ex7/images/SBPA_Approval_Form_1.png" width=90% height=90%>
<br><img src="/exercises/ex7/images/SBPA_Approval_Form_2.png" width=90% height=90%>

2. Equipments and Training that are suited for this employee and approve them. Do not change any default selection and click on <b>Approve</b> button.
<br><img src="/exercises/ex4/ex43/images/Step02.png" width=90% height=90%>

3. The employee should have received a notification as well with information on the equipment and training selected by the manager on the newly hired candidate's email id configured in the integration flow.
<br><img src="/exercises/ex4/ex43/images/Step03.png" width=60% height=60%>
