## Introduction

The software we are developping is for bank management. I will allow users to manage their bank accounts through a web application. They will be able to create a bank account, edit their account info (country), track balances, etc.. The software will have a frontend, where the user can interact with the account data trhough a home page when accesing the root URL and a bakcend with an API to access the database.   


## Assumptions and Constrains

### Assumptions

- Availability to Azure as the hosting service and including its services like App Service and PostgreSQL Database
- Flask will be used for the backend 
- Vue.js will be used for the frontent 
- When accesing the homepage it would be used through a web browser
- The development team will hvae the necessary skills with Github workflows, Node.js and Python 
- The business team will the database updated with the right information and in a timely manner


### Constraints

- All the environments must use Azure and its services
- We must use Github workflows and branching strategy
- The project must stay within the budget given by IT
- Used programming languages are Js and Python 
- We must comply with the Data Protection laws and the with online banking EU laws 


## General System Description

### System Context

There are 4 components: 
- Frontend: Handles user interactions and displays the bank account management interface.
- Backend: Handles business logic and interacts sith the database. 
- Database: Stores the user data, bank accounts and transactions.
- Infrasturcture: Handles Cloud ressources and the deployment on Azure.

### Infrastructure Architecture design 




TODO: Draw a diagram that depicts the infrastructure architecture design of the system for each environment. Below, provide a description of all the necessary components, include a description of the configuration that will be enabled for each infrastructure component.

Reference links:
- Basic web application: https://learn.microsoft.com/en-us/azure/architecture/web-apps/app-service/architectures/basic-web-app
- Scalable web and mobile applications using Azure Database for PostgreSQL: https://learn.microsoft.com/en-us/azure/architecture/solution-ideas/articles/scalable-web-and-mobile-applications-using-azure-database-for-postgresql
- Azure Well-Architected Framework perspective on Azure App Service (Web Apps): https://learn.microsoft.com/en-us/azure/well-architected/service-guides/app-service-web-apps
- Azure Well-Architected Framework review - Azure Database for PostgreSQL: https://learn.microsoft.com/en-us/azure/well-architected/service-guides/postgresql
- Azure App Service: https://learn.microsoft.com/en-us/azure/app-service/overview
- Azure Database for PostgreSQL: https://learn.microsoft.com/en-us/azure/postgresql/flexible-server/service-overview

### Environments design 

- Local development environment: this is where we will implement, debug and test our apllication on our local machine. It is composed of the fronted (running vue.js), the backend (Flask API running), the databse (SQLite, lightweight database) and VScode. 
- Cloude development environment: we test the app in near production environment. We can catch the deployment issues early before actual release. It is composed of the frontend (Azure App Service), the backend (Flask API running), the database (Azure PostgreSQL) and the CI/CD Pipeline (automatically deploy code to this env). 
- User acceptance test environment: this is where the client and end-users do the final test of the app before deployed into production. It is as close to the actual poduct we are going to launch. It is composed of frontend, backend, database. 

### Release strategy

We will used GitHub Flow with feature branches fro development and pull request for code review. Code merged into "main" will be automatically deployed into the UAT environment. Development commits will trigger deployment into the Developpement environment. Only after passin through UAT, we will release to production. 

## Functional requirements
1- The system shall display a homepage when users access the root URL (/).
2- The system shall allow users to create a bank account.
3- The system shall allow users to input the following details during account creation: Name, Country and Account balance
4- The system shall store the account details in a PostgreSQL database.
5- The system shall allow users to view a list of their bank accounts.
6- The system shall validate user inputs, such as ensuring no fields are left empty.
7- The system shall provide a REST API for account creation.
8- The system shall allow users to delete a bank account.
9- The system shall implement API error handling, including validation errors and database connection issues.
10- The system shall allow users to update account information.
11- The system shall log all user actions in the backend for auditing purposes.
12- The system shall display appropriate messages on account creation success or failure.
13-The system shall have input validation for the country field, ensuring it accepts only valid country names.
14- The system shall allow users to query accounts by country.
15- The system shall integrate with Azure Application Insights for monitoring.
16- The system shall ensure that deployments to UAT use the same configuration as the production environment.
17- The system shall handle 404 errors and display user-friendly error pages.
18-The system shall support internationalization for the frontend (future feature).
19-The system shall encrypt sensitive data such as passwords.
20- The system shall handle user authentication and authorization (future feature).

## Non-functional requirements

### Security

TODO: describe 5 non functional requirements for application system security controls applied for each environment;

Reference links:
- Azure App Service: https://learn.microsoft.com/en-us/azure/app-service/overview-security
- Azure Database for PostgreSQL: https://learn.microsoft.com/en-us/azure/postgresql/flexible-server/concepts-security

### Availability and reliability

TODO: describe 5 non functional requirements for system availability, which is the time when the application must be available for use and times that are most acceptable for maintenance; and for system reliability, which is the probability that the system will operate without failure over a specified time period. Reliability aims to minimize system failures and downtime, while availability aims to maximize operational time.

