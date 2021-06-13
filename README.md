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

## Contributors

Me, Amir. 

## Acknowledgements

Nick, Ben, and Raji for providing me with the relevant skills needed to be able to code the app.

Special thanks to Harry who was an absolute gem and really made it possible with filling in gaps in our knowledge. 

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
