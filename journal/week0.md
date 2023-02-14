# Week 0 — Billing and Architecture


## CREATING AN ARCHITECTURE DIAGRAM FOR CRUDDR

In creation of the architecture diagram for cruddr it was essential for me to figure out what the risks, assumptions and constraints were to derive the requirement of Cruddr.
I was able to achieve this by going through the notes taken during the meeting with both investors and dev team. Based on this meeting note I was able to streamline them accordingly.
RISKS
DELIVERY TIME- The delivery time for this particular project which was agreed upon that it would take 14 weeks to complete. Using the Iron-Triangle I was able to get a reasonable  expectation to work with based on the delivery time. 
ASSUMPTIONS
I will be assuming that we have network bandit will be sufficient for the project you are, I also will assuming that we've got enough money or the budget has been approved to complete the project.
CONSTRAINTS
For the appropriate completion of the project it is tantamount to address either policy or technical limitation that may ensue while working on this project. Some of which are,
Using AWS as the cloud vendor selected,
The budget, which is estimated to be 0( we will be leveraging AWS Free tier) 
Time frame of 14weeks for the project completion.
REQUIREMENT
Ephemeral-First (micro-blogging platform)
-Frontend- JavaScript using react
-Backend-  Python using ~(flask)
- API only -(~no tightly coupled monolithic) 
-Careful of budget
-User content (upload?)
-Users- college students, younger students, professionals
--user validation?
--Age Limit?
ORM(Object relational mapping)

After gathering the RRAC, I was able to leverage these information, draw up the requirement and then iterate with the risk, assumption and constraints so as to come up with a good foundational Requirements.
After the foundation has been set the conceptual design implementation follows. Which is basically business requirement that is translated to common language that can be understood by users and developers. The conceptual design often referred as napkin doesn’t involve any technical aspect, so I sketched out the basic parameters for which my design will work.

## Image
<path xmlns="http://www.w3.org/2000/svg" d="M-3153.97-2417.43a6 6 0 0 1 6-6h1336.28a6 6 0 0 1 6 6v810a6 6 0 0 1-6 6h-1336.27a6 6 0 0 1-6-6z" stroke="#232f3e" stroke-width="3" fill="#fff" fill-opacity="0"/>

Link to my Conceptual Design
https://lucid.app/lucidchart/baccf444-30b6-4911-86de-63257a979c43/edit?viewport_loc=-3798%2C-2576%2C2731%2C1320%2C0_0&invitationId=inv_baeac777-4dd2-4e34-8ced-7783b8ab4c58



## DESIGN PROCESS

1.	User load up the Crudr website either from their mobile or Laptop
2.	User directed at Google IDP to authenticate( The authentication was added because the requirement specify User validation, which will be handled by google IDP Identity provider)
3.	If successful, google returns a token
4.	Cognito API called using ID Pool to swap google token for AWS
5.	Cognito assumes a Role, AWS temporary credentials are generated 
6.	Credential Returned ( Identity Access Management Temporary Security Credential was also added as a security measure, as the third service application won’t have a direct access to our AWS account and the access key with the private keys are not hardcoded in case of a security breach, the AWS account won't be compromised.



