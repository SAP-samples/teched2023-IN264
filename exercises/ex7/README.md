# Exercise 7 - Verify Scenario Success

In the last part of the exercise, you will verify and check as part of testing whether the scenario has demonstrated successful implementation, meeting the intended requirements and functioning as expected.

## Exercise steps

Run through the exercise steps in the given order.

[Check the Cloud Integration Monitoring](/exercises/ex4/ex41)
<br>[Check your Email Inbox and Click through Qualtrics Survey](/exercises/ex4/ex42)
<br>[Approve the new hire in SAP Build Process Automation Inbox](/exercises/ex4/ex43)
* Check Integration Flow(s) Success in Cloud Integration Monitoring.
* Check Email Inbox for Welcome Email along with the Qualtrics Survey Link.
* Click through the Qualtrics Survey.
* Approve the Equipment and Training requirements of newly hired employee in SAP Build Process Automation Inbox.

### Check the Cloud Integration Monitoring

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
> If the status is not reflecting as **Completed** for any of the mentioned integration flow, kindly contact one of the session instructor to troubleshoot.
