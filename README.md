# CI CD Based Web Application Deployment


## Overview
This project shows an automated CI CD pipeline for a Java web application. The pipeline links GitHub with Jenkins for continuous integration and continuous deployment. Each code commit starts an automated workflow which builds the application, checks code quality, stores artifacts, and deploys the application to a server.



## Goal
Create an automated process for building and deploying a Java web application with DevOps tools.


## Technologies Used
* Jenkins
* GitHub
* Apache Maven
* SonarQube
* Sonatype Nexus Repository Manager
* Apache Tomcat
* AWS EC2
* Linux
* Java



## Project Workflow

1. Code Management
Source code stored in GitHub repository.

2. Automated Trigger
GitHub webhook sends a trigger to Jenkins after each code push.

3. Build Process
Jenkins pipeline starts automatically. Maven compiles the project and generates a WAR file.

4. Code Quality Analysis
SonarQube scans the source code and produces quality reports.

5. Artifact Storage
Nexus Repository stores the generated build artifact.

6. Deployment
Jenkins deploys the application to Apache Tomcat running on an AWS EC2 Linux instance.


<br>


## Architecture Flow
Developer → GitHub → Jenkins Pipeline → Maven Build → SonarQube Analysis → Nexus Artifact Storage → Tomcat Deployment on EC2



## Project Result
An automated CI CD pipeline handles build, code analysis, artifact management, and deployment of the web application. This process reduces manual work and improves deployment reliability.