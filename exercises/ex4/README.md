# Exercise 4 - Copy, configure and deploy the Survey Email subscription flow

In this exercise, you will setup an integration flow that listens to the SAP Integration Suite, advanced event mesh queue using the Cloud Integration AMQP sender adapter. This queue is subscribed to the topic `SuccessFactors/NewHire/{EmployeeId}` where SAP SuccessFactors publishes new hire events. This integration triggers a real-time welcome email, along with a survey link using the Mail receiver adapter upon adding a new employee in SAP SuccessFactors. By clicking the survey link, candidate can provide the onboarding experience feedback.

## Exercise steps

Run through the exercise steps in the given order.

### Copy the integration flow

1. Open the [solution package](https://in264-72e8h9xc.integrationsuite.cfapps.eu10-002.hana.ondemand.com/shell/design/contentpackage/IN264CombineSAPIntegrationSuiteandSAPBuildProcessAutomationinHR?section=ARTIFACTS) available in Cloud Integration capability of SAP Integration Suite and log in using the user ID and password provided to you by the instructors.
<br><img src="/exercises/ex4/images/CI_Solution_Package.png" width=90% height=90%> 	

2. Search for the **SAP SFSF New Hire Welcome Email with Survey Link** integration flow and from the **Actions** menu, select the **Copy** menu entry.
<br><img src="/exercises/ex4/images/CI_SM_Copy_1.png" width=90% height=90%> 	

3. In the **Copy** dialog, update the name of the integration flow to **SAP SFSF New Hire Welcome Email with Survey Link - IN264-XXX**
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   <img src="/exercises/ex4/images/CI_SM_Copy_2.png" width=90% height=90%>
     
4. Press **Select** to choose another package as destination.
<br/>As the target package, choose the the package that you had created in [exercise 3](../ex3/README.md) i.e. **Combine SAP Integration Suite and SAP Build Process Automation in HR_IN264-XXX** to ensure that the integration flow is copied into your package.
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   <img src="/exercises/ex4/images/CI_SM_Copy_3.png" width=90% height=90%>

5. When done, select the **Copy** button to copy the Integration Flow into your package.
<br><img src="/exercises/ex4/images/CI_SM_Copy_4.png" width=90% height=90%>

6. After the integration flow has been copied, you are asked to navigate to your package. Confirm by clicking on the **Navigate** button.
<br><img src="/exercises/ex4/images/CI_SM_Navigate.png" width=90% height=90%>

### Configure and deploy the integration flow

7. After copying the integration flow **SAP SFSF New Hire Welcome Email with Survey Link - IN264-XXX**, you should see the same in your package. From the **Actions** menu of the integration flow, select the **Configure** menu entry.
<br><img src="/exercises/ex4/images/CI_SM_Configure_1.png" width=90% height=90%>

8. In the **Conifigure** dialog, as *Queue Name* enter **NewHire_SurveyEmail_IN264-XXX**. This queue has already been created in [exercise 1](../ex1/README.md).
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   <img src="/exercises/ex4/images/CI_SM_Configure_2.png" width=90% height=90%>
    
9. Then click on **Save** button, in case of any warning just ignore it. Once saved, click on the **Deploy** button.
<br><img src="/exercises/ex4/images/CI_SM_Configure_Save.png" width=90% height=90%>
    
10. Click on **Yes** to confirm the deployment and close the confirmation dialog.
<br><img src="/exercises/ex4/images/CI_SM_Deploy_Confirmation.png" width=80% height=80%>
<br><img src="/exercises/ex4/images/CI_SM_Deployment.png" width=80% height=80%>

### Check the deployment status

11. From the navigation pane on the left side, switch to the **Monitor --> Integrations** area.
<br><img src="/exercises/ex4/images/CI_SM_Monitor_1.png" width=40% height=40%>

12. In the Monitor overview, select the first tile below the **Manage Integration Content** section.
<br><img src="/exercises/ex4/images/CI_SM_Monitor_2.png" width=80% height=80%>

13. Search for your integration flow i.e. **SAP SFSF New Hire Welcome Email with Survey Link - IN264-XXX**. Check and confirm that the status has turned to **Started**.
    > [!IMPORTANT]
    > Replace **XXX** with the participant number that is assigned to you.
    <img src="/exercises/ex4/images/CI_SM_Monitor_Started.png" width=90% height=90%>

## Summary

At the end of this exercise, you should have copied, configured and deployed an integration flow to send out the welcome email along with the survey link to the newly hired employee's email ID.

Continue to - [Exercise 5 - Copy, configure and deploy the SAP S/4Hana Purchase Requsition subscription flow](/exercises/ex5/README.md)
