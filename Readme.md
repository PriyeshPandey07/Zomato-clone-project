Steps:-
Step 1 - Launch an Ubuntu(22.04) T2 Large Instance

Step 2 - Install Jenkins, Docker and Trivy in ubuntu instance. 

Step 3 - Create a Sonarqube Container using Docker.
*SONAR IMAGE AND CONTAINERIZATION*
docker pull sonarqube:lts-community
docker run -dit --name sonar -p 9000:9000 sonarqube:lts-communit

*SONAR INTEGRATION IN JENKINS*
Go to sonar server> Administration> Security> Users> Generate token> Give name> Noexpiry> Generate and copy the token.
Add this sonar token in Jenkins credentials, Manage Jenkins > Credentials

Manage Jenkins> Tools> SonarQube Scanner Installations, Give the name, Tick the Install automatically.
Manage Jenkins> Tools> Nodejs installations, give the name, it will install automatically.
Manage Jenkins> Tools> JDK installations, give the name, Tick the Install automatically, add installer as Install from adoptium.net and select the version according to requirement.
Manage Jenkins> Tools> Dependency-Check installations, give the name, Tick the Install automatically, add installer as Install from gitHub.com.
SAVE*

Manage Jenkins> System> SonarQube installations, give the name, Put the sonar url [https://public_ip:9000], Select the authentication token which was added in Jenkins credentials. 

*CREATE A PROJECT IN SONARQUBE*
Go to project, Manually, Give the name to the project, Give the branch name of git repo and then click on setup.
Go to locally, Step-1 click on 'Use existing token' and then select the or copy user token which is created and added on Jenkins credentials. Step-2 click on Others(), then select Linux OS. Then copy Execute the scanner 


Step 4 - *INSTALL NECESSARY PLUGINS FOR JENKINS* 
Docker, Docker pipeline, Docker api, Docker build-step
SonarQube Scanner, Sonar Quality Gates 
OWASP Dependency-Check 
NodeJS 
Eclipse Temurin installer

Step 5 - Install necessary tools like Nodejs, Docker, JDK, Dependency check and Git.

Step 6 - Create a Pipeline Project in Jenkins using a Declarative Pipeline
                
Step 7 - Docker Image Build and Push

Step 8 - Deploy the image using Docker
