# Automated CI/CD pipeline using Jenkins, and Github

## Technology and Tool Used
- postman
- Java
- Jenkin
- newman

## Prerequisites

- You must have installed node js to your system
- Postman
- Java
- NPM
- Newman

## Scenario of this project

- Admin will login to the system

- Create a user

- User can create a user

- User can create a multiple user

- User can't create a user without authorization

- User can't share a user without authorization

## API Documents

      https://documenter.getpostman.com/view/16548351/2s8YRjoszo  

## How to run this project

- clone this project

- hit following commands
      
          npm i newman
          npx newman run
          
 ## HTML report generate using Newman
       
       npm i newman-reporter-htmlextra
       
 - Now create another file named report.js
 
       copy paste following code:
       
       const newman = require('newman');

       newman.run({
       collection: require('./collection/customer_api_collection.json'), // pointing to local JSON file.
       environment: require('./collection/customer_api_env.json'), // pointing to local env file
       iterationCount: 1,
       reporters: 'htmlextra',
       reporter: {
        htmlextra: {
            export: './Reports/report.html', // If not specified, the file will be written to `newman/` in the current working directory.
        }
        }
    
       }, function (err) {
       if (err) { throw err; }
       console.log('collection run complete!');
       });
       
  - Now create a folder named Reports. If you do not create this folder, the report will be generate to a new folder named ‘newman’ in current working directory.

  - Then go to the package file and update “test” value under scripts as:
    “node report.js”
    
  - Now hit this command:

           npm test
  ## Jenkins
  
  ## What is Jenkins
  
Jenkins is an open-source automation server which enables developers around the world to reliably build, test, and deploy their software. 

![3](https://user-images.githubusercontent.com/78067017/235484426-f1c08051-c576-4ee7-9f9c-42b1af30de3f.png)


## What is CI:

Continuous delivery (CD) is the automated delivery of completed code to environments like testing and development. CD provides an automated and consistent way for code to be delivered to these environments.

## What is CD:

Continuous deployment is the next step of continuous delivery. Every change that passes the automated tests is automatically placed in production, resulting in many production deployments.

Continuous deployment should be the goal of most companies that are not constrained by regulatory or other requirements.


- Install Jenkins
      
           https://www.jenkins.io/download/
           - Download war file
           - Then go to this link: https://www.jenkins.io/doc/book/installing/war-file/
           - Run the WAR file
           - open the cmd
           - java -jar jenkins.war
           
 ## Install Jenkins
 
- Download and install from here.

- During installing, select logon type as LocalSystem and Next

- Then input port as 7070
- Click on Test Port and Next. If a green tick mark appears, then you are ready to go

- Then confirm the JDK location and Next

- Allow the firewall exception and next

- Click on the Install button

- After completing the installation go to the location: http://localhost:7070

- Then unlock Jenkins

![1](https://user-images.githubusercontent.com/78067017/235483568-a68c79fe-4e09-4d28-b04c-82cb1cc88e94.png)


- Go to the location and copy-paste the password and continue

- Then select Install suggested plugins and continue

- After installing it successfully, you will be redirected to the Jenkins dashboard.

   

![2](https://user-images.githubusercontent.com/78067017/235483714-1d4b0113-3982-4a46-a96f-0a7ecbfed0ba.png)

## Integrate Jenkins with Github

- Now give any of your project names

- Click on Freestyle project and ok

- Now you are in the project configuration screen

- Select Git from Source Code Management Section

- Give the github repo url of your project as https://github.com/Mamun104/CICD_withGitHubandJenkins/

- Now edit your branch name

- Now select Poll SCM from Build Triggers section

- Now select Execute Windows batch command in the build section

- Now clone your repository in any drive and locate the project in the script field by this command

                  d:
                  cd "Automation_Work\API Automation"
                  npm test file .\customers.test.js
  

-  d: means which drive you have cloned your repo
- cd “<project location>” means where is your project location
- the last line is the command to execute your project

- Now save the configuration

- Now click on Build Now button and you will see the project is running throw Jenkins in the build history.

- Now edit your code and push it to GitHub. Then you will see that Jenkins will automatically trigger the run command of your project.


## Output

![4](https://user-images.githubusercontent.com/78067017/235485017-49c19daf-521f-4924-b089-89a4e92d441c.png)

![Screenshot_1](https://user-images.githubusercontent.com/78067017/235485052-1c86d5f4-6a4b-4a1a-95fe-39cb591a9edc.png)




