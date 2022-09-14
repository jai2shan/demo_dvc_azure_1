## Demo

01. Create a git repository in github.com       
02. Clone the repository   
03. Initiate DVC in the git repository      
``` 
    dvc init    
```       
04.  Set up Azure blob storage   
> Add the special permissions for this type of request:         
   . Storage Blob Data Contributor           
   . Storage Queue Data Contributor          

> Create a additional folder in the blob storage where you want to add your data
    
    az account list --output table  

        
> Activating the required Azure subscription

    az account set --subscription b99a3d53-4546-410d-8236-ddc98cb9e9cd

> Add the remote directory for data

    dvc remote add -d titanic azure://dvc-demo

> Modify the storage account name    

     dvc remote modify titanic account_name 'gdpdeva3suks'

> Copy the files to Data folder in dvc. Add Data to dvc.

    dvc add Data

> Commit dvc config file to git. Add and commit all untracked files

    git add .
    git commit -m "Version 1 - Data"
    
> Push the data to Cloud location

    dvc push

> Copy the training scripts and config.yaml     
> Do a git commit

    git add .
    git commit -m "Training Scripts"

> Create a model folder and add the same to the dvc

    dvc add model

> Run the python training

    python3 -m training

> Once the model ran successfully we can commit the current state to git

    git add .
    git commit -m "Version 1 Model Run"
    dvc push
    git push

> 

