
### Project :Continuous Integration and Continuous Delivery on Azure
In this project, you will build a Github repository from scratch and create a scaffolding that will assist you in performing both Continuous Integration and Continuous Delivery. You'll use Github Actions along with a Makefile, requirements.txt and application code to perform an initial lint, test, and install cycle. Next, you'll integrate this project with Azure Pipelines to enable Continuous Delivery to Azure App Service.


## Project Plan

* A link to a Trello board for the project : https://trello.com/b/TOI3yMD0/udacityproject6
* A link to a spreadsheet that includes the original and final project plan : https://github.com/abdullahfurquan/starter_file/blob/main/project-management-template.xlsx

## Instructions

* Architectural Diagram (Shows how key parts of the system work) : ![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/image.PNG)

## Project cloned into Azure Cloud Shell
* Enter to Azure Portal with your Accoutn and open a Azure Cloud shell ( use Bash).If you are not created one , just follow the first creation and wait a seconds to get your Cloud Shell.
* First of all set up SSH Keys in your azure cloud shell, add the id_rsa.pub key to your GitHub repo ( ssh keys) and then clone the project there.

ssh-keygen -t rsa

cat ~/.ssh/id_rsa.pub


![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/project_clonned_in_azure.PNG)



## Project running on Azure Webapp Service
* create a virtual env with python 3.7
* Install the packages using:  make install
* Run the command to start the app. 
 
 az webapp up --name eram --resource-group Azuredevops --runtime "PYTHON:3.7" (so the webapp name is flask-ml-lingchenzhu)
* Wait until the webapp infrastructure is created. 


![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/app4_a.PNG)


![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/app6.PNG)



## Make prediction
* Update make_predict_azure_app.sh to have the webapp name eram in the POST target line

## Output of streamed log files from deployed application

* az webapp log tail :



![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/app2_a.PNG)



* we can see log from,  by opeining url in a browser : https://eram.scm.azurewebsites.net/api/logs/docker



![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/app1.PNG)


## Test code using make command
* Passing tests that are displayed after running the make all command from the Makefile


![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/make_all_a.PNG)



![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/make_all_b.PNG)



![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/make_all_c.PNG)



* Output of a test run :Run: ./make_predict_azure_app.sh 



![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/app5.PNG)


## load test with locust
* Load test an application using Locust (swarm the target website from localhost). 
From linux system start any editor(pycharm). 
Install packgae locust: pip install locust
run: locust -f locustfile.py
Open browser and go to http://localhost:8089/



![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/load_test_b.PNG)




![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/load_test_a.PNG)



## Successful deploy of the project in GitHub Actions

![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/ci%20github%20action.PNG)


## Successful deploy of the project in Azure Pipelines Note the official documentation should be referred to and double checked as you setup CI/CD
* Running Azure App Service from Azure Pipelines automatic deployment 



![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/pipeline_a.PNG)



![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/pipeline_a.PNG)



![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/pipeline_a.PNG)




* sample successful run of the project in Azure Pipelines 


![alt text](https://github.com/abdullahfurquan/starter_file/blob/main/new.PNG)



## Enhancements

* Containerize the webapp in a docker image and publish the docker image to a repository such as Docker Hub
* Deploy a Kubernetes version of the project on Azure Kubernetes Service (AKS) for high scalability and better usability

## Demo 

* link Screencast on YouTube :  https://youtu.be/yTYuWA2xpBw


