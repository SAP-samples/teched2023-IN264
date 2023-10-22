# Exercise 5 - Copy, configure and deploy the SAP S/4Hana Purchase Requsition subscription flow

In this exercise, you will setup an integration flow that listens to the SAP Integration Suite, advanced event mesh queue using the Cloud Integration AMQP sender adapter. This queue is subscribed to the topic `SBPA/NewHire/{EmployeeId}/Approval` where SAP Build Process Automation (SBPA) publishes manager's approval events. This integration triggers a real-time creation of purchase requisition (PR) with the approved equipments list in the S/4HANA Cloud system using the OData receiver adapter. Once the purchase requisition gets created, Cloud Integration also sends an email to the given newly hired candidate's email ID with the PR number and direct link to open the same in SAP S/4Hana Cloud system.

## Exercise steps

Run through the exercise steps in the given order.

### Copy the integration flow

1. Open the [solution package](https://in264-72e8h9xc.integrationsuite.cfapps.eu10-002.hana.ondemand.com/shell/design/contentpackage/IN264CombineSAPIntegrationSuiteandSAPBuildProcessAutomationinHR?section=ARTIFACTS) available in Cloud Integration capability of SAP Integration Suite and log in using the user ID and password provided to you by the instructors.
<br><img src="/exercises/ex5/images/CI_Solution_Package.png" width=90% height=90%> 	

2. Search for the **Create Purchase Requisition in SAP S4HANA for New Hire Equipment Post Manager Approval** integration flow and from the **Actions** menu, select the **Copy** menu entry.
<br><img src="/exercises/ex5/images/CI_PR_Copy_1.png" width=90% height=90%>

3. In the **Copy** dialog, update the name of the integration flow to **Create Purchase Requisition in SAP S4HANA for New Hire Equipment Post Manager Approval - IN264-XXX**
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   <img src="/exercises/ex5/images/CI_PR_Copy_2.png" width=90% height=90%>

4. Press **Select** to choose another package as destination.
<br/>As the target package, choose the package that you had created in [exercise 3](../ex3/README.md) i.e. **Combine SAP Integration Suite and SAP Build Process Automation in HR_IN264-XXX** to ensure that the integration flow is copied into your package.
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   <img src="/exercises/ex5/images/CI_PR_Copy_3.png" width=90% height=90%>

5. When done, select the **Copy** button to copy the Integration Flow into your package.
<br><img src="/exercises/ex5/images/CI_PR_Copy_4.png" width=90% height=90%>

6. After the integration flow has been copied, you are asked to navigate to your package. Confirm by clicking on the **Navigate** button.
<br><img src="/exercises/ex5/images/CI_PR_Navigate.png" width=90% height=90%>

### Configure and deploy the integration flow

7. After copying the integration flow **Create Purchase Requisition in SAP S4HANA for New Hire Equipment Post Manager Approval - IN264-XXX**, you should see the same in your package. From the **Actions** menu of the integration flow, select the **Configure** menu entry.
<br><img src="/exercises/ex5/images/CI_PR_Configure_1.png" width=90% height=90%>

8. In the **Conifigure** dialog, as *Queue Name* enter **ApprovedNewHire_PR_IN264-XXX**. This queue has already been created in [exercise 1](../ex1/README.md).
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   <img src="/exercises/ex5/images/CI_PR_Configure_2.png" width=90% height=90%>
    
9. Then click on **Save** button, in case of any warning just ignore it. Once saved, click on the **Deploy** button.
<br><img src="/exercises/ex5/images/CI_PR_Configure_Save.png" width=90% height=90%>
    
10. Click on **Yes** to confirm the deployment and close the confirmation dialog.
<br><img src="/exercises/ex5/images/CI_PR_Deploy_Confirmation.png" width=80% height=80%>
<br><img src="/exercises/ex5/images/CI_PR_Deployment.png" width=80% height=80%>

### Check the deployment status

11. From the navigation pane on the left side, switch to the **Monitor --> Integrations** area.
    >Hint: By clicking on the burger icon on the top left corner, you can expand the navigation pane.
    
    <br><img src="/exercises/ex5/images/CI_PR_Monitor_1.png" width=40% height=40%>

13. In the Monitor overview, select the first tile below the **Manage Integration Content** section.
<br><img src="/exercises/ex5/images/CI_PR_Monitor_2.png" width=80% height=80%>

14. Search for your integration flow i.e. **Create Purchase Requisition in SAP S4HANA for New Hire Equipment Post Manager Approval - IN264-XXX**. Check and confirm that the status has turned to **Started**.
    > [!IMPORTANT]
    > Replace **XXX** with the participant number that is assigned to you.
    <img src="/exercises/ex5/images/CI_PR_Monitor_Started.png" width=90% height=90%>

## Summary

At the end of this exercise, you should have copied, configured and deployed an integration flow that automatically create a purchase requisition (PR) with the approved equipments list in the S/4HANA Cloud system.

With this exercise you have completed all the technical configuration steps. Now you have to execute and test the scenario by adding a new employee in SAP SuccessFactors system.

Continue to - [Exercise 6 - Add a New Employee in SAP SuccessFactors](/exercises/ex6/README.md)
