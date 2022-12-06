# flask-ml-service
This project is a sample Flask application created on the basis of the Udacity project. The motivation is to build a Github repository from scratch and create a scaffolding that will perform both Continuous Integration and Continuous Delivery

[![Python application test with Github Actions](https://github.com/ichliebemath/azure-devops/actions/workflows/main.yml/badge.svg)](https://github.com/ichliebemath/azure-devops/actions/workflows/main.yml)

## Project Plan

1) Trello Board: https://trello.com/b/IUpZXhDw/udacity
2) Spreadsheet: 

## Continuous Integration
### Set up Azure Cloud Shell

1. Create a Github Repo containing requirements.txt and Makefile
![image](https://user-images.githubusercontent.com/74469717/205758509-51851c78-33da-44ea-a9b8-8fa63fe17fd5.png)

<img width="1785" alt="image" src="https://user-images.githubusercontent.com/74469717/205752895-26937107-b6c4-44a4-9bfa-f07113aa7566.png">

2. Connect Azure CLI with Github Repo with ssh-keys (with your own directory)

    ```
    ssh-keygen -t rsa
    cat /home/mei/.ssh/id_rsa.pub
    ```
    

3. Setup Virtual Environment and activate it

    ```
    ssh-keygen -t rsa
    cat /home/mei/.ssh/id_rsa.pub
    ```
    
4. Clone Github Repo to Azure Cloud Shell

![image](https://user-images.githubusercontent.com/74469717/205753581-b6474893-8aa2-4a03-8163-670e761fcc0d.png)

5.run 'make all' in Azure cloud shell to download all the dependencies and test the code

![image](https://user-images.githubusercontent.com/74469717/205755987-e2ae26f5-1b6b-4faf-b273-5497399ee2fe.png)

6. Enable Github Actions

6.1 Setup workflow

![image](https://user-images.githubusercontent.com/74469717/205757096-c56317b0-70d3-4ace-b068-bd38b083421b.png)

6.2 Run the yml.file

![image](https://user-images.githubusercontent.com/74469717/205757370-15525daa-e915-410b-ad06-bbc5c3c67c18.png)


##Configure Github Actions




## Continuous Delivery 

### Deploy the Flask starter code to Azure App Services

### Making predictions
![image](https://user-images.githubusercontent.com/74469717/205757766-962a63d9-c2c5-4c96-b154-45acb798b383.png)

![image](https://user-images.githubusercontent.com/74469717/205757827-d81ab25e-6774-431f-a4e5-9254f3f7e7b2.png)

### Logs


