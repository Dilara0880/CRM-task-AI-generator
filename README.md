# CRM task AI generator

This project analyzes dialogues between clients and managers to generate relevant tasks in a CRM system. It uses OpenAI's language model to formulate tasks based on dialogues and feedback provided.

## [Решение задания 2](https://github.com/Dilara0880/CRM-task-AI-generator/blob/main/Task%202.md)
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

## Tests
Raw dialogue text in test_dialogs.csv:
  ```
  [02.04.2024 19:23:00]Менеджер: Добрый день!! [02.04.2024 19:24:00]Клиент: Здравствуйте! Хотел бы узнать о новой акции... 😊🙂 [02.05.2024 10:23:00]Менеджер: Конечно, у нас есть отличное предложение!!!!---
  ```
after _normalize_text_:
```
  менеджер добрый день клиент здравствуйте хотел узнать новой акции менеджер отличное предложение
```

after _generate_task_ (OpenAI answer):
```
{
  "Описание задачи": "Информирование клиента о новой акции",
  "Действие для менеджера": [
    "Найти информацию о текущих акциях компании",
    "Отправить клиенту полное описание актуальной акции",
    "Предложить дополнительные услуги или продукты, если применимо"
  ],
  "Приоритет задачи": "Средний",
  "Дополнительная информация": "Нет",
  "Сроки": "1 день"
}
```

OpenAI task evaluation:
```
7
```



