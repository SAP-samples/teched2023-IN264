# Exercise 1 - Create queues and subscribe to topic in SAP Integration Suite, advanced event mesh

## Overview

To enable the event-driven architecture in this integration scenario, we use **SAP Integration Suite, advanced event mesh (AEM)**.<br/>
In this exercise, each participant has to create 3 queues and subscribe to the relevant topic.
These queues are then required and subscribed in the later part of the session while configuring or creating the integration interfaces in the Cloud Integration capability of SAP Integration Suite.

## Exercise steps
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
7. From these connectivity option, <b>AMQP</b> connectivity details will be used by the Integration Flows in Cloud Intgeration capability of SAP Integration Suite to subscribe to AEM Queues. 
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
      - Topic Subscription: **SBPA/NewHire/IN264-XXX/Approval**
   
   Click <b>"+ Queue"</b> button on the top right area to create a first queue.
   <br><img src="/exercises/ex1/images/AEM_Manage_1_Queue.png" width=90% height=90%> 	

10. Enter the following Queue Name and click the <b>"Create"</b> button:
    - <b>NewHire_Workflow_IN264-XXX</b>, kindly replace **XXX** with the participant number that is assigned to you.
    <br><img src="/exercises/ex1/images/AEM_Create_1_Queue.png" width=90% height=90%> 

11. Keep the default configuration and click the <b>"Apply"</b> button.
<br><img src="/exercises/ex1/images/AEM_Apply_1_Queue.png" width=90% height=90%>

12. Select the Queue thay you have just created i.e., <b>NewHire_Workflow_IN264-XXX</b> 
<br><img src="/exercises/ex1/images/AEM_Select_1_Queue.png" width=90% height=90%>

13. Navigate to <b>"Subscriptions"</b> tab and click <b>"+ Subscription"</b> button on the top right area to create a new topic subscription.
<br><img src="/exercises/ex1/images/AEM_1_Queue_Topic_Subscription.png" width=90% height=90%>

14. Enter the following topic value and click the <b>"Create"</b> button:
    - <b>SFSF/NewHire/IN264-XXX</b>, kindly replace **XXX** with the participant number that is assigned to you.
    <br><img src="/exercises/ex1/images/AEM_1_Queue_Topic_Subscription_Create.png" width=90% height=90%> 

15. Naviagte back to Queues.  
<br><img src="/exercises/ex1/images/AEM_Navigate_Back_Queues_1.png" width=90% height=90%> 

16. Click <b>"+ Queue"</b> button on the top right area to create a second queue.
<br><img src="/exercises/ex1/images/AEM_Manage_2_Queue.png" width=90% height=90%>  

17. Enter the following Queue Name and click the <b>"Create"</b> button:
    - <b>NewHire_SurveyEmail_IN264-XXX</b>, kindly replace **XXX** with the participant number that is assigned to you.
    <br><img src="/exercises/ex1/images/AEM_Create_2_Queue.png" width=90% height=90%> 

18. Keep the default configuration and click the <b>"Apply"</b> button.
<br><img src="/exercises/ex1/images/AEM_Apply_2_Queue.png" width=90% height=90%>

19. Select the Queue thay you have just created i.e., <b>NewHire_SurveyEmail_IN264-XXX</b> 
<br><img src="/exercises/ex1/images/AEM_Select_2_Queue.png" width=90% height=90%>

20. Navigate to <b>"Subscriptions"</b> tab and click <b>"+ Subscription"</b> button on the top right area to create a new topic subscription.
<br><img src="/exercises/ex1/images/AEM_2_Queue_Topic_Subscription.png" width=90% height=90%>

21. Enter the following topic value and click the <b>"Create"</b> button:
    - <b>SFSF/NewHire/IN264-XXX</b>, kindly replace **XXX** with the participant number that is assigned to you.
    <br><img src="/exercises/ex1/images/AEM_1_Queue_Topic_Subscription_Create.png" width=90% height=90%> 

22.  Naviagte back to Queues.  
<br><img src="/exercises/ex1/images/AEM_Navigate_Back_Queues_2.png" width=90% height=90%>

23. Click <b>"+ Queue"</b> button on the top right area to create a second queue.
<br><img src="/exercises/ex1/images/AEM_Manage_3_Queue.png" width=90% height=90%>    

24. Enter the following Queue Name and click the <b>"Create"</b> button:
    - <b>ApprovedNewHire_PR_IN264-XXX</b>, kindly replace **XXX** with the participant number that is assigned to you.
    <br><img src="/exercises/ex1/images/AEM_Create_3_Queue.png" width=90% height=90%>

25. Keep the default configuration and click the <b>"Apply"</b> button.
<br><img src="/exercises/ex1/images/AEM_Apply_3_Queue.png" width=90% height=90%>

26. Select the Queue thay you have just created i.e., <b>ApprovedNewHire_PR_IN264-XXX</b> 
<br><img src="/exercises/ex1/images/AEM_Select_3_Queue.png" width=90% height=90%>

27. Navigate to <b>"Subscriptions"</b> tab and click <b>"+ Subscription"</b> button on the top right area to create a new topic subscription.
<br><img src="/exercises/ex1/images/AEM_3_Queue_Topic_Subscription.png" width=90% height=90%>

28. Enter the following topic value and click the <b>"Create"</b> button:
    - <b>SBPA/NewHire/IN264-XXX/Approval</b>, kindly replace **XXX** with the participant number that is assigned to you.
    <br><img src="/exercises/ex1/images/AEM_3_Queue_Topic_Subscription_Create.png" width=90% height=90%> 

29. Naviagte back to Queues.  
<br><img src="/exercises/ex1/images/AEM_Navigate_Back_Queues_3.png" width=90% height=90%>

## Summary

At the end of the first part of the session, you should have created 3 queues and subscribed to the relevant topic. 
<br/>Please make sure that you have used the right nomenclature and replaced **XXX** with the participant number that is assigned to you.

Continue to - [Exercise 2 -](/exercises/ex2/README.md)
