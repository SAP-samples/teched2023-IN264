# Exercise 3 - Create the Integration Flow to subscribe abd trigger SAP Build Process Automation (SBPA) approval workflow
In this exercise, you will setup an integration flow, which triggers the SAP Build Process Automation approval workflow based on 
new hire events received from SuccessFactors via Advanced Event Mesh.


## Create a new Integration Package

1. First you need to open the SAP Integration Suite tenant via this [URL](https://in264-72e8h9xc.integrationsuite.cfapps.eu10-002.hana.ondemand.com/shell/home)
<br/>Choose <b>"tdct3ched2.accounts.ondemand.com"</b> as Identity Provider.
<br/>![image](https://media.github.tools.sap/user/13842/files/49e84695-aefe-4f11-b77b-a62d774a2598)

2. Log onto the system with the username and password provided by your instructor and press <b>"Continue"</b>:
<br/>![image](https://media.github.tools.sap/user/13842/files/d74deae6-3ec4-4be0-9e96-609195913341)

3. Navigate to "<b>Design > Integrations</b>" and press "<b>Create</b>"
![image](https://media.github.tools.sap/user/13842/files/3ae039f0-1897-4454-8a26-b7d56a387f0e)

4. Provide following details <b>(Replace XXX with the participant number provided by your instructor)</b> and press "<b>Save</b>":
- <b>Name:</b> Combine SAP Integration Suite and SAP Build Process Automation in HR - <b>IN264-XXX</b>
- <b>Short Description:</b> An event-driven enterprise auto scenario where you react and respond to a new hire business event using SAP Integration Suite and includes human interactions to achieve an end-to-end employee onboarding business process using SAP Build Process Automation.</b>  
![image](https://media.github.tools.sap/user/13842/files/16a49223-1861-4e21-afb2-8e055834301a)

5. Now you have two options:   
a) Either you can copy&configure the integration flow from the solution package and continue with [Option A](#option-a-copyconfigure-integration-flow-from-solution-package)  
b) You can create the Integration Flow from scratch, continue with [Option B](option-a-copyconfigure-integration-flow-from-solution-package)

## Option A) Copy&Configure Integration Flow from solution package

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


## Option B) Create Integration Flow from scratch


1. Switch to tab "<b>Artifacts</b>" and press "<b>Add > Integration Flow</b>"
![image](https://media.github.tools.sap/user/13842/files/9d8b92e6-479c-416f-bc8a-60391f486efe)

2. Provide following details <b>(Replace XXX with the participant number provided by your instructor)</b> and press "<b>Save</b>":  
- <b>Name:</b> SAP SFSF New Hire Onboarding Process Approval Workflow using SAP Build Process Automation - <b>IN264-XXX</b> 
- <b>Description:</b> This Integration flow triggers the new hire onboarding process automation for the newly hired candidate's Equipment and Training to the manager using SAP Build Process Automation. This is implemented using an Event-Driven Integration Pattern.  
- <b>Sender:</b> AEM
- <b>Receiver:</b> SAP Build Process Automation 
<br/><br/>Press "<b>OK</b>":  
<br/>![image](https://media.github.tools.sap/user/13842/files/a589dd78-2a61-4b8e-9dcf-e544238b403b)  

3. Open the Integration Flow:
![image](https://media.github.tools.sap/user/13842/files/71bb2a72-0290-4503-922e-a6d9199429f8) 

4.Enable edit mode.
<br/>![image](https://media.github.tools.sap/user/13842/files/c149af40-4fea-4a43-853a-f43ab4bb7e14)  

5. Double click on the "<b>Sender</b>" participant or press the "<b>Restore</b>" button on the bottom right to expand the details menu.
<br/>![image](https://media.github.tools.sap/user/13842/files/19e8a446-61b3-4360-b93c-cb812a67fe14)
6. Rename "<b>Sender</b>" to AEM.<br/>
![image](https://media.github.tools.sap/user/13842/files/d60f2bbc-2770-41f4-bcb9-7a8fb893e6b1)  
7. Press and drag the "<b>Connector</b>" button to connect the <b>AEM</b> sender with the <b>Start</b> step.  
![image](https://media.github.tools.sap/user/13842/files/b6d8947b-108d-48c3-99ad-b204bb9df251)
8. Select <b>AMQP</b> as sender adapter and choose <b>TCP</b> as Transport Protocol.  
![image](https://media.github.tools.sap/user/13842/files/5cc8e23f-c0bc-4cd7-bf85-43b7dab3e1f7)  
![image](https://media.github.tools.sap/user/13842/files/b27f9c48-bbc9-486b-87e5-8a5bac8b92a2)  
9. Switch to tab "<b>Connection</b>" and provide following details:  
- <b>Host</b>: mr-connection-qs6tj0v0zlv.messaging.solace.cloud  
- <b>Port</b>: 5671  
- <b>Credential Name</b>: AEM_Credential  
![image](https://media.github.tools.sap/user/13842/files/3cb1c49c-8461-405d-b0a3-0dba088278d8) 
10. Switch to tab Processing and privde following details <b>(Replace XXX with the participant number provided by your instructor)</b>:  
- <b>Queue Name</b>: NewHire_Workflow_<b>IN264-XXX</b> 
- <b>Max. Number of Retries</b>: 0  

![image](https://media.github.tools.sap/user/13842/files/8e4ccfe4-c659-4302-b38f-a860008e1ba3)  

11. In order to open the general <b>Integration Flow settings</b>, click on a white space in the IFlow Diagram as shown in the screenshot.  
Change to <b>“References”</b> tab and navigate to <b>“Global”</b> tab.  
Click <b>“Add References” -> “Script Collection”</b> to create a new Script Collection Reference. 
![image](https://media.github.tools.sap/user/13842/files/e6b92098-7292-43aa-8e8c-d34bda74a675)  
12. Select Package “IN264 - Combine SAP Integration Suite and SAP Build Process Automation in HR - Solution”.  
>Note: Script Collection and Message Mapping artifacts that are required for this exercise is already created and deployed as part of the Solution package and with this step we just referencing the same without the need of creating it again and again for each participant.  

![image](https://media.github.tools.sap/user/13842/files/4ef67b56-34fe-4658-8d24-dcb21f8e7848)  
13. Select <b>“SC MPL_Utils”</b> and press <b>“OK”</b>. Now you have successfully added a Global Script Collection as reference in your integration flow.  
>Note: The "SC MPL_Utils" contains one script "Log Payload" to add payloads as attachments in the message processing log (MPL).  

![image](https://media.github.tools.sap/user/13842/files/bd10bcf2-55fb-4603-acf3-484773571ac2)  
14. Next, you need to add a mapping reference. Press <b>Add References</b> and choose <b>Message Mapping</b>
![image](https://media.github.tools.sap/user/13842/files/afa1aedb-6be6-49ad-a2f5-319d3f5d439e)  

15. Select Package “IN264 - Combine SAP Integration Suite and SAP Build Process Automation in HR - Solution”.  
![image](https://media.github.tools.sap/user/13842/files/4ef67b56-34fe-4658-8d24-dcb21f8e7848)  

16. Select "<b>MM_SFSF_Event_JSON_to_SBPA_Workflow_JSON</b>" and press <b>OK</b>.  
![image](https://media.github.tools.sap/user/13842/files/dba1fd8f-a2ae-4239-b46e-62e23bfceee4)  

17. Select the <b>“Start”</b> step and press the “<b>+</b>” button to create a new flow step.  
![image](https://media.github.tools.sap/user/13842/files/6d0ff469-5e5c-4d30-b7b0-11c76dd2c837)  

18. Choose <b>"Groovy Script"</b> step.
![image](https://media.github.tools.sap/user/13842/files/16d89b2f-5160-4b7a-bb12-a9bd467c03d8)  

19. Rename the step to <b>Log New Hire Event Payload</b>  
![image](https://media.github.tools.sap/user/13842/files/33bc0326-9170-4270-ba36-a27983cf65eb)  

20. Switch to tab "<b>Processing</b>" and press the "<b>Select</b>" button.  
![image](https://media.github.tools.sap/user/13842/files/c734f39b-23bf-4f3e-9526-6c4a70d52039)  

21. Navigate to "<b>Global Resources</b>" and choose "<b>Log_Payload</b>". Press "<b>OK</b>".  
![image](https://media.github.tools.sap/user/13842/files/9bfc44b8-5f40-4a28-b09f-1082e2e338ea)  

22. Enter <b>logNewHireEventPayload</b> as Script Function.  
![image](https://media.github.tools.sap/user/13842/files/bb88ca46-95ee-4ef6-8f50-5c7efb94c1cc)  

23. Select the "<b>Log New Hire Event Payload</b>" step and press the "<b>+</b>" button.  
![image](https://media.github.tools.sap/user/13842/files/76f1bfbd-85a9-4b7c-9ab7-486ec59ab5bf)  

24. Choose "<b>Content Modifier</b>".  
![image](https://media.github.tools.sap/user/13842/files/6603992c-87c1-4079-be43-0b9f902efb17)  

25. Rename the step to <b>Set Properties</b>.  
![image](https://media.github.tools.sap/user/13842/files/3294eca9-6c83-43f6-a20a-2c51ef783e01)  

26. Switch to tab "<b>Exchange Property</b>". And press the "<b>Add</b>" button twice and provide following values: 
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