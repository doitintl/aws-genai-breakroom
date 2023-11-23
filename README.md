

# Text-to-SQL demo using AWS Bedrock and Anthropic Claude V2 APIs. 
The  AWS Bedrock contains the publisher endpoints for Anthropic Claude V2 model, which is a large language model (LLMs) that generate text and code in response to natural language prompts.

## Setup
Create a ```config.py``` in the config folder with the following environment variables: \
openai_api_key = "" API key from OpenAI \
service_account = "" #Cloud SQL service account \
database_version="MYSQL_8_0" \
cpu=2 \
memory="8GB" \
storage_size="10GB" \
db_user = "" \
db_name = "" \
bucket = "gs://" # bucket for storing MySQL dump file \
project_id="" \
region="" \
instance_name="" # Instance name \

## Loading example dataset into database -
Use the ```mysql-database-setup.ipynb``` notebook to set up the database environment with config options above. This notebook does the following:
1. Download MySQL dump file from [MySQL Public Tutorial](https://www.mysqltutorial.org/mysql-sample-database.aspx)
2. Create Cloud Storage bucket and RDS instance
3. Import MySQL dump file into RDS instance

### Database Schema
This is a very common example relational structure for a retail company
![alt text](images/MySQL-Sample-Database-Schema.png "Title")

## ```bedrock-anthropic-claudev2-text-to-sql```: Use Text-to-SQL Generative AI to build an end-to-end application.
## ```bedrock-langchain-anthropic-claudev2-text-to-sql.ipynb```: Integrating Bedrock API with Langchain get questions/answers from our database.
LangChain is a framework for developing applications powered by language models. It enables applications that are:
* Data-aware: connect a language model to other sources of data
* Agentic: allow a language model to interact with its environment