# CRM task AI generator

This project analyzes dialogues between clients and managers to generate relevant tasks in a CRM system. It uses OpenAI's language model to formulate tasks based on dialogues and feedback provided.

## Requirements

- Python 3.x
- Required Python libraries:
  - pandas
  - openai
  - re
  - nltk
  - configparser

You can install the required libraries using pip:

```bash
pip install pandas openai nltk configparser
``` 

## Setup and Configuration

### Obtain OpenAI API Key
You need an OpenAI API key to use the language model. You can get your API key by signing up at OpenAI. 
Put your API key and name of the OpenAI Model in config.ini:

```
[openai]
api_key = {your-api-key}
model = {model}
```

### Prepare Your CSV File
Ensure your CSV file is formatted with columns for _dialog_id,dialog_text,dialog_date_. Put name of .csv file in config.ini:
```
[files]
input_file = {your-input-file.csv}
output_file = {your-output-file.csv}
```

## Usage
Execute the script in the same directory:
```
python task_generator.py
```
