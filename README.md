# In this project im building a MLops project based on MLFlow tool along side ci/cd with aws deployment

## Requirements to figure this out

1. What is logging and why it is important ?
2. why do we need Scripts instead of notebooks ?
3. double underscore methods also called dunder methods and why do we have all these __init__ files inside each folder ?
4. making a Venv -> virtual environment and installing a requirements.txt file


## Bird's eye Walkthrough 
1. first step i'm testing every step in the research folder which is full of notebooks
2. building logging files
3. building config yaml variables
4. buildig data ingestion 
5. building data validation
6. building data transformation
7. building data trainer
8. building data evaluation
9. prediction
10. web application
11. deployment


## Workflows

1. Update config.yaml
2. Update schema.yaml
3. Update params.yaml
4. Update the entity
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline 
8. Update the main.py   # ui related
9. Update the app.py    # ui related

## Tips and tricks
I use VSCode for this so Ctrl+p is so handful when it comes to jumping between files


# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/Amr-Abdellatif/End-to-End-Mlops-with-MLFlow.git
```
### STEP 01- Create a virtual environment after opening the repository

```bash
python -m venv venv
```

```bash
./venv/Scripts/activate
```


### STEP 02- install the requirements
```bash
python -m pip install -r requirements.txt
```


```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```



## MLflow

[Documentation](https://mlflow.org/docs/latest/index.html)


##### cmd
- mlflow ui to view mlflow user interface in web

# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 566373416292.dkr.ecr.ap-south-1.amazonaws.com/mlproj

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app




## About MLflow 
MLflow

 - Its Production Grade
 - Trace all of your expriements
 - Logging & tagging your model



### More Detailed walkthrough -> Tracing path for each step from main.py
1. DataIngestionTrainingPipeline() -> stage_01_data_ingestion -> configuration.py (class ConfigurationManager) -> Constants folder (__init__.py) -> init.py is pointing to 3 yaml files -> config.yaml contains the configuration required for data ingestion

2. write me later ...

3. config.yaml insertion -> define `class DataTransformationConfig:` -> `class ConfigurationManager:` (def get_data_transformation_config(self) -> DataTransformationConfig:) -> `class DataTransformation:` (def train_test_spliting(self):) -> Worflows copy and paste parts -> create stage 3 pipeline in which inside of it we're checking if the previous step returns `True` or not to initiate this stage3.py 
