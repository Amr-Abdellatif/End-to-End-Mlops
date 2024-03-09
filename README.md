In this project im building a MLops project based on MLFlow tool

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

### More Detailed walkthrough -> Tracing path for each step from main.py
1. DataIngestionTrainingPipeline() -> stage_01_data_ingestion -> configuration.py (class ConfigurationManager) -> Constants folder (__init__.py) -> init.py is pointing to 3 yaml files -> config.yaml contains the configuration required for data ingestion

2. write me later ...

3. config.yaml insertion -> define `class DataTransformationConfig:` -> `class ConfigurationManager:` (def get_data_transformation_config(self) -> DataTransformationConfig:) -> `class DataTransformation:` (def train_test_spliting(self):) -> Worflows copy and paste parts -> create stage 3 pipeline in which inside of it we're checking if the previous step returns `True` or not to initiate this stage3.py 


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