# DevOps-Practical-Project

## Contents
* [Brief](https://github.com/AmirAR-QA/DevOps-Practical-Project#brief)
   * [Listed Requirements](https://github.com/AmirAR-QA/DevOps-Practical-Project#listed-project-requirements)
   * [Created With](https://github.com/AmirAR-QA/DevOps-Practical-Project#created-with)
* [Layout](https://github.com/AmirAR-QA/DevOps-Practical-Project#layout)
* [Architecture](https://github.com/AmirAR-QA/DevOps-Practical-Project#architecture)
   * [Database Relationship Diagram](https://github.com/AmirAR-QA/DevOps-Practical-Project#database-relationship-diagram)
   * [CI Pipeline](https://github.com/AmirAR-QA/DevOps-Practical-Project#ci-pipeline)
* [Project Management](https://github.com/AmirAR-QA/DevOps-Practical-Project#project-management)
* [Risk Assessment](https://github.com/AmirAR-QA/DevOps-Practical-Project#risk-assessment)
* [Testing](https://github.com/AmirAR-QA/DevOps-Practical-Project#testing)
* [Application](https://github.com/AmirAR-QA/DevOps-Practical-Project#application)
* [Future Development](https://github.com/AmirAR-QA/DevOps-Practical-Project#future-development)
* [Contributors](https://github.com/AmirAR-QA/DevOps-Practical-Project#contributors)
* [Acknowledgments](https://github.com/AmirAR-QA/DevOps-Practical-Project#acknowledgements)
* [Licensing](https://github.com/AmirAR-QA/DevOps-Practical-Project#licensing)

## Brief 

I have been tasked with creating a web app which is made up for 4 interconnected services, and then testing, deploying, and configuring the app in an automated environment with a complete CI/CD Pipeline. This will showcase my knowledge and understanding of the programs that we've discussed so far, as well as showcasing my ability to use them effectively. 

## Listed Project Requirements

* A Kanban board tech) with full expansion on tasks needed to complete the project.
* This could also provide a record of any issues or risks that you faced creating your project.
* An Application fully integrated using the Feature-Branch model into a Version Control System which will subsequently be built through a CI server and deployed to a cloud-based virtual machine.
* If a change is made to a code base, then Webhooks should be used so that Jenkins recreates and redeploys the changed application
* The project must follow the Service-oriented architecture that has been asked for.
* The project must be deployed using containerisation and an orchestration tool.
* As part of the project, you need to create an Ansible Playbook that will provision the environment that your application needs to run.
* The project must make use of a reverse proxy to make your application accessible to the user.

## Created With

* Visual Studio Code - IDE
* GCP - Database and instance host
* MySQL - Database language
* Jenkins - CI pipeline
* Git - Version control
* GitHub - Repository and version control
* Trello - Project management
* Pytest - Unit testing
* Ansible - Load balancer
* Nginx - Reverse Proxy
* Docker (Compose, Swarm) - Containers to deploy to
* Draw.io - ERD creation

## Layout

To satisfy the requirements of this project I created an app with generates a random encounter, a random location, and an outcome based on the counter In more detail:

Service 1: Front-end of the program, displays all the information by requesting it from the other services.
Service 2: Generates a random encounter
Service 3: Generates a random location
Service 4: Generates an outcome of the random encounter from service 2, then sends the information to service 1 by a POST request

Docker and Docker-Compose used to containerise the images and builds
Docker Swarm spreads the app across worker nodes and a manager node
Nginx acts as a reverse proxy load balancer so no one node gets overloaded
Testing takes place in the automated Jenkins environment
Ansible configures the docker and nginx functionalities
Jenkins deploys the app

![SERVICES](https://i.imgur.com/iJdegYr.png)

Process
* A user clicks on the adventure button
* Service 1 initiates a get request from service 2 and 3 bringing back a random location and a random encounter
* Service 1 initiates a post request with this information returning a random outcome based on the encounter
* Service 4 passes this information back to service 1
* Service 1 posts this to an external SQL database instance
* Service 1 displays the adventure on the page alongside the last 5 adventures

## Architecture

### Database Relationship Diagram

![ERD](https://i.imgur.com/AS00oZ6.png)

Displayed above is my Entity Relationship Diagram showing the table that is used by the app. It's very simple 

### CI Pipeline

![CI](https://i.imgur.com/PcgtRtR.png)

The pipeline displayed above was my working stream. 
* Worked out what to work on first and tracked all streams of work with my Trello board
* I started by developing the code of the app using Python and flask
* Pushed the code to this GitHub repository
* Cloned the repository into my GCP instance on 4 seperate VM's
* Pulled the code, built and ran the app via Jenkins
* Tested the code with Pytest (unit testing) and Selenium (integration testing)
* I accordingly adjusted my code till it passed my assertions and pushed to my GitHu
* b to be rebuilt by Jenkins
* I then used Jenkins to build the final app for presentation

I had intended to run the testing via jenkins itself but the skills required are, as of yet, not in my grasp. 

## Project Management

The Trello board I used to track and manage tasks while developing the app which can be found here https://trello.com/b/Co65bKUV/qa-project-2

I archived lists as I went and moved cards from left to right, going from it's conception as a User Story to the Design, and Testing lists (now archived) and then to the Doing and Completed lists (still visible) 

![TB](https://i.imgur.com/QTx3m2Y.png)

The User Stories that have been entered come with Acceptance Criteria in the comments, like so;

![US](https://i.imgur.com/tGSAc3Z.png)

## Risk Assessment

![RA](https://i.imgur.com/HkCf69L.png)

The following matrix shows my risk assessments. The first three risks I forsaw during my intial planning stage. Later on I realised, that in my rush to finish the app my passwords weren't as secure as they should have been. Similarly, I added risk 5 when I had an outage during development and realised that GCP may be prone to outages too. 

## Testing

Testing was carried out in an automated fashion through Jenkins. Pytest was used to unit test. My unit testing is highly developed, with a total coverage of 100%. This shows marked improvement on my previous project testing. I do believe that I could have implemented more stenuous and complicated tests to ensure every possible function had been tested thoroughly.

![TESTS](https://i.imgur.com/6OvPw6T.png)

## Application

My application is fully functional and has no bugs (that I've yet found). As you can see the app is fairly simple in its application.

![APP](https://i.imgur.com/JMlfKPv.png)

A user presses the button, and a encounter, location, and outcome are displayed - then stored below.

## Future Development

There are a few points of improvements I'd like to carry out. 

A note on versioning - The current app is fully functional and without any major (or percievable minor) bugs. Thus the version number is 0.1.0.

## Contributors

Me, Amir. 

## Acknowledgements

Nick, Ben, and Raji for providing me with the relevant skills needed to be able to code the app.

Special thanks to Harry who was an absolute gem during the entire process and really made it possible with filling in gaps in our knowledge and troubleshooting every single issue. My saviour.

## Licensing 

MIT License

Copyright (c) [2021] [Amir Abdur-Rahman]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
