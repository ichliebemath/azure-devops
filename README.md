# flask-ml-service
This project is a sample Flask application created on the basis of the Udacity project. The motivation is to build a Github repository from scratch and create a scaffolding with Azure Pipeline that will perform both Continuous Integration and Continuous Delivery

[![Python application test with Github Actions](https://github.com/ichliebemath/azure-devops/actions/workflows/main.yml/badge.svg)](https://github.com/ichliebemath/azure-devops/actions/workflows/main.yml)

## Project Plan

1) Trello Board: https://trello.com/b/IUpZXhDw/udacity
2) Spreadsheet: 

    | Date       | component                          |
    | ---------- | ---------------------------------- |
    | 11.5.2022  | Setup project plan                 |
    | 11.10.2022 | Commit code to Github repo         |
    | 11.15.2022 | Test with Github Actions           |
    | 11.20.2022 | Setup Azure Cloud Shell            |
    | 11.25.2022 | Clone Project to Azure Cloud Shell |
    | 11.30.2022 | Create Virtual Machine             |
    | 12.5.2022  | Add Azure Pipeline Agent           |
    | 12.10.2022 | Create Azure Pipeline              |
    | 12.15.2022 | Deploy WebApp using pipeline       |
    | 12.20.2022 | Documentation                      |
    |            | Goals                              |
    |            | Finish Udacity Project 2 !         |

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
    python3 -m venv ~/.azure-devops
    source ~/.azure-devops/bin/activate
    ```
    
    ![image](https://user-images.githubusercontent.com/74469717/205753581-b6474893-8aa2-4a03-8163-670e761fcc0d.png)
        
4. Clone Github Repo to Azure Cloud Shell

    <img width="777" alt="image" src="https://user-images.githubusercontent.com/74469717/205963519-bc22dd85-edaf-475e-b63a-62b36bc17df6.png">

    ![image](https://user-images.githubusercontent.com/74469717/206275399-fce3000e-c822-455a-8bce-5d6984bd0eb1.png)

5. run `make all` in Azure cloud shell to download all the dependencies and test the code

    ![image](https://user-images.githubusercontent.com/74469717/205755987-e2ae26f5-1b6b-4faf-b273-5497399ee2fe.png)

6. Enable Github Actions

    1. Setup workflow

    ![image](https://user-images.githubusercontent.com/74469717/205757096-c56317b0-70d3-4ace-b068-bd38b083421b.png)

    2. Run the workflow and test the code

    ![image](https://user-images.githubusercontent.com/74469717/205757370-15525daa-e915-410b-ad06-bbc5c3c67c18.png)



## Continuous Delivery 
### Make Manual Prediction
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
    ```
    az webapp log tail --name flask-ml-service --resource-group Azuredevops
    ```
    <img width="1353" alt="image" src="https://user-images.githubusercontent.com/74469717/205967962-33682640-db97-4653-b49d-47da9e1b7646.png">

### Prediction with Automation

1. Setup Virtual Machine in Azure Portal
    ![image](https://user-images.githubusercontent.com/74469717/205955665-c63b846d-b965-4dfd-9ffe-1badbc675eae.png)

2. Create new Azure Devops project and add the pipeline
    ![image](https://user-images.githubusercontent.com/74469717/205958159-a239b20f-68c6-4996-9fab-d942b3d466ec.png)

3. Add Agent Pool 
    <img width="1470" alt="image" src="https://user-images.githubusercontent.com/74469717/205962468-7258bca1-1b66-41a2-9ebd-010a46361e6e.png">

4.  Deploy Web App

    <img width="1507" alt="image" src="https://user-images.githubusercontent.com/74469717/205962686-e76dd8a9-4e08-4e20-8270-0f24ac82ca7c.png">

## Demo
https://www.youtube.com/watch?v=6DaERsWbHFs

