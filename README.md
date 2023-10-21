[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2023-IN264)](https://api.reuse.software/info/github.com/SAP-samples/teched2023-IN264)

# IN264 - Combine SAP Integration Suite and SAP Build Process Automation in HR


## Description

This repository contains the material for the SAP TechEd 2023 hands-on session called **IN264 - Combine SAP Integration Suite and SAP Build Process Automation in HR**

The **Onboarding** process is a crucial and very common activity of **Human Resource** department of any organization, influencing the experience and success of new hires. Organisations often face challenges in onboarding process especially with equipments and trainings that are required by the new-hire. If these not done right, the onboarding process can involve manual and repetitive tasks, leading to inefficiencies and delays. A solution is needed that enables seamless event-driven integration, process automation and customization to provide a personalized onboarding experience for new hires.

## Overview

SAP Integration Suite & SAP Build can support our customers today by quickly identifying, vetting and automating as many processes as possible.
Let us implement and learn how to improve the new hire experience with enterprise automation solutions from SAP. While you manage employee onboarding with SAP SuccessFactors solution, use the Advance Event Mesh capability within SAP Integration Suite to trigger real-time event-driven business process integrations. One of these involves starting an approval workflow process using the SAP Build Process Automation solution, ensuring you involve the relevant stakeholders in certain scenarios. Let us experience the combination of integration and automation in this HR scenario.

By leveraging event-based integration patterns and low-code/no-code process automation, organizations can :
- extend and customize the onboarding experience,
- integrate with third-party tools,
- react and respond to events in real time using event-driven integration pattern,
- automate activities, and
- streamline shared-service processes.

Check out the following chapters to understand and achieve the end-to-end employee onboarding business subprocess as documented in this session:

- [Scenario Introduction](intro/intro1)
- [New hire event configuration in SAP SuccessFactors (for your information only)](intro/intro2)
- [SAP S/4Hana Cloud System configuration (for your information only)](intro/intro3)

## Requirements

There are no dedicated requirement for this session. You would be able to execute the excercises by just following the descriptions even if you do not have any experience with SAP Integration Suite and SAP Build Process Automation. <br/>
However, you will be able to derive more value from this session, if you have some knowledge and understanding of event-driven architectures, namely events, queues, topics, event subscriptions along with SAP Integration Suite and SAP Build Process Automation.<br/>

You can check out the following SAP Discovery Center missions that will help you in getting started with SAP Integration Suite, SAP Build Proces Automation and SAP Integration Suite, advanced event mesh 

* [SAP Integration Suite](https://discovery-center.cloud.sap/serviceCatalog/integration-suite)
* [SAP Build Process Automation](https://discovery-center.cloud.sap/serviceCatalog/sap-build-process-automation)
* [SAP Integration Suite, advanced event mesh](https://discovery-center.cloud.sap/serviceCatalog/advanced-event-mesh)
  
You can also gain some further knowledge around SAP Integration Suite, SAP Build and SAP Integration Suite, advanced event mesh by attending the following SAP TechEd sessions:
- Learn about Edge Integration cell, the next-generation hybrid integration runtime offered with SAP Integration Suite in [IN160 - Discover next-generation hybrid integrations with Edge Integration Cell](https://github.com/SAP-samples/teched2023-IN160)
- Take a deep dive into SAP Integration Suite, advanced event mesh in [IN265 - Event-Driven Architecture with SAP Integration Suite, Advanced Event Mesh](https://github.com/SAP-samples/teched2023-IN265)
- Learn how to build a application, automate process and connect with CAP services in [AD272 - SAP Cloud Application Programming Model Meets SAP Build](https://github.com/SAP-samples/teched2023-AD272)
- Learn how to build and extend standard business process in SAP S/4HANA [AD163 - Extend Your Sales Order Process in SAP S/4HANA with SAP Build](https://github.com/SAP-samples/teched2023-AD163)

## System URL and login information

For running through the exercises, you need access to the following applications:
- [SAP SuccessFactors system](https://pmsalesdemo8.successfactors.com/login?company=SFPART069417)
- [SAP S/4Hana Cloud system](https://my407161.s4hana.cloud.sap/ui)
- [SAP Integration Suite, advanced event mesh tenant](https://eu10.console.pubsub.em.services.cloud.sap/login?tenant-id=75520573-e903-4c94-855b-49f03d179a95)
- [SAP Integration Suite tenant](https://in264-72e8h9xc.integrationsuite.cfapps.eu10-002.hana.ondemand.com/shell/home) or [SAP Integration Suite backup tenant](https://teched23blr03.integrationsuite.cfapps.ap11.hana.ondemand.com/shell/home)
- [SAP Build Process Automation - Lobby](https://in264-72e8h9xc.eu10.build.cloud.sap/lobby)
- [SAP Build Process Automation - My Inbox](https://in264-72e8h9xc.sap-process-automation.cfapps.eu10.hana.ondemand.com/comsapspaprocessautomation.comsapspainbox/inbox.html)


> [!IMPORTANT]
> - We have done everything to make this experience enjoyable. Your tenants are pre-configured and you already have all the roles and definitions you need to complete this exercise.
> - User ID and password information will be provided to you by the instructors.
> - When you run through the exercise steps, you need to ensure that the technical IDs of the integration artifacts that you will create are unique. Hence, add a participant number to your integration artifacts. The instructors will assign the participant number to you.
> - Please adhere strictly to the instructions regarding the naming conventions for the artifacts you create. This will ensure successful completion of the tasks without conflicting with other participants.
> - Do not delete, change or undeploy any artifact in the tenant other than yours.

## Exercises

The complete list of exercise steps are listed below, run through them in the given order.
<br>You can use this section as a Table of Contents. Use the breadcrumb navigation on top of the pages to go back to the Table of Contents.

- [Exercise 1 - Create queues and subscribe to topic in SAP Integration Suite, advanced event mesh](exercises/ex1/README.md)
- [Exercise 2 - SAP Build Process Automation](exercises/ex2/README.md)        
- [Exercise 3 - Create the subscription flow that triggers the SAP Build Process Automation (SBPA) equipment and training approval workflow](exercises/ex3/README.md)
- [Exercise 4 - Copy, configure and deploy the Survey Email subscription flow](exercises/ex4/README.md)
- [Exercise 5 - Copy, configure and deploy the SAP S/4Hana Purchase Requsition subscription flow](exercises/ex5/README.md)
- [Exercise 6 - Add a New Employee in SAP SuccessFactors](exercises/ex6/README.md)
- [Exercise 7 - Verify Scenario Success](exercises/ex7/README.md)
    - [Check the Cloud Integration Monitoring](/exercises/ex7/ex71)
    - [Check your Email Inbox and Click through Survey](/exercises/ex7/ex72)
    - [Approve the new hire in SAP Build Process Automation Inbox](/exercises/ex7/ex73)
    - [Check your Email and navigate to the created Purchase Requisition in SAP S/4Hana Cloud system](/exercises/ex7/ex74)
  
## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2023 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