Reference links:
- Service Level Agreements (SLA) for Azure Services: https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services?lang=1
- Product availability: https://azure.microsoft.com/en-us/explore/global-infrastructure/products-by-region/
- Azure reliability documentation: https://learn.microsoft.com/en-us/azure/reliability/overview
- Reliability guides by service: https://learn.microsoft.com/en-us/azure/reliability/overview-reliability-guidance
- Azure App Service: https://learn.microsoft.com/en-us/azure/reliability/reliability-app-service?tabs=cli#availability-zone-support
- PostgreSQL: https://learn.microsoft.com/en-us/azure/reliability/reliability-postgresql-flexible-server

### Recoverability

TODO: describe 5 non functional requirements for system recoverability, which is the ability to restore the system to a specified operational level after a disaster or other failure. Recoverability aims to minimize the time and data lost during a system failure.

Reference links:
- Disaster recovery overview: https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview
- Azure App Service: https://learn.microsoft.com/en-us/azure/reliability/reliability-app-service?tabs=cli#availability-zone-support
- PostgreSQL: https://learn.microsoft.com/en-us/azure/reliability/reliability-postgresql-flexible-server

### Business Continuity

TODO: describe 5 non functional requirements for business continuity, which is the ability of an organization to maintain essential functions during, as well as after, a disaster has occurred. Business continuity aims to minimize the impact of a disaster on the organization.

Reference links:
- Business Continuity Management Program: https://learn.microsoft.com/en-us/azure/reliability/business-continuity-management-program

### Cost management

TODO: describe 5 non functional requirements for cost management, which is the process of planning and controlling the budget of a project or business. Cost management aims to minimize the cost of the project or business.

Reference links:
- Gets started: Manage cloud costs: https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/get-started/manage-costs
- Azure App Service: https://azure.microsoft.com/en-us/pricing/details/app-service/linux
- PostgreSQL: https://azure.microsoft.com/en-us/pricing/details/postgresql/flexible-server/

### System maintenance and support

TODO: describe 5 non functional requirements for system maintenance and support, which is the process of maintaining and supporting the system for end users in production. System maintenance and support aims to minimize the time and effort required to maintain and support the system.

Reference links:
- Azure Monitor overview: https://learn.microsoft.com/en-us/azure/azure-monitor/overview
- Azure Application Insights overview: https://learn.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview
- Overview of Log Analytics in Azure Monitor: https://learn.microsoft.com/en-us/azure/azure-monitor/logs/log-analytics-overview
- Apply design principles and advanced operations: https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/manage/design-principles
- Workload operations in cloud management: https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/manage/considerations/workload

## Software modelling

### Use Case and Sequential model

TODO: Add at least 3 use case and sequence diagram/s and explain each use case. This sample table can be useful to qualify each use case.

| Use Case Name | Register User |
| --- | --- |
| Summary | In order to get personalized or restricted information, place orders or do other specialized transactions a new user must register a username and password.
| Basic Flow |  <ol><li> The use case start when a user indicates that he wants to register.</li><li>The system requests a username and password.</li><li>The user enters a username and password.</li><li>The system checks that the username does not duplicate any existing registered usernames.</li><li>The system requests a name (*), street, city, state, zipcode(*), phone and email address. Items marked by (*) are required.</li><li>The user enters the information.</li><li>The system determines the user's location and access level and stores all user information.</li><li>The system executes use case Register Preferences.</li><li>The system starts a login session and displays a welcome message based on the user's preferences.</li></ol>
| Alternative Flows | <ul><li>Step 4: If the username duplicates an existing username the system displays a message and the use case goes back to step 2.</li><li>Step 5: If the user does not enter a required field, a message is displayed and the use case repeats step 4.
| Extension Points | Register Preferences
| Preconditions | none |
| Postconditions | The user can now obtain data and perform functions according to his registered access level.
| Business Rules | <ul><li>A registered user's location is the SBE location nearest his zip code.</li><li>Access levels are</li><ul><li>0: A user can access only data classification 0</li><li>1: The user can access data classification <= 1</li><li>2: The user can access data classification <= 2</li></ul></li></ul><br/>The default access level is 0

Reference links:
- Visual paradigm: https://online.visual-paradigm.com/app/diagrams/

### Entity relationship diagram

TODO: Add an entity relationship diagram that represents the data model of the system. -->

### Data flow diagram

TODO: Add a data flow diagram that represents the data flow of the system. -->

## Software Quality Assurance (SQA) requirements

### Test plan

TODO: The following Test Plan sections contain a project-specific description of testing for this project.
- Testing Approach: A general overview of the plan for testing the entire system is given here. Included are how each major group of software features will be tested, major testing activities, techniques, and testing tools to be used.
- Tests to be Performed: This describe a detailed explanation of the tests that have been developed for the system, including links to each of the tests and to the test results.
