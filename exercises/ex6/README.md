# Exercise 6 - Add a New Employee in SAP SuccessFactors

In this exercise, you will be adding a new employee in the SAP SuccessFactors application.

## Exercise steps

Run through the following steps:

1. Logon to the SAP SuccessFactors using the user ID and password provided to you by the instructors.
<br><img src="/exercises/ex6/images/SAP_SFSF_Logon.png" width=60% height=60%>

2. Search for `Add New Employee` and select **Add New Employee** list entry and this would bring us to the **Add New Employee Wizard**.
<br><img src="/exercises/ex6/images/SFSF_Add_1.png" width=90% height=90%>

3. In the **Identity** section, enter the following details:
   > [!IMPORTANT]
   > Replace **XXX** with the participant number that is assigned to you.
      <ol type="i">
      <li><b>Hire Date:</b> Keep the default current date</li>
      <li><b>Company:</b> From the drop down list - BestRun (10000)</li>
      <li><b>Event Reason:</b> From the drop down list - New Hire (HIRNEW)</li>
      <li><b>First Name:</b> Any name of your choice</li>
      <li><b>Last Name:</b> Any name of your choice</li>
      <li><b>Date Of Birth:</b> Select any date, e.g.: Oct 18, 2000</li>
      <li><b>Country Of Birth:</b> Select any country, e.g.: India</li>
      <li><b>Person Id:</b> IN264_XXX</li>
      <li><b>User Name:</b> IN264_XXX</li>
      </ol>
      <br>Then we click <b>Continue</b> to continue the wizard.
      <br><img src="/exercises/ex6/images/SFSF_Add_2.png" width=90% height=90%>

4. In the **Personal Information** section, enter the following details:
      <ol type="i">
      <li><b>Gender:</b> Male</li>
      <li><b>Preferred Language:</b> From drop down list - English (US)</li>
      <li><b>Nationality:</b> From drop down list - United States</li>
      <li><b></b>Add the following Email Information:</li>
            <ol type="a">
                  <li><b>Email Type:</b> Business</li>
                  <li><b>Email Address:</b> Enter any Email ID that you can access to see the generated email as part of the employee onboarding subprocess in SAP SuccessFactors</li>
                  <li><b>Is Primary:</b> From drop down list - Yes</li>
            </ol>
      </ol>
      <br>Then we click <b>Continue</b> to continue the wizard.
      <br><img src="/exercises/ex6/images/SFSF_Add_3.png" width=90% height=90%>
      <br><img src="/exercises/ex6/images/SFSF_Add_4.png" width=90% height=90%>

5. In the **Job Information** section, enter the following details:
   > [!IMPORTANT]
   > You have the option to choose any available position, yet it's important to note that the SAP Build Process Automation (SBPA) employs equipment determination decisions specific to roles such as **Sales**, **Marketing**, **Analyst**, **Consulting**, and **Default**. Your selected role will dictate the equipment and training list displayed in the approval form.
      <ol type="i">
      <li><b>Select Position:</b> From drop down list - Select any available poistion (It usually automatically fills all the other fields) </li>
      </ol>
      <br><img src="/exercises/ex6/images/SFSF_Add_5.png" width=90% height=90%>

6. Scroll down, in **Employment Details**, set the **First Date Worked** as any date in the future.
   <br>Then we click <b>Continue</b> to continue the wizard.
   <br><img src="/exercises/ex6/images/SFSF_Add_6.png" width=100%>

7. As a final step to create a new employee, click on the **Submit** button.
   <br><img src="/exercises/ex6/images/SFSF_Add_Submit.png" width=90% height=90%>
   
8. When the employee has been added successfully the following screen appears.
<br><img src="/exercises/ex6/images/SFSF_Employee_Added.png" width=90% height=90%>

## Summary

You should have been able to onboard a new employee successfully in SAP SuccessFactors.
This will trigger an event to <b>SAP Integration Suite, advanced event mesh</b> that eventually triggers your integration flows in <b>Cloud Integration</b> capability of SAP Integration Suite.

Continue to - [Exercise 7 - Verify Scenario Success](/exercises/ex7/README.md)
