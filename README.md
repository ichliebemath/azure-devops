# flask-ml-service
A sample Flask application to showcase the Azure Pipeline.

Motivation: Build a Github repository from scratch and create a scaffolding that will perform both Continuous Integration and Continuous Delivery

# Environment
Python 3.7

# Continuous Integration
## Set up Azure Cloud Shell

1. Create a Github Repo containing requirements.txt and Makefile
<img width="1785" alt="image" src="https://user-images.githubusercontent.com/74469717/205752895-26937107-b6c4-44a4-9bfa-f07113aa7566.png">

2. Connect Azure CLI with Github Repo with ssh-keys


3. Setup Virtual Environment 
![image](https://user-images.githubusercontent.com/74469717/205753581-b6474893-8aa2-4a03-8163-670e761fcc0d.png)


4.run make all in Azure cloud shell to test code
![image](https://user-images.githubusercontent.com/74469717/205755987-e2ae26f5-1b6b-4faf-b273-5497399ee2fe.png)

5. Enable Github Actions

5.1 Setup workflow
![image](https://user-images.githubusercontent.com/74469717/205757096-c56317b0-70d3-4ace-b068-bd38b083421b.png)

5.2 Run the yml.file
![image](https://user-images.githubusercontent.com/74469717/205757370-15525daa-e915-410b-ad06-bbc5c3c67c18.png)

###

###Configure Github Actions

# Continuous Delivery 

deploy the Flask starter code to Azure App Services

Making predictions
![image](https://user-images.githubusercontent.com/74469717/205757766-962a63d9-c2c5-4c96-b154-45acb798b383.png)

![image](https://user-images.githubusercontent.com/74469717/205757827-d81ab25e-6774-431f-a4e5-9254f3f7e7b2.png)

Logs


