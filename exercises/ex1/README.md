# Exercise 1 - Create queues and subscribe to topic in SAP Intgration Suite, advanced event mesh

## Overview

To enable the event-driven architecture in this integration scenario, we use **SAP Integration Suite, advanced event mesh (AEM)**.<br/>
In this exercise, each participant has to create 3 queues and subscribe to the relevant topic.
These queues are then required and subscribed in the later part of the session while configuring or creating the integration interfaces in the Cloud Integration capability of SAP Integration Suite.
<br/><br/>
Run through the following steps in the given order:

1. Open the [SAP Integration Suite, advanced event mesh](https://eu10.console.pubsub.em.services.cloud.sap/login?tenant-id=75520573-e903-4c94-855b-49f03d179a95) tenant and log in using the user ID and password provided to you by the instructors.
<br><img src="/exercises/ex1/images/AEM_Login.png" width=50% height=50%> 	
   
2. Open the <b>"Cluster Manager"</b> tile.
<br><img src="/exercises/ex1/images/AEM_Cluster_Manager.png" width=90% height=90%> 	

3. Deselect <b>"Only show my services"</b> checkbox.
<br><img src="/exercises/ex1/images/AEM_Services.png" width=90% height=90%> 	

4. Click on the <b>"IN264_Teched"</b> tile.
<br><img src="/exercises/ex1/images/AEM_IN264_Teched.png" width=90% height=90%>

> [!NOTE]  
> Only for Information! <br/>
5. Navigate to the <b>"Connect"</b> tab. This tab provides the various conectivity protcol options.
<br><img src="/exercises/ex1/images/AEM_Connect.png" width=90% height=90%>

> [!NOTE]  
> Only for Information! <br/>
6. From these connectivity option, <b>REST</b> connectivity details is used by SAP SuccessFactors to send events to AEM. You can get more information about the SFSF configurations [here](../../intro/intro2/README.md). 
<br><img src="/exercises/ex1/images/AEM_Connect_REST.png" width=90% height=90%>

> [!NOTE]  
> Only for Information! <br/>
7. From these connectivity option, <b>AMQP</b> connectivity details are used by the Integration Flows in Cloud Intgeration capability of SAP Integration Suite to subscribe to AEM Queues. 
<br><img src="/exercises/ex1/images/AEM_Connect_AMQP.png" width=90% height=90%>

8. Navigate to the <b>"Manage"</b> tab, and click on <b>"Queues"</b> tile.
<br><img src="/exercises/ex1/images/AEM_Manage.png" width=90% height=90%> 	

9. A new tab will be open and list all the Queues. <br/>
As mentioned earlier, each participant has to create the following 3 queues and subscribe to the relevant topic.
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
   - First Queue: **NewHire_Workflow_IN264-XXX**
      - Topic Subscription: **SFSF/NewHire/IN264-XXX**
   - Second Queue: **NewHire_SurveyEmail_IN264-XXX**
      - Topic Subscription: **SFSF/NewHire/IN264-XXX**
   - Third Queue: **ApprovedNewHire_PR_IN264-XXX**
      - Topic Subscription: **SFSF/NewHire/IN264-XXX**
   
   Click <b>"+ Queue"</b> button on the top right area to create a new queue.
   <br><img src="/exercises/ex1/images/AEM_Manage_Queue.png" width=90% height=90%> 	

10. Enter the following Queue Name and click the <b>"Create"</b> button:
    - <b>NewHire_Workflow_IN264-XXX</b>, kindly replace **XXX** with the participant number that is assigned to you.
    <br><img src="/exercises/ex1/images/AEM_Create_1_Queue.png" width=90% height=90%> 

11. Keep the default configuration and click the <b>"Apply"</b> button.
<br><img src="/exercises/ex1/images/AEM_Apply_1_Queue.png" width=90% height=90%>

12. Select the Queue thay you have just created i.e., <b>NewHire_Workflow_IN264-XXX</b> 
<br><img src="/exercises/ex1/images/AEM_Select_1_Queue.png" width=90% height=90%>

13. Navigate to <b>"Subscriptions"</b> tab and click <b>"+ Subscription</b> button on the top right area to create a new topic subscription.
<br><img src="/exercises/ex1/images/AEM_1_Queue_Topic_Subscription.png" width=90% height=90%>

14. Enter the following topic value and click the <b>"Create"</b> button:
    - <b>SFSF/NewHire/IN264-XXX</b>, kindly replace **XXX** with the participant number that is assigned to you.
    <br><img src="/exercises/ex1/images/AEM_1_Queue_Topic_Subscription_Create.png" width=90% height=90%> 

15. Naviagte back to Queues.  
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
