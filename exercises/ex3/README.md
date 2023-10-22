# Exercise 3 - Create the subscription flow that triggers the SAP Build Process Automation (SBPA) equipment and training approval workflow

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
b) [Option B](#option-b-copyconfigure-integration-flow-from-solution-package): Or, you can copy & configure the integration flow from the solution package.

### Option A) Create Integration Flow from scratch

1. Switch to the "<b>Artifacts</b>" tab and press "<b>Add > Integration Flow</b>"
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

19. Rename the step to <b>Log New Hire Event Payload</b>  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_15.png">

20. Switch to tab "<b>Processing</b>" and press the "<b>Select</b>" button.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_16.png"> 

21. Navigate to "<b>Global Resources</b>" and choose "<b>Log_Payload</b>". Press "<b>OK</b>".  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_17.png">

22. Enter <b>logNewHireEventPayload</b> as Script Function.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_18.png">

23. Select the "<b>Log New Hire Event Payload</b>" step and press the "<b>+</b>" button.  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_19.png">

24. Choose "<b>Content Modifier</b>".  
<br><img src="/exercises/ex3/images/CI_SBPA_Model_20.png"> 

27. Rename the step to <b>Set Properties</b>.  
![image](https://media.github.tools.sap/user/13842/files/3294eca9-6c83-43f6-a20a-2c51ef783e01)  

28. Switch to tab "<b>Exchange Property</b>". And press the "<b>Add</b>" button twice and provide following values: 
>Provide your personal email address to receive a notification email once a Purchase Order Requisition has been created  

<b>Property 1</b>  
- Name: managerEmailID  
- Source Type: Constant  
- Source Value: <b>your-personal-email-address</b>  

>Provide the workflow definition ID created in exercise 1.  

<b>Property 2</b>
- Name: workflowDefinitionID  
- Source Type: Constant  
- Source Value: <b>workflowDefinitionID-created-in-ex1</b>  

![image](https://media.github.tools.sap/user/13842/files/4dd691ff-6b4a-4823-8371-d351d873a773)  

27. Widen the Integration Process box to make space for some more steps. Select the "<b>Set Properties</b>" step and press the "<b>+</b>" button to create a new step.  
![image](https://media.github.tools.sap/user/13842/files/1cd4f55d-0ebc-4cf2-bc63-f7404cd1809f)  

28. Search for <b>Message</b> and choose <b>Message Mapping</b>  
![image](https://media.github.tools.sap/user/13842/files/f259679e-b82c-4d8f-953e-ffa4143458d2)  

29. Rename the step to <b>Map New Hire Event Payload to SBPA Workflow Payload</b>  
![image](https://media.github.tools.sap/user/13842/files/75107af9-af0f-4d19-aae5-057e625af5d1)  

30. Navigate to tab "<b>Processing</b>" and press the "<b>Select</b>" button.  
![image](https://media.github.tools.sap/user/13842/files/143d49ef-9034-4ecf-b344-59363f70d221)  

31. Open "<b>Global Resources</b>" and select "<b>MM_SFSF_Event_JSON_to_SBPA_Workflow_JSON</b>".  
![image](https://media.github.tools.sap/user/13842/files/315b6b7f-bb6d-4d54-82cc-e30504ded711)  

32. Select the "<b>Map New Hire Event Payload to SBPA Workflow Payload</b> " step and press the "+" button.  
![image](https://media.github.tools.sap/user/13842/files/b075c50f-1e36-409e-af3c-abc3e25b638c)  

33. Choose "<b>Content Modifier</b>".  
![image](https://media.github.tools.sap/user/13842/files/c0f647b8-d4a5-4831-a091-42499ea1bc6d)  

34. Rename the step to <b>Set Headers</b>.  
![image](https://media.github.tools.sap/user/13842/files/57e5e239-d905-44ac-8a96-106bd317eb33)  

35. Navigate to "<b>Message Header</b>" tab, press the "<b>Add</b>" button twice and provide following headers:  
<b>Header 1</b>
- Name: Content-Type  
- Source Type: Constant  
- Source Value: application/json  

<b>Header 2</b>
- Name: SAP_ApplicationID  
- Source Type: <b>Property</b>  
- Source Value: employeeId

36. Select the "<b>Set Headers</b>" step and press the "<b>+</b>" button to add the last step.  
![image](https://media.github.tools.sap/user/13842/files/d3cbb610-7fe0-4833-86a0-88fadc7b69cc)  

37. Select "<b>Request Reply</b>"  
![image](https://media.github.tools.sap/user/13842/files/805d8e84-aeac-4744-ac06-21026dd3046f)  

38. Rename the step to <b>Trigger SAP Build Process Automation Workflow</b>
>Hint: Widen the process step to see the full name  
![image](https://media.github.tools.sap/user/13842/files/56d73617-2964-4c00-bb31-ef2e1a882255)  

39. Place the "<b>Receiver</b>" underneath the Integration Process and rename it to <b>SBPA</b>.  
![image](https://media.github.tools.sap/user/13842/files/786a906a-3094-4a6f-8a7b-2115f4691c40)  

40. Select the "<b>Trigger SAP Build Process Automation Workflow</b>" step. Press and drag the "<b>Connector</b>" button to connect the Request Reply step with the <b>SPBA</b> receiver.  
![image](https://media.github.tools.sap/user/13842/files/44567ee5-eb2e-44d7-bb2e-8beabc2255cc)  

41. Select "<b>HTTP</b>" as Adapter.  
![image](https://media.github.tools.sap/user/13842/files/2bdfe99d-ce32-4367-87b6-2a8e9b435a1b)

42. Navigate to "<b>Connection</b>" and provide following details:  

- Address: https://spa-api-gateway-bpi-eu-prod.cfapps.eu10.hana.ondemand.com/workflow/rest/v1/workflow-instances
- Method: POST
- Authentication: OAuth2 Client Credentials
- Credential Name: SBPA_OAuth2
- Request Headers: Content-Type  

![image](https://media.github.tools.sap/user/13842/files/250526d1-d528-44e5-851d-2e44049169c6)  

42. Click “<b>Save as Version</b>” on top right of the window.  
![image](https://media.github.tools.sap/user/13842/files/5467c7eb-fd91-44d1-b35a-b38fc6668990)  

43. Step 103. Provide the following properties and Press "<b>OK</b>".
 - Version: 1.0.0
- Comment: initial version  
![image](https://media.github.tools.sap/user/13842/files/f1afac41-a905-40d0-b5f5-aa537af9568e)  

44. Press “<b>Deploy</b>” and confirm the dialog with “<b>Yes</b>” to deploy your integration flow.
![image](https://media.github.tools.sap/user/13842/files/e047f158-c289-4696-8aaf-e50d9f324cfd)

### Option B) Copy&Configure Integration Flow from solution package

1. <b>Open</b> the solution package by clicking this [URL](https://in264-72e8h9xc.integrationsuite.cfapps.eu10-002.hana.ondemand.com/shell/design/contentpackage/IN264CombineSAPIntegrationSuiteandSAPBuildProcessAutomationinHR?section=ARTIFACTS)  
2. Search for the "SAP SFSF New Hire Onboarding Process Approval Workflow using SAP Build Process Automation" integration flow, press the "<b>Action</b>" button and select "<b>Copy</b>"  
![image](https://media.github.tools.sap/user/13842/files/3306b461-d748-4cd5-8f08-f318cba2592c) 

3. Press the "<b>Select</b>" button and choose your Integration Package just created.  
![image](https://media.github.tools.sap/user/13842/files/5af07785-d794-4a97-bf55-f6f5e3320473) 

![image](https://media.github.tools.sap/user/13842/files/acad9d17-0174-4480-9b85-902ce8286a9a)

4. As name enter <b>(Replace XXX with the participant number provided by your instructor)</b>:  
SAP SFSF New Hire Onboarding Process Approval Workflow using SAP Build Process Automation - <b>IN264-XXX</b>  
![image](https://media.github.tools.sap/user/13842/files/d59884b8-1904-4788-8152-3c7f79c927ed)

5. Press "<b>Copy</b>"  
![image](https://media.github.tools.sap/user/13842/files/93bc719e-4ccf-4b62-9349-e2f219a92a1b)

6. The Success Dialog will pop-up. Press "<b>Navigate</b>" to open the package.  
![image](https://media.github.tools.sap/user/13842/files/ba634d88-ab6d-4153-b04b-e8dca85dc845)

7. Press the "<b>Action</b>" button and click on "<b>Configure</b>".
![image](https://media.github.tools.sap/user/13842/files/e6246e71-0e49-48ae-ad89-7b7c7ac03c9c)

8. As Queue Name enter <b>(Replace XXX with the participant number provided by your instructor)</b>:  
NewHire_Workflow_<b>IN264-XXX</b>  
![image](https://media.github.tools.sap/user/13842/files/9b7dddc3-9a64-4cd4-b99e-7c1a45c69ae5)  

9. Switch to tab <b>"More"</b> and provide following properties:  
  >Provide your personal email address to receive a notification email once a Purchase Order Requisition has been created   
  
  - Manager_Email: <b>your-personal-email-address</b>  
  >Provide the workflow definition ID created in exercise 1.  
  
  
  - SBPA_Workflow_Definition: <b>workflowDefinitionID-created-in-ex1</b>  
![image](https://media.github.tools.sap/user/13842/files/701f3ce3-58df-4c55-890c-bf15ac44d858)  

10. Press "<b>Save</b>" and close the Warning Dialog.  
![image](https://media.github.tools.sap/user/13842/files/401ff6df-4105-40da-8db1-1232b2c56f3e)  


11. Press <b>"Deploy"</b> and confirm the deployment.  
![image](https://media.github.tools.sap/user/13842/files/9ee1027d-01f8-49f1-99ff-7db0a5844831)  

Congratulations! You successfully completed the exercise.



### Check the deployment status

11. From the navigation pane on the left side, switch to the **Monitor --> Integrations** area.
<br><img src="/exercises/ex3/images/CI_SBPA_Monitor_1.png" width=40% height=40%>

12. In the Monitor overview, select the first tile below the **Manage Integration Content** section.
<br><img src="/exercises/ex3/images/CI_SBPA_Monitor_2.png" width=80% height=80%>

13. Search for your integration flow i.e. **SAP SFSF New Hire Onboarding Process Approval Workflow using SAP Build Process Automation - IN264-XXX**. Check and confirm that the status has turned to **Started**.
    > [!IMPORTANT]
    > Replace **XXX** with the participant number that is assigned to you.
    <img src="/exercises/ex3/images/CI_SBPA_Monitor_Started.png" width=90% height=90%>

## Summary

At the end of this exercise, you should have copied, configured and deployed an integration flow to send out the welcome email along with the survey link to the newly hired employee's email ID.

Continue to - [Exercise 4 - Copy, configure and deploy the Survey Email subscription flow](/exercises/ex4/README.md)
