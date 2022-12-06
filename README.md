# flask-ml-service
This project is a sample Flask application created on the basis of the Udacity project. The motivation is to build a Github repository from scratch and create a scaffolding that will perform both Continuous Integration and Continuous Delivery

[![Python application test with Github Actions](https://github.com/ichliebemath/azure-devops/actions/workflows/main.yml/badge.svg)](https://github.com/ichliebemath/azure-devops/actions/workflows/main.yml)

## Project Plan

1) Trello Board: https://trello.com/b/IUpZXhDw/udacity
2) Spreadsheet: 

## Continuous Integration

1. Create a Github Repo containing requirements.txt and Makefile

<img width="992" alt="Screenshot 2022-12-06 at 13 37 54" src="https://user-images.githubusercontent.com/74469717/205914896-f359f2b5-b4a8-438c-a7e7-b883de978d30.png">


2. Connect Azure Cloud Shell with Github Repo with ssh-keys (with your own directory)

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

5. run `make all` in Azure cloud shell to download all the dependencies and test the code

![image](https://user-images.githubusercontent.com/74469717/205755987-e2ae26f5-1b6b-4faf-b273-5497399ee2fe.png)

6. Enable Github Actions

6.1 Setup workflow

![image](https://user-images.githubusercontent.com/74469717/205757096-c56317b0-70d3-4ace-b068-bd38b083421b.png)

6.2 Run the workflow and test the code

![image](https://user-images.githubusercontent.com/74469717/205757370-15525daa-e915-410b-ad06-bbc5c3c67c18.png)



## Continuous Delivery 
### Make 
1. Copy the Flask starter code to Azure App Services and prepare for a push

    ```
    git clone https://github.com/udacity/nd082-Azure-Cloud-DevOps-Starter-Code.git
    git clone https://github.com/ichliebemath/flask-ml-service.git    ```
    cp -r nd082-Azure-Cloud-DevOps-Starter-Code/C2-AgileDevelopmentwithAzure/azure_pipelines_exercise/starter_files/ flask-ml-service/
    cd flask-ml-service
    git add -A
    git status
    git commit -m "Upload the starter flask app"
    git push
    ```
    
2. Deploy the APP in the Azure Cloud Shell
    ```
    az webapp up --name flask-ml-service --resource-group Azuredevops --runtime "PYTHON:3.7"
    ```

![image](https://user-images.githubusercontent.com/74469717/205757766-962a63d9-c2c5-4c96-b154-45acb798b383.png)



3. Making predictions

    ```
    ./make_predict_azure_app.sh
    ```

![image](https://user-images.githubusercontent.com/74469717/205757827-d81ab25e-6774-431f-a4e5-9254f3f7e7b2.png)

4. Logs


