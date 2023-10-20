# Exercise 1 - Create queues and subscribe to topic in SAP Intgration Suite, advanced event mesh

## Overview

To enable the event-driven architecture in this integration scenario, we use **SAP Integration Suite, advanced event mesh**.<br/>
In this exercise, each participant has to create 3 queues and subscribe to the relevant topic.
These queues are then required and subscribed in the later part of the session while configuring or creating the integration interfaces in the Cloud Integration capability of SAP Integration Suite.
<br/><br/>
Run through the following steps in the given order:
1. Open the [SAP Integration Suite, advanced event mesh](https://eu10.console.pubsub.em.services.cloud.sap/login?tenant-id=75520573-e903-4c94-855b-49f03d179a95) tenant and log in using the user ID and password provided to you by the instructors.
   
3. Open the <b>"Cluster Manager"</b> tile.
<br><img src="/exercises/ex1/images/AEM_Cluster_Manager.png" width=90% height=90%> 	

4. Deselect <b>"Only show my services"</b> checkbox.
<br><img src="/exercises/ex1/images/AEM_Services.png" width=90% height=90%> 	

5. Click on the <b>IN264_Teched</b> tile.  
<br><img src="/exercises/ex1/images/AEM_IN264_Teched.png" width=90% height=90%> 	

6. Navigate to the <b>"Manage"</b> tab, and click on <b>"Queues"</b>  
<br><img src="/exercises/ex1/images/AEM_Manage.png" width=90% height=90%> 	

7. A new tab will open and list all of the Queues. Click <b>"+ Queue"</b> to create a new one.
<br><img src="/exercises/ex1/images/AEM_Manage_Queue.png" width=90% height=90%> 	


8. Provide following Queue Name: <b>NewHire_Workflow_IN264-XXX</b> and press <b>Create</b>.
> Replace XXX with the participant number provided by your instructor  

![image](https://media.github.tools.sap/user/13842/files/1060196f-7037-48f7-98cd-f7338a646e19)

8. Press "<b>Apply</b>  
![image](https://media.github.tools.sap/user/13842/files/1cecb8ed-12c4-4d3c-a4d0-1abe6f43f318)  

9. Open the Queue just created (<b>NewHire_Workflow_IN264-XXX</b>)  
![image](https://media.github.tools.sap/user/13842/files/851895c4-f0ee-460e-ab68-b87513e9e2fb)  

10. Navigate to "<b>Subscriptions</b> and press <b>"+ Subscription</b>  
![image](https://media.github.tools.sap/user/13842/files/d0f32eff-9241-43cc-b363-192ece1ecbf4)

11. Provide following value: <b>SFSF/NewHire/IN264-XXX</b> and press <b>"Create"</b>  
> Replace XXX with the participant number provided by your instructor 
![image](https://media.github.tools.sap/user/13842/files/ed9d2dc7-c750-4856-93af-a3744fd43f44)  

12. Naviagte back to Queues.  
![image](https://media.github.tools.sap/user/13842/files/4b4a17f6-d87a-458c-809e-65eecc6547f8)  

13. Press <b>"+ Queue"</b> to create a new one.  
![image](https://media.github.tools.sap/user/13842/files/ce1562b3-cd6d-4d08-92fe-f6d11abbc694)  

14. Provide following Queue Name: <b>NewHire_SurveyEmail_IN264-XXX</b> and press <b>Create</b>.
> Replace XXX with the participant number provided by your instructor  

![image](https://media.github.tools.sap/user/13842/files/c2692310-155b-4d49-8f4b-98d88fde37d4)

15. Press "<b>Apply</b>  
![image](https://media.github.tools.sap/user/13842/files/a6bf72c4-1fff-424c-b349-efe013b8876a)

16. Open the Queue just created (<b>NewHire_SurveyEmail_IN264-XXX</b>)  
![image](https://media.github.tools.sap/user/13842/files/cc4d7371-8dc0-485b-9103-5a3eaab0dc09) 

17. Navigate to "<b>Subscriptions</b> and press <b>"+ Subscription</b>  
![image](https://media.github.tools.sap/user/13842/files/1a2b7370-84c1-4368-8e84-80f1f08e6ea8)

18. Provide following value: <b>SFSF/NewHire/IN264-XXX</b> and press <b>"Create"</b>  
> Replace XXX with the participant number provided by your instructor 
![image](https://media.github.tools.sap/user/13842/files/b253301e-23d4-4be6-93c5-75d1f60b4adc)  

19. Naviagte back to Queues  
![image](https://media.github.tools.sap/user/13842/files/4b4a17f6-d87a-458c-809e-65eecc6547f8)  

20. Press <b>"+ Queue"</b> to create a new one.  
![image](https://media.github.tools.sap/user/13842/files/ce1562b3-cd6d-4d08-92fe-f6d11abbc694)  

21. Provide following Queue Name: <b>ApprovedNewHire_PR_IN264-XXX</b> and press <b>Create</b>.  
> Replace XXX with the participant number provided by your instructor  

![image](https://media.github.tools.sap/user/13842/files/e234793c-176e-4162-bcbd-10eb002c35d4)  

22. Press "<b>Apply</b>  
![image](https://media.github.tools.sap/user/13842/files/159fc4f6-6ea7-4074-9652-02cd66ad1f16)  

23. Open the Queue just created (<b>ApprovedNewHire_PR_IN264-XXX</b>)  
![image](https://media.github.tools.sap/user/13842/files/ee5bbe87-5dc5-4dd7-9e30-9607d246cf3f)  

24. Navigate to "<b>Subscriptions</b> and press <b>"+ Subscription</b>  
![image](https://media.github.tools.sap/user/13842/files/76c1f433-7899-4368-bb29-88a4eba9814b)  

25. Provide following value: <b>SBPA/NewHire/IN264-XXX/Approval</b> and press <b>"Create"</b>  
> Replace XXX with the participant number provided by your instructor 
![image](https://media.github.tools.sap/user/13842/files/e794c143-8a04-4660-b95d-e08c735bf960)

## Summary

If you want some more information on the general concepts around **Event-Driven Architectures**, you can check [here](https://solace.com/what-is-event-driven-architecture/) for a brief introduction.

At the end of the first part of the tutorial, you should have configured and deployed an integration flow to send out the welcome email along with the Qualtrics survey link.

Continue to - Exercise 2 - Copy, configure and deploy the Equipment and Training Approval subscription flow


Navigate to - [Exercise overview page](/README.md#exercises)
