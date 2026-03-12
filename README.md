# azuresqldb-github-adf-adls-adb-adls-powerbi-DataEngineeringProject
A simple project where data is read from Azure SQL DB/GitHub using ADF and stored in ADLS as the bronze layer in a medallion architecture. Using Databricks with a mount point, we applied basic transformations and saved the data as Delta. The cleaned data was loaded into Power BI for visuals.

Step1:-we need to create azure account. 
step2:-we need to create resource group inside azure account
step3:- need to azure sql database and now copy sql tables data from the github and paste inside azure sql database query run that query
step4:-create azure adls account and create a conatiner inside that container create a 3 folders bronze, silver, gold folders which is for medallian architecture.
<img width="805" height="344" alt="image" src="https://github.com/user-attachments/assets/02914f7d-bfc5-4b31-a3c8-229387feb28e" />

step5:-create a azure dataFactory account. inside adf need to create a one pipeline inside pipeline we need to select 4 copy actvities. for 3 copy activities we are getting data from azure sql database tables(stores, transactions,products) and customers data from github
step5.1:- for copy activities we need to create a linked services. so we need to create 3 linked services 1)till sql database 2)till github 3)till adls accounnt
step5.2:- for each copy activites need to select source linked service and for each copy activity dataset is different(we are not used dynamic values)
<img width="936" height="268" alt="image" src="https://github.com/user-attachments/assets/92f86152-c237-4c47-a42c-ddeec8d8193e" />

step5.3:-one we created copy activites now validate it and check is there any errors or not. after that pulish it and now trigger the pipelines now. all the data comes to bronze layer and goes to different folders.which already created.
step6:-create a azure databricks account and login  & create a cluster to run notebooks and create a folder inside folder create a notebook . attach a cluster  to this notebook..
<img width="955" height="494" alt="image" src="https://github.com/user-attachments/assets/37871399-a582-49f0-ac3b-96566741d412" />

step6.1:-inside adb notebook by using azure acess keys (inside adls storage account). we created a mount point inside notebook to access adls data.
stepp6.2:-we access data and did some trasformations like column names and dtaa types and stored back into adls gen2 silver folder as a delta format. finally inside cleansed data  in adb notebook we stored in adls gen2 gold layer folder. 
step7:- we downloaded final cleansed data inside adb notebook as csv data
step8:-open powerbi blank now get data and select csv file and do basic visualizations



s
