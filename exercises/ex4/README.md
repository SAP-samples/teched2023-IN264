# Exercise 4 - Copy, configure and deploy the Welcome Email subscription flow

In the first part of the exercise, you will setup an integration flow that listens to the Advanced Event Mesh queue that is subscribed to the topic `SuccessFactors/NewHire` exposed by SAP SuccessFactors. This triggers a welcome email along with the Qualtrics survey link in real-time once the new hire gets created in SAP SuccessFactors.

## Exercise steps

Run through the exercise steps in the given order.

### Copy the integration flow template
1. Open the SAP Integration Suite tenant that is assigned to you and logon with the user userXX and the password provided to you. Replace XX with the participant number that is assigned to you.
   
2. Expand the Navigation pane and switch to the *Design --> Integrations* area
<br><img src="/exercises/ex1/images/01-0001.png" width=50%>

3. Use _Filter_ with **SOLUTION** to find  the package **D-Com 2023 HO010 - SOLUTION**, click and navigate to the <b>Artifacts</b> tab.
<br>![Maintain package name](/exercises/ex2/images/02-0001.png)

4. From the *Actions* menu of the **SAP SFSF New Hire Welcome Email along with Qualtrics Survey Link**, select the menu entry *Copy*
<br>![Copy](/exercises/ex1/images/01-0007.png)

5. In the upcoming dialog, add the participant number assigned to you to the **name** of the copied integration flow. Update the name of the integration flow to **SAP SFSF New Hire Welcome Email along with Qualtrics Survey Link_XX**, replacing **XX** with the participant number assigned to you.

6. **Important**: As the target package, select your beforehand created package to ensure that the integration flow is copied into your package
   
7. When done, select the *Copy* button
<br>![Maintain name and target](/exercises/ex1/images/01-0008.png)

8. After the integration flow has been copied, you are asked to navigate to your package. Confirm by selecting button *Navigate*
<br>![Navigate to your package](/exercises/ex1/images/01-0009.png)

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
