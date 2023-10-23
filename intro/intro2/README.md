# New Hire event configuration in SAP SuccessFactors (for your information only)

To enable the <b>New Hire</b> event in <b>SAP SuccessFactors(SFSF) Employee Central</b>, the following configuration steps has already been done for you. This section is for your information only. 

Run through the following steps in the given order and kindly do not touch or change any given configuration.

1. Go to <b>Integration Center</b> by searching it in the search field.
    <br><img src="/intro/intro2/images/Search_Integration_Center.png" width=90% height=90%>

2. Select <b>My Integrations</b> from the Integration Center landing page.
    <br><img src="/intro/intro2/images/Integration_Center.png" width=90% height=90%>

3. We have aready created an integration with the name <b>IN264 - Combine SAP Integration Suite and SAP Build in HR</b>.<br/>
In this we have defined the <b>New Hire</b> attributes and <b>REST Destination</b> to publish the new hire event data to <b>SAP Integration Suite, advanced event mesh</b> topic `SuccessFactors/NewHire/{EmployeeId}` where EmployeeId gets dynamically resolved from the new hire payload. Once it get published to the topic, any one can subscribe to the new hire event.
    <br><img src="/intro/intro2/images/Integration_Center_List.png" width=90% height=90%>

4. In the <b>Options</b> tab, we have provided the <b>Integration Name</b> and <b>Description</b>. Click <b>Next</b> to see the configured fields.
    <br><img src="/intro/intro2/images/IC_Options.png" width=90% height=90%>

5. In the <b>Configure Fields</b> tab, we have defined the <b>New Hire</b> attributes like employee name, position, manager name, etc. that is required for this scenario. As this event contains all the fields necessary for the scenario, we do not need to do a call back to get the newly hired details. We call this type of event as data event.<br/>
On the right side, you can also see the data preview. Click <b>Next</b> to see the response fields.
    <br><img src="/intro/intro2/images/IC_Configure_Fields.png" width=90% height=90%>

6. In the <b>Response Fields</b> tab, we can configure the fields for processing the REST response.<br/>
We have not configured any fields here as this is not required for this scenario. Click <b>Next</b> to see the filters.
    <br><img src="/intro/intro2/images/IC_Response_Fields.png" width=90% height=90%>

7. In the <b>Filter</b> tab, we can configure the advanced filter and sort options.<br/>
We have not defined any filters for this scenario, click <b>Next</b> to see the destination settings.
    <br><img src="/intro/intro2/images/IC_Filter.png" width=90% height=90%>

8. In the <b>Destination Settings</b> tab, we have defined the REST endpoint and Authentication details of <b>SAP Integration Suite, advanced event mesh</b> along with the topic name `SFSF/NewHire/{EmployeeId}`. EmployeeId gets dynamically resolved from the new hire payload using <b>Calculated URI</b> settings. The new hire event would get published to this topic only. <br/><br/>
This has been done so that new hire created by each participant would get published to their topic only and does not get broadcasted to all the participants. Click <b>Calculated URI</b> to check the settings.
    <br><img src="/intro/intro2/images/IC_Destination_Settings.png" width=90% height=90%>

9. In the <b>Calculated URI</b> section, we have defined <b>User ID i.e., EmployeeId </b>. This would get appended to the REST endpoint as defined in the Destination. Click <b>Ok</b> to close it.
    <br><img src="/intro/intro2/images/IC_Destination_Settings_Calculated_URI.png" width=90% height=90%>

10. Click <b>Next</b> to review and run the integration.
    <br><img src="/intro/intro2/images/IC_Destination_Settings2.png" width=90% height=90%>
    
11. In the <b>Review and Run</b> tab, we can review the settings of the integration before committing it.</br>
After the review, save it to deploy it to the server.
    <br><img src="/intro/intro2/images/IC_Review_and_Run.png" width=90% height=90%>
    <br><br><img src="/intro/intro2/images/IC_Save_Deploy.png" width=90% height=90%>

12. Go to <b>Intelligent Service Center(ISC)</b>, where you can configure this integration against the <b>Employee Hire</b> event.
    <br><img src="/intro/intro2/images/IC_Goto_ISC.png" width=90% height=90%>
    
13. In the <b>Integration Services Center</b>, we have configured the <b>IN264 - Combine SAP Integration Suite and SAP Build in HR</b> integration against the <b>Employee Hire</b> event along with the given rule.
    <br><img src="/intro/intro2/images/Integration_Services_Center.png" width=90% height=90%>   
    <br><img src="/intro/intro2/images/Integration_Services_Center_Rule.png" width=90% height=90%>    
    
## Summary

You should now be familiar with all the configurations that has been done in **SAP SuccessFactors** to enable the new hire event publication to <b>SAP Integration Suite, advanced event mesh</b>.

Now, to learn more about the configuration that has been done in <b>SAP S/4Hana Cloud System</b>, you can navigate to [SAP S/4Hana Cloud System configuration](/intro/intro3/README.md) section.
