- [Moduł `flask` - tworzenie strony www](#moduł-flask---tworzenie-strony-www)
  - [Quick start](#quick-start)
  - [Setup for dev](#setup-for-dev)
  - [Python](#python)
  - [Dodaj template](#dodaj-template)
  - [static](#static)
  - [bootstrap](#bootstrap)
  - [Serwowanie różnych adresów](#serwowanie-różnych-adresów)
  - [Serwowanie z szablonów html, css](#serwowanie-z-szablonów-html-css)
    - [Uruchomienie](#uruchomienie)
  - [Deploy Linux](#deploy-linux)
  - [Docker](#docker)
  - [nginx](#nginx)

# Moduł `flask` - tworzenie strony www

## Quick start

Instalacja zleżności:
```bash
cd 87_flask_imprezka
python -m venv .venv
source .venv/bin/activate
pip install Flask
pip install -r requirements.txt
```

run **main.py** on port 8080:
```bash
cd src
flask --app main --debug run --host=0.0.0.0 --port=8080
```

<img style="width: 683px;" src="data:image/png;base64,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"/>


cleanup
```bash
pip list
deactivate
```

```
pip list
Package      Version
------------ -------
blinker      1.9.0
click        8.1.8
colorama     0.4.6
Flask        3.1.0
itsdangerous 2.2.0
Jinja2       3.1.5
MarkupSafe   3.0.2
pip          24.2
Werkzeug     3.1.3
```



## Setup for dev

Folder structure:

```
my_flask_app
├── .gitignore
├── requirements.txt
└── src/
    └── main.py
```


Plik **requirements.txt**:
```
Flask
Jinja2
gunicorn
```

Plik **.gitignore**:
```
.venv/
```




## Python


Plik **src/main.py**:

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello():
    return "Hello World!"

if __name__ == '__main__':
    # app.run() # ip=127.0.0.1, port=80
    app.run(host='0.0.0.0', port=8080)    
```

Uruchomienie:

```bash
cd src
flask --app main --debug run --host=0.0.0.0 --port=8080
```

Uruchomienie (wersja 2):

```bash
su
python main.py
```



## Dodaj template

```
my_flask_app
├── .gitignore
├── requirements.txt
└── src/
    ├── main.py
    └── templates/
        └── main.html
```

Plik **main.html**:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>htmx</title>
</head>
<body>
    <h1>htmx</h1>

</body>
</html>
```

Plik **main.py**:

```py
from flask import Flask
from flask import render_template, redirect, send_from_directory

app = Flask(__name__)

@app.route('/hello')
def hello():
    return "Hello World!"

@app.route('/')
def htmx():
    return render_template('main.html')

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=80)
```


## static

Dodaj:
```html
<body>
    <h1>htmx</h1>

    <img src="static/dog.png" alt="">
</body>
```

Dodaj:
```py
@app.route('/static/<path:path>')
def send_report(path):
    return send_from_directory('static', path)
```


## bootstrap

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css">

    <title>htmx</title>
</head>

<body>
    <h1>htmx</h1>

    <img src="static/dog.png" alt="">
    
    <button type="button" class="btn btn-primary">Primary</button>
</body>
```









## Serwowanie różnych adresów

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello():
    """http://127.0.0.1:5000"""
    return "Hello World!"

@app.route('/name')
def hello_name():
    """http://127.0.0.1:5000/name"""
    return "Hello World Rafał!"

if __name__ == '__main__':
    app.run() # domyślnie ip=127.0.0.1, port=5000
    #app.run(host='0.0.0.0', port=80)
```

Uruchomienie:
```bash
su
python app.py
```


## Serwowanie z szablonów html, css

Zawartość projektu:

```
app_web
├── templates
│   ├── main.css
│   └── main.html
└── app.py
```


**./templates/main.css**
```css
.button {
    background-color: #5bb5ff; 
    border: 2px solid #5bb5ff;
    color: #002849;
    padding: 16px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    transition-duration: 0.1s;
    cursor: pointer;
    border-radius: 5px;
    border: none;
    box-shadow: 0 7px #999;
    outline: none;
    border: 2px solid #5bb5ff;
  }
  
  .button:hover {
    background-color: #2ca0ff;
    border: 2px solid #007add;
    color: #000000;
  }
  
  .button:active {
    background-color: #2ca0ff;
    box-shadow: 0 5px #666;
    transform: translateY(2px);
  }
```

**./templates/main.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="/templates/main.css">
    <title>Ave DocMaker</title>
</head>
<body>
    <h2>Lista plików *.md</h2>
    Pliki *.md do konwersji (cd {{ in_folder }}):
    <ul>
        {% for item in md_files %}
        <li> {{ item }} </li>
        {% endfor %}
    </ul>
</body>
</html>
```

**./app.py**
```python
from flask import render_template
from flask import Flask, request, send_from_directory
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    if request.method == "GET":
        return render_template('main.html',
            in_folder = '', 
            md_files = ['file1', 'file2'])

if __name__ == '__main__':
    app.run() # domyślnie ip=127.0.0.1, port=5000
    #app.run(host='0.0.0.0', port=80)
```

### Uruchomienie
Uruchomienie:
```bash
su
python app.py
```

Inny sposób:

```bash
export FLASK_APP=app.py # domyślnie app.py
flask run
flask run --host=0.0.0.0  # domyślnie port=5000
```

Gunicorn:
```bash
python -m gunicorn -w 1 -b 0.0.0.0:80 --reload web:app

gunicorn -w 4 -b 0.0.0.0:5000 web:app
gunicorn -w 1 -b 0.0.0.0:5000 --reload web:app
```








## Deploy Linux

```bash
cd 87_flask
source .venv/bin/activate
cd src
gunicorn -w 4 -b 0.0.0.0:6060 main:app
killall gunicorn
```


## Docker

```

```


## nginx

