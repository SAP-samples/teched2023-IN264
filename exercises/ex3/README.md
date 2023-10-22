![image](https://github.com/SAP-samples/teched2023-IN264/assets/4324378/d050e676-20b8-4f6c-96f6-9ef2a1f10da7)# Exercise 3 - Create the subscription flow that triggers the SAP Build Process Automation (SBPA) equipment and training approval workflow

In this exercise, you will setup an integration flow that listens to the SAP Integration Suite, advanced event mesh queue using the Cloud Integration AMQP sender adapter. This queue is subscribed to the topic `SuccessFactors/NewHire/{EmployeeId}` where SAP SuccessFactors publishes new hire events. This integration triggers the SAP Build Process Automation (SBPA) equipment and training approval workflow in real-time. Once the manager approves the new hire equipments and trainings, SBPA publishes an event to the SAP Integration Suite, advanced event mesh topic `SBPA/NewHire/{EmployeeId}/Approval` for further integration.

## Exercise steps

Run through the exercise steps in the given order.

### Create a new Integration Package

1. Open the [SAP Integration Suite tenant](https://in264-72e8h9xc.integrationsuite.cfapps.eu10-002.hana.ondemand.com/shell/home) and log in using the user ID and password provided to you by the instructors.
<br><img src="/exercises/ex3/images/IS_Login.png" width=50% height=50%> 	

2. From the navigation pane on the left side, switch to the **Design --> Integrations** area.
<br><img src="/exercises/ex3/images/IS_CI_Navigate.png" width=90% height=90%>

3. Click the **"Create"** button on the top right area to create your own package.
<br><img src="/exercises/ex3/images/CI_Create_Package_1.png" width=100% height=100%>

4. Provide the following details:
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   
- Name: **Combine SAP Integration Suite and SAP Build Process Automation in HR - IN264-XXX**
- Short Description: **An event-driven enterprise automation scenario using SAP Integration Suite, SAP Integration Suite advanced event mesh, also incorporating human interactions by leveraging SAP Build Process Automation for streamlined employee onboarding subprocess.**
- Version: **1.0.0**
- Vendor: **SAP TechEd 2023**
<br/><br/>Press the **"Save"** button.
<br><img src="/exercises/ex3/images/CI_Create_Package_2.png" width=100% height=100%>

5. Now you have two options:   
a) [Option A](#option-a-create-integration-flow-from-scratch): Either you can create the Integration Flow from scratch.<br/>
b) [Option B](#option-b-copy--configure-integration-flow-from-solution-package): Or, you can copy & configure the integration flow from the solution package.

### Option A) Create Integration Flow from scratch

1. Switch to the "<b>Artifacts</b>" tab and press "<b>Add > Integration Flow</b>".
<br><img src="/exercises/ex3/images/CI_SBPA_Create_1.png" width=90% height=90%>

2. Provide the following details:
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   
- Name: **SAP SFSF New Hire Onboarding Process Approval Workflow using SAP Build Process Automation - IN264-XXX**
- Description: **This Integration flow triggers the new hire onboarding process automation for the newly hired candidate's Equipment and Training to the manager using SAP Build Process Automation. This is implemented using an Event-Driven Integration Pattern.**
- Sender: **AEM**
- Receiver: **SAP Build Process Automation**
<br/><br/>Press the **"OK"** button.
<br><img src="/exercises/ex3/images/CI_SBPA_Create_2.png" width=70% height=70%>

3. Click on the created Integration Flow to open it.
<br><img src="/exercises/ex3/images/CI_SBPA_Create_3.png" width=100% height=100%>

4. Enable **Edit** mode.
   > [!IMPORTANT]
   > Remember to **save** your work regularly.
   
   <br><img src="/exercises/ex3/images/CI_SBPA_Edit.png" width=90% height=90%>

5. Double click on the "<b>Sender</b>" participant or press the "<b>Restore</b>" button on the bottom right to expand the details menu.
<br><img src="/exercises/ex3/images/CI_SBPA_Model_1.png">

6. Rename "<b>Sender</b>" to **AEM**.<br/>
<br><img src="/exercises/ex3/images/CI_SBPA_Model_2.png">

7. Press and drag the "<b>Connector</b>" button to connect the <b>AEM</b> sender with the <b>Start</b> step.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_3.png">

8. Select <b>AMQP</b> as sender adapter and choose <b>TCP</b> as Transport Protocol.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_4.png">
<br><img src="/exercises/ex3/images/CI_SBPA_Model_5.png">

9. Switch to "<b>Connection</b>" tab and provide the following details:  
- Host: **mr-connection-qs6tj0v0zlv.messaging.solace.cloud**  
- Port: **5671**  
- Credential Name: **AEM_Credential**  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_6.png">

10. Switch to "<b>Processing</b>" tab and privde the following details:
    > [!IMPORTANT]
    > Replace **XXX** with the participant number that is assigned to you.
   - Queue Name: **NewHire_Workflow_IN264-XXX**
   - Max. Number of Retries: **0**  
   <br><img src="/exercises/ex3/images/CI_SBPA_Model_7.png">

11. In order to open the general <b>Integration Flow settings</b>, click on a white space in the IFlow Diagram as shown in the screenshot.  
Change to <b>“References”</b> tab and navigate to <b>“Global”</b> tab.  
Click <b>“Add References” -> “Script Collection”</b> to create a new Script Collection Reference. 
<br><img src="/exercises/ex3/images/CI_SBPA_Model_8.png">

12. Select the Package **"IN264 - Combine SAP Integration Suite and SAP Build Process Automation in HR - Solution"**.
    > [!Note]
    > Script Collection and Message Mapping artifacts that are required for this exercise is already created and deployed as part of the Solution package and with this step we just referencing the same without the need of creating it again and again for each participant.  

      <br><img src="/exercises/ex3/images/CI_SBPA_Model_9.png">
   
13. Select **“SC MPL_Utils”** and press **“OK”**. Now you have successfully added a Global Script Collection as reference in your integration flow.
    > [!Note]
    > The "SC MPL_Utils" contains one script "Log Payload" to add payloads as attachments in the message processing log (MPL).   

      <br><img src="/exercises/ex3/images/CI_SBPA_Model_10.png">
   
14. Next, you need to add a mapping reference. Press **"Add References"** and choose **"Message Mapping"**.
<br><img src="/exercises/ex3/images/CI_SBPA_Model_11.png">

15. Select the Package **"IN264 - Combine SAP Integration Suite and SAP Build Process Automation in HR - Solution"**.
<br><img src="/exercises/ex3/images/CI_SBPA_Model_12.png">

16. Select "<b>MM_SFSF_Event_JSON_to_SBPA_Workflow_JSON</b>" and press <b>OK</b>.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_13.png">

17. Select the <b>“Start”</b> step and press the “<b>+</b>” button to create a new flow step.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_13_5.png"> 

18. Choose <b>"Groovy Script"</b> step.
<br><img src="/exercises/ex3/images/CI_SBPA_Model_14.png">  

19. Rename the step to <b>Log New Hire Event Payload</b>.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_15.png">

20. Switch to tab "<b>Processing</b>" and press the "<b>Select</b>" button.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_16.png"> 

21. Navigate to "<b>Global Resources</b>" and choose "<b>Log_Payload</b>". Press "<b>OK</b>".  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_17.png">

22. Enter <b>logNewHireEventPayload</b> as Script Function.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_18.png">

23. Select the "<b>Log New Hire Event Payload</b>" step and press the "<b>+</b>" button.
<br><img src="/exercises/ex3/images/CI_SBPA_Model_19.png">

24. Choose "<b>Content Modifier</b>" step.
<br><img src="/exercises/ex3/images/CI_SBPA_Model_20.png"> 

25. Rename the step to <b>Set Properties</b>.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_21.png"> 

26. Switch to the "<b>Exchange Property</b>" tab and press the "<b>Add</b>" button twice to provide the following values:
    > [!IMPORTANT]
    > Replace **XXX** with the participant number that is assigned to you.
    > <br/> Make sure to add the manager Email ID in small case.
    > <br/><br/>You only act as a manager for the hired new employee that's why we need to add your used ID as Manager's Email ID, so that you get the approval task in your inbox.
    
    - <b>Property 1</b>
       - Name: **managerEmailID**
       - Source Type: **Constant**
       - Source Value: **in264-XXX@education.cloud.sap**
         
    - <b>Property 2</b>
       - Name: **workflowDefinitionID**
       - Source Type: **Constant**
       - Source Value: [**workflowDefinitionID-created-in-exercise-1**](../ex2/README.md)

      <br><img src="/exercises/ex3/images/CI_SBPA_Model_22.png"> 

27. Widen the Integration Process box to make space for some more steps. Select the "<b>Set Properties</b>" step and press the "<b>+</b>" button to create a new step.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_23.png"> 

28. Search for <b>Message</b> and choose <b>Message Mapping</b> step.
<br><img src="/exercises/ex3/images/CI_SBPA_Model_24.png">   

29. Rename the step to <b>Map New Hire Event Payload to SBPA Workflow Payload</b>.
    >Hint: Widen the process step to see the full name.
    
    <br><img src="/exercises/ex3/images/CI_SBPA_Model_25.png">

30. Switch to the "<b>Processing</b>" tab and press the "<b>Select</b>" button.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_26.png">

31. Open "<b>Global Resources</b>" and select "<b>MM_SFSF_Event_JSON_to_SBPA_Workflow_JSON</b>" mapping.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_27.png">

32. Select the "<b>Map New Hire Event Payload to SBPA Workflow Payload</b>" step and press the "<b>+</b>" button.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_28.png">

33. Choose "<b>Content Modifier</b>" step.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_29.png">

34. Rename the step to <b>Set Headers</b>.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_30.png">

35. Switch to the "<b>Message Header</b>" tab and press the "<b>Add</b>" button twice to provide the following headers:
   > [!Note]
   > **SAP_ApplicationID** header allows you to search with the new hire employeeId in the Message Procesing Logs (MPL).

   - <b>Header 1</b>
       - Name: **Content-Type**
       - Source Type: **Constant**
       - Source Value: **application/json**
         
   - <b>Header 2</b>
       - Name: **SAP_ApplicationID**
       - Source Type: **Property**
       - Source Value: **employeeId**

      <br><img src="/exercises/ex3/images/CI_SBPA_Model_30_5.png">

36. Select the "<b>Set Headers</b>" step and press the "<b>+</b>" button to add the last step.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_31.png"> 

37. Choose "<b>Request Reply</b>" step.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_32.png">  

38. Rename the step to <b>Trigger SAP Build Process Automation Workflow</b>.
>Hint: Widen the process step to see the full name.  

<br><img src="/exercises/ex3/images/CI_SBPA_Model_32_5.png"> 

39. Place the "<b>Receiver</b>" underneath to the Integration Process and rename it to <b>SBPA</b>.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_33.png">

40. Select the "<b>Trigger SAP Build Process Automation Workflow</b>" step. Press and drag the "<b>Connector</b>" button to connect the Request Reply step with the <b>SPBA</b> receiver.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_34.png">

41. Select "<b>HTTP</b>" as Receiver Adapter.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_35.png">

42. Navigate to "<b>Connection</b>" and provide the following details:  

- Address: **https://spa-api-gateway-bpi-eu-prod.cfapps.eu10.hana.ondemand.com/workflow/rest/v1/workflow-instances**
- Method: **POST**
- Authentication: **OAuth2 Client Credentials**
- Credential Name: **SBPA_OAuth2**
- Request Headers: **Content-Type**  

<br><img src="/exercises/ex3/images/CI_SBPA_Model_36.png">

43. Click “<b>Save as Version</b>” on top right of the window.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_37.png"> 

44. Provide the following properties and Press "<b>OK</b>".
 - Version: **1.0.0**
 - Comment: **initial version**  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_37_5.png"> 

45. Press “<b>Deploy</b>” and confirm the dialog with “<b>Yes</b>” to deploy your integration flow.
<br><img src="/exercises/ex3/images/CI_SBPA_Model_38.png">
<br><img src="/exercises/ex3/images/CI_SBPA_Deploy_Confirmation.png" width=80% height=80%>
<br><img src="/exercises/ex3/images/CI_SBPA_Deployment.png" width=80% height=80%>

### Option B) Copy & Configure Integration Flow from solution package

1. Open the [solution package](https://in264-72e8h9xc.integrationsuite.cfapps.eu10-002.hana.ondemand.com/shell/design/contentpackage/IN264CombineSAPIntegrationSuiteandSAPBuildProcessAutomationinHR?section=ARTIFACTS) available in Cloud Integration capability of SAP Integration Suite and log in using the user ID and password provided to you by the instructors.
<br><img src="/exercises/ex3/images/CI_Solution_Package.png" width=90% height=90%>
  
2. Search for the **SAP SFSF New Hire Onboarding Process Approval Workflow using SAP Build Process Automation** integration flow and from the **Actions** menu, select the **Copy** menu entry.
<br><img src="/exercises/ex3/images/CI_SBPA_Copy_1.png" width=90% height=90%>

3. In the **Copy** dialog, update the name of the integration flow to **SAP SFSF New Hire Onboarding Process Approval Workflow using SAP Build Process Automation - IN264-XXX**
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   <img src="/exercises/ex3/images/CI_SBPA_Copy_2.png" width=90% height=90%>

4. Press **Select** to choose another package as destination.
<br/>As the target package, choose the package that you had created i.e. **Combine SAP Integration Suite and SAP Build Process Automation in HR - IN264-XXX** to ensure that the integration flow is copied into your package.
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   <img src="/exercises/ex3/images/CI_SBPA_Copy_3.png" width=90% height=90%>

5. When done, select the **Copy** button to copy the Integration Flow into your package.
<br><img src="/exercises/ex3/images/CI_SBPA_Copy_4.png" width=90% height=90%>

6. After the integration flow has been copied, you are asked to navigate to your package. Confirm by clicking on the **Navigate** button.
<br><img src="/exercises/ex3/images/CI_SBPA_Navigate.png" width=90% height=90%>

7. After copying the integration flow **SAP SFSF New Hire Onboarding Process Approval Workflow using SAP Build Process Automation - IN264-XXX**, you should see the same in your package. From the **Actions** menu of the integration flow, select the **Configure** menu entry.
<br><img src="/exercises/ex3/images/CI_SBPA_Configure_1.png" width=90% height=90%>

8. In the **Conifigure** dialog, as *Queue Name* enter **NewHire_Workflow_IN264-XXX**. This queue has already been created in [exercise 1](../ex1/README.md).
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   <img src="/exercises/ex3/images/CI_SBPA_Configure_2.png" width=90% height=90%>

9. Switch to the <b>"More"</b> tab and provide the following values:
    > [!IMPORTANT]
    > Replace **XXX** with the participant number that is assigned to you.
    > <br/> Make sure to add the manager Email ID in small case.
    > <br/><br/>You only act as a manager for the hired new employee that's why we need to add your used ID as Manager's Email ID, so that you get the approval task in your inbox.

   - Manager_Email: **in264-XXX@education.cloud.sap**
   - SBPA_Workflow_Definition_ID: [**workflowDefinitionID-created-in-exercise-1**](../ex2/README.md)
  
   <br><img src="/exercises/ex3/images/CI_SBPA_Configure_3.png">
   
10. Then click on **Save** button, in case of any warning just ignore it. Once saved, click on the **Deploy** button.
<br><img src="/exercises/ex3/images/CI_SBPA_Configure_Save.png" width=90% height=90%>
    
11. Click on **Yes** to confirm the deployment and close the confirmation dialog.
<br><img src="/exercises/ex3/images/CI_SBPA_Deploy_Confirmation.png" width=80% height=80%>
<br><img src="/exercises/ex3/images/CI_SBPA_Deployment.png" width=80% height=80%>

### Check the deployment status

1. From the navigation pane on the left side, switch to the **Monitor --> Integrations** area.
<br><img src="/exercises/ex3/images/CI_SBPA_Monitor_1.png" width=40% height=40%>

2. In the Monitor overview, select the first tile below the **Manage Integration Content** section.
<br><img src="/exercises/ex3/images/CI_SBPA_Monitor_2.png" width=80% height=80%>

3. Search for your integration flow i.e. **SAP SFSF New Hire Onboarding Process Approval Workflow using SAP Build Process Automation - IN264-XXX**. Check and confirm that the status has turned to **Started**.
    > [!IMPORTANT]
    > Replace **XXX** with the participant number that is assigned to you.
    <img src="/exercises/ex3/images/CI_SBPA_Monitor_Started.png" width=90% height=90%>

## Summary

At the end of this exercise, you should have copied, configured and deployed an integration flow to send out the welcome email along with the survey link to the newly hired employee's email ID.

Continue to - [Exercise 4 - Copy, configure and deploy the Survey Email subscription flow](/exercises/ex4/README.md)
