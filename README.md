[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2023-IN264)](https://api.reuse.software/info/github.com/SAP-samples/teched2023-IN264)

# IN264 - Combine SAP Integration Suite and SAP Build Process Automation in HR


## Description

This repository contains the material for the SAP TechEd 2023 session called **IN264 - Combine SAP Integration Suite and SAP Build Process Automation in HR**

The **Onboarding** process is a crucial abd very common activity of **Human Resource** department of any organization, influencing the experience and success of new hires. Organisations often face challenges in onboarding process especially with new trainings and system accesses that are required by the new-hire. If these not done right, the onboarding process can involve manual and repetitive tasks, leading to inefficiencies and delays. A solution is needed that enables seamless integration, process automation and customization to provide a personalized onboarding experience for new hires.

## Overview

This session introduces attendees how to combine **SAP Integration Suite** and **SAP Build Process Automation** to design a comprehensive solution to address the challenges in the onboarding process. By leveraging event-based integration patterns and low-code/no-code process automation organizations can :
- extend and customize the onboarding experience,
- integrate with third-party tools,
- automate activities and
- streamline shared-service processes.

<img width="1164" alt="image" src="https://github.com/SAP-samples/teched2023-IN264/assets/34297037/ae6a7241-4edd-4455-9a15-95016639aa49">


<br>In this scenario: <br>
- A new hire is created in SAP SuccessFactors
- Advanced Event Mesh is configured to subscribe to the SuccessFactors Event.
- Process is triggered to assign trainings and equipment to new hire using SAP Build Process Automation
- Integration flows are called from the process to create purchase orders in the backend S/4HANA cloud
- SAP Work Zone workspace is used to provide centralized access to S/4HANA applications, workflow inbox applications and for notifications
- In addition, whole process can be managed and monitored using out-of-the-box visibility.


## Requirements

There are no dedicated requirement for this exercise. But in case you want to gain some further knowledge around SAP Build, please feel free to attend these SAP TechEd workshops:
- Learn how to build a application, automate process and connect with CAP services in [AD272 - SAP Cloud Application Programming Model Meets SAP Build](https://github.com/SAP-samples/teched2023-AD272)
- Learn how to build and extend standard business process in SAP S/4HANA [AD163 - Extend Your Sales Order Process in SAP S/4HANA with SAP Build](https://github.com/SAP-samples/teched2023-AD163)

## Exercises


- [Exercise 1 - SAP Integration Suite](exercises/ex1/)
    - [Exercise 1.1 - Exercise 1 Sub Exercise 1 Description](exercises/ex1#exercise-11-sub-exercise-1-description)
    - [Exercise 1.2 - Exercise 1 Sub Exercise 2 Description](exercises/ex1#exercise-12-sub-exercise-2-description)
- [Exercise 2 - SAP Build Process Automation](exercises/ex2/)
        <br>Save the employee onboarding sample content as new project
         <br>Add parallel Gateway to add new Training rule
         <br>Edit Equipment Determination Rule
         <br>Edit Forms to add Equipment Table
         <br>Add Action for CAP Service
         <br>Release and Deploy
         <br>Run the Process 
    - [Exercise 2.1 - Create business project and process](exercises/ex2#exercise-21-sub-exercise-1-description)
   - - [Exercise 2.2.1 - Add API Trigger](exercises/ex2#exercise-22-sub-exercise-2-description)
    - - [Exercise 2.2.2 - Add Decision to Determine Trainings](exercises/ex2#exercise-22-sub-exercise-2-description)
    - - [Exercise 2.2.3 - Add Approver Form](exercises/ex2#exercise-22-sub-exercise-2-description)
    - [Exercise 2.3 - Add Condition](exercises/ex2#exercise-22-sub-exercise-2-description)
    - [Exercise 2.4 - Add Action to Create Purchase Order](exercises/ex2#exercise-22-sub-exercise-2-description)
    - [Exercise 2.5 - Send Email Notification](exercises/ex2#exercise-22-sub-exercise-2-description)

  
## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2023 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
