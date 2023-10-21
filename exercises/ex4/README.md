# Exercise 4 - Copy, configure and deploy the Survey Email subscription flow

In this exercise, you will setup an integration flow that listens to the SAP Integration Suite, advanced event mesh queue. This queue is subscribed to the topic where SAP SuccessFactors publishes new hire events. This integration triggers a real-time welcome email, along with a survey link, upon adding a new hire in SAP SuccessFactors.

## Exercise steps

Run through the exercise steps in the given order.

### Copy the integration flow template
1. Open the [solution package](https://in264-72e8h9xc.integrationsuite.cfapps.eu10-002.hana.ondemand.com/shell/design/contentpackage/IN264CombineSAPIntegrationSuiteandSAPBuildProcessAutomationinHR?section=ARTIFACTS) in Cloud Integration capability of SAP Integration Suite and log in using the user ID and password provided to you by the instructors.
<br><img src="/exercises/ex4/images/CI_Solution_Package.png" width=90% height=90%> 	

2. Search for the **SAP SFSF New Hire Welcome Email with Survey Link** integration flow and from the **Actions** menu, select the menu entry **Copy**
<br><img src="/exercises/ex4/images/CI_SM_Copy_1.png" width=90% height=90%> 	

3. In the **Copy** dialog, update the name of the integration flow to **SAP SFSF New Hire Welcome Email with Survey Link - IN264-XXX**
   > [!IMPORTANT]  
   > Replace **XXX** with the participant number that is assigned to you.
<img src="/exercises/ex4/images/CI_SM_Copy_2.png" width=90% height=90%>
     
4. Press **Select** to choose another package as destination.
<br/>As the target package, choose the the package that you had created in [exercise 3](../ex3/README.md) i.e. **"Combine SAP Integration Suite and SAP Build Process Automation in HR_IN264-XXX"** to ensure that the integration flow is copied into your package.
 > [!IMPORTANT]  
 > Replace **XXX** with the participant number that is assigned to you.
<img src="/exercises/ex4/images/CI_SM_Copy_3.png" width=90% height=90%>

5. When done, select the *Copy* button to copy the Integration Flow into your package.
<img src="/exercises/ex4/images/CI_SM_Copy_4.png" width=90% height=90%>

6. After the integration flow has been copied, you are asked to navigate to your package. Confirm by selecting button *Navigate*
<img src="/exercises/ex4/images/CI_SM_Navigate.png" width=90% height=90%>

### Configure and deploy the integration flow
1. After having copied the integration flow template, you should see one integration flow in your package. From the *Actions* menu of your integration flow, select the menu entry <b>Configure</b>
<br>![Script collection](/exercises/ex1/images/01-0010.png)

2. In the upcoming dialog, maintain the Queue name **HO010_XX_Email**, replacing **XX** with the participant number assigned to you.
<br>![Script collection](/exercises/ex1/images/01-0011.png)
    
3. Switch to the <b>Receiver</b> Tab in the same dialog and replace **New Hire EMail ID** with your own Email ID where you can login and check the emails. This has been done to overwrite the email id of the newly hired candidate so that each one of you can get the welcome email on your own configured email id. 
<br>Then select *Save*, in case of any warning just ignore it. Once saved, select *Deploy*
<br><img src="/exercises/ex1/images/01-0012.png" width=80%>
    
4. Close the next dialog if the warning message is shown. Then click on **Yes** to deploy and close the confirmation dialog.
<br>![Script collection](/exercises/ex1/images/01-0013-warning.png)
<br>![Script collection](/exercises/ex1/images/01-0014_2.png)
<br>![Script collection](/exercises/ex1/images/01-0014.png)

### Check the deployment status
1. From the navigation pane on the left side, switch to the *Monitor --> Integrations* area
<br><img src="/exercises/ex1/images/01-0015.png" width=40% height=40%>

2. In the Monitor overview, select the first tile below the *Manage Integration Content* section
<br><img src="/exercises/ex1/images/01-0016.png" width=60% height=60%>

3. Search for your integration flow - <b>SAP SFSF New Hire Welcome Email along with Qualtrics Survey Link_XX</b>, replacing <b>XX</b> with the participant number assigned to you. Check and confirm that the status has turned to **Started**
<br>![Design menu](/exercises/ex1/images/01-0017.png)

## Summary

At the end of this exercise, you should have configured and deployed an integration flow to send out the welcome email along with the survey link.

Continue to - [Exercise 5 - Copy, configure and deploy the SAP S/4Hana Purchase Requsition subscription flow](/exercises/ex5/README.md)
