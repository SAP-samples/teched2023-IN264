# Exercise 6 - Add a New Employee in SAP SuccessFactors

In this exercise, we will be adding a new employee in the SAP SuccessFactors application.

Please do note that while the steps shown are comprehensive, due to time constraints on the session this process will be run by the instructor of the session for you, but this will match exactly with what is shown below.

## Exercise steps

Run through the following steps:

1. Logon to the SAP SuccessFactors with the SFSF Admin User ID.
<br><img src="/exercises/ex6/images/1. SFSF_Logon.png" width=60% height=60%>

2. Enter `Add New Employee` in the search field. This would bring us to the <b>Add New Employee Wizard</b>.
<br><img src="/exercises/ex6/images/2. SFSF_Admin.jpg" width=90% height=90%>

3. In the <b>Identity</b> section, details will vary by company, but we will enter the following critical employee information for our new employee:
      <ol type="i">
      <li><b>Hire Date:</b> Jan 30, 2023</li>
      <li><b>Company:</b> From the drop down list - BestRun (10000)</li>
      <li><b>Event Reason:</b> From the drop down list - New Hire (HIRNEW)</li>
      <li><b>First Name:</b> Jim</li>
      <li><b>Last Name:</b> Halpert</li>
      <li><b>Date Of Birth:</b> Oct 01, 1978</li>
      <li><b>Country Of Birth:</b> United States</li>
      <li><b>Person Id:</b> DCOM2023</li>
      <li><b>User Name:</b> DCOM2023</li>
      </ol>
      <br>Then we click <b>Continue</b> to continue the wizard.
      <br><img src="/exercises/ex6/images/3a. New Hire.PNG" width=90% height=90%>

4. In Personal Information section, enter details as given below:
      <ol type="i">
      <li><b>Gender:</b> Male</li>
      <li><b>Preferred Language:</b> From drop down list - English (US)</li>
      <li><b>Nationality:</b> From drop down list - United States</li>
      <li>Enter Email Information:</li>(You have overwritten this Email ID in the Integration Flow with your own Email Id)
            <ol type="a">
                  <li><b>Email Type:</b> Business</li>
                  <li><b>Email Address:</b> dcom_participant@sap.com</li>
                  <li><b>Is Primary:</b> From drop down list - Yes</li>
            </ol>
      </ol>
      <br>Then we click <b>Continue</b> to continue the wizard.
      <br><img src="/exercises/ex6/images/3b. New Hire.PNG" width=90% height=90%>

5. In Job Information section, enter details as given below:
      <ol type="i">
      <li><b>Select Position:</b> From drop down list - Inspector (It automatically fills all the other fields) </li>
      <li>In Organizational Information, No data for <b>Cost Center</b></li>
      </ol>
      <br><img src="/exercises/ex6/images/3d. New Hire.PNG" width=90% height=90%>

6. Scrolling down to the end of the page to Employment Details, because it would be cruel to make an employees first day be on Valentine's Day. Set the First Date Worked to February 15th, so they can attend this sesssion.
<br>Click <b>Continue</b> to move the wizard forward, and then click <b>Submit</b> to finalize the addition of the new Employee.
<br><img src="/exercises/ex3/ex6/images/3e. New Hire.PNG" width=90% height=90%>
<br><img src="/exercises/ex3/ex6/images/3e2. New Hire.PNG" width=90% height=90%>

7. When the employee has been added successfully the following screen appears.
<br><img src="/exercises/ex3/ex6/images/3f. New Hire.PNG" width=70% height=70%>

## Summary

You now have seen how the employee is added to the SuccessFactors system, which will trigger the event to <b>SAP Integration Suite, advanced event mesh</b> and eventually triggers your integration flows in <b>Cloud Integration</b> capability of SAP Integration Suite

Continue to - [Exercise 7 - Verify Scenario Success](/exercises/ex7/README.md)
