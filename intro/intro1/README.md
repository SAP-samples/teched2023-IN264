
# Scenario Introduction

This session scenario helps you to learn event-driven integration pattern along with the exactly-once(EO) quality of service using SAP Integration Suite and Confluent Kafka.

In this, we implement an end-to-end [Recruit-to-Retire (R2R)](https://help.sap.com/docs/R2R/a4ca0ba232014b139a05f79d14732864/8665f29aafbc4be4b27511c18ecc0e0f.html) business process across a heterogeneous and hybrid landscape i.e. SAP SuccessFactors, Confluent Kafka, Email and SAP Build Process Automation.

## Business Scenario

Presume in your organization, you are using SAP SuccessFactors as a central Human Capital Management (HCM) application and you like to automate few aspects of newly hired employee in real-time like:

1. You like to send a welcome email to the newly hired candidate along with the qualtrics survey link to understand the candidate's onboarding experience.
	
2. You would also like to initiate the newly hired candidate's equipment and training approval workflow to the manager using the SAP Build Process Automation.
	
Instead of developing point-to-point integration for the above two use cases, you will learn and understand how we can achieve the same via event-driven integration pattern along with the exactly-once quality of service.

## Scenario Architecture

<img src="/intro/intro1/images/scenario_architecture.png" width=100% height=100%>

1. As and when you add a new employee in SAP SuccessFactors, 
	  <br> 1a. It will publishes an event with the required payload to Cloud Integration REST interface.
	  <br> 1b. Cloud Integration then publishes the same new hire event payload to Confluent Kafka topic using the Kafka receiver adapter.
   <br><br>
   
2. First subscriber subscribes to the same Confluent Kafka topic using the Cloud Integration Kafka sender adapter.
	  <br> 2a. It then sends a welcome email to the newly hired candidate's email id along with the qualtrics survey link using the Cloud Integration Mail receiver adapter.
	  <br> 2b. By clicking the qualtrics survey link, candidate provides the onboarding experience feedback.
	  <br><br>
   
3. Second subscriber subscribes to the same Confluent Kafka topic using the Cloud Integration Kafka sender adapter along with the Idempotent process call to achieve the exactly-once quality of service that handles the duplicate events.
	  <br> 3a. It will trigger the equipment and training approval workflow in SAP Build Process Automation and assign the task to the manager on the given manager's email id using the Cloud Integration HTTPS receiver adapter. This will be visible in the Task Center(one inbox).
   <br> 3b. On approval or rejection, workflow notify the newly hired candidate on the given candidate's email id.
    <br><br>
  
### Exactly-Once(EO) Handling
On publishing an event with the same new hire payload again, the first subscriber sends the duplicate welcome email to the newly hired candidate's email id as exactly-once handling is not done in the integration flow.<br> Whereas the second subscriber does not trigger the equipment and training approval workflow in SAP Build Process Automation as exactly-once handling is done using the Idempotent process call in the integration flow.

## Summary

You should now be familiar with the scenario.

Now, we show what all configurations has been done in SAP SuccessFactors to enable new hire events publication to Cloud Integration. Continue to - [SAP SuccessFactors Configuration](/intro/intro2)
