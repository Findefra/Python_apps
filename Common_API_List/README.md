# Common API List – Top 25 Most Used Python Libraries

Ranked by real-world usage, PyPI downloads, and developer adoption (2026).

Each entry includes:
- `pip` install command
- Short, practical usage example

---

### 1. boto3 – AWS SDK
```bash
pip install boto3
```
```python
import boto3

s3 = boto3.client("s3")
response = s3.list_buckets()
print([b["Name"] for b in response["Buckets"]])
```

### 2. requests – HTTP Client
```bash
pip install requests
```
```python
import requests

response = requests.get("https://api.github.com")
print(response.status_code)
print(response.json())
```

### 3. numpy – Numerical Computing
```bash
pip install numpy
```
```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])
print(arr.mean(), arr.std())
```

### 4. pandas – Data Analysis
```bash
pip install pandas
```
```python
import pandas as pd

df = pd.DataFrame({"name": ["Alice", "Bob"], "age": [25, 30]})
print(df.describe())
```

### 5. pydantic – Data Validation
```bash
pip install pydantic
```
```python
from pydantic import BaseModel

class User(BaseModel):
    name: str
    age: int

user = User(name="Alice", age=30)
print(user.model_dump())
```

### 6. fastapi – Modern API Framework
```bash
pip install fastapi uvicorn
```
```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def root():
    return {"message": "Hello World"}

# Run with: uvicorn main:app --reload
```

### 7. urllib3 – Low-level HTTP
```bash
pip install urllib3
```
```python
import urllib3

http = urllib3.PoolManager()
response = http.request("GET", "https://httpbin.org/get")
print(response.status)
```

### 8. botocore – AWS Core Library
```bash
pip install botocore
```
```python
import botocore.session

session = botocore.session.get_session()
client = session.create_client("s3")
print(client.meta.service_model.service_name)
```

### 9. pyyaml – YAML Parsing
```bash
pip install pyyaml
```
```python
import yaml

data = yaml.safe_load("""
name: Alice
age: 30
""")
print(data["name"])
```

### 10. python-dateutil – Date/Time Utilities
```bash
pip install python-dateutil
```
```python
from dateutil import parser
from dateutil.relativedelta import relativedelta
from datetime import datetime

dt = parser.parse("2026-11-02")
print(dt + relativedelta(months=1))
```

### 11. cryptography – Cryptographic Primitives
```bash
pip install cryptography
```
```python
from cryptography.fernet import Fernet

key = Fernet.generate_key()
f = Fernet(key)
token = f.encrypt(b"Secret message")
print(f.decrypt(token))
```

### 12. click – CLI Framework
```bash
pip install click
```
```python
import click

@click.command()
@click.option("--name", default="World")
def hello(name):
    click.echo(f"Hello, {name}!")

if __name__ == "__main__":
    hello()
```

### 13. pytest – Testing Framework
```bash
pip install pytest
```
```python
def add(a, b):
    return a + b

def test_add():
    assert add(2, 3) == 5

# Run with: pytest
```

### 14. sqlalchemy – SQL Toolkit & ORM
```bash
pip install sqlalchemy
```
```python
from sqlalchemy import create_engine, text

engine = create_engine("sqlite:///:memory:")
with engine.connect() as conn:
    result = conn.execute(text("SELECT 1"))
    print(result.scalar())
```

### 15. httpx – Modern HTTP Client
```bash
pip install httpx
```
```python
import httpx

response = httpx.get("https://api.github.com")
print(response.status_code)
print(response.json())
```

### 16. aiohttp – Async HTTP Client/Server
```bash
pip install aiohttp
```
```python
import aiohttp
import asyncio

async def main():
    async with aiohttp.ClientSession() as session:
        async with session.get("https://httpbin.org/get") as resp:
            print(await resp.json())

asyncio.run(main())
```

### 17. django – Full-stack Web Framework
```bash
pip install django
```
```python
# Create project
# django-admin startproject mysite
# python manage.py runserver

# Example view (views.py)
from django.http import JsonResponse

def home(request):
    return JsonResponse({"message": "Hello from Django"})
```

### 18. flask – Lightweight Web Framework
```bash
pip install flask
```
```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return {"message": "Hello from Flask"}

if __name__ == "__main__":
    app.run(debug=True)
```

### 19. scikit-learn – Machine Learning
```bash
pip install scikit-learn
```
```python
from sklearn.linear_model import LinearRegression
import numpy as np

X = np.array([[1], [2], [3], [4]])
y = np.array([2, 4, 6, 8])

model = LinearRegression().fit(X, y)
print(model.predict([[5]]))
```

### 20. torch (PyTorch) – Deep Learning
```bash
pip install torch
```
```python
import torch

x = torch.tensor([1.0, 2.0, 3.0])
y = torch.tensor([4.0, 5.0, 6.0])
print(torch.dot(x, y))
```

### 21. openai – OpenAI API Client
```bash
pip install openai
```
```python
from openai import OpenAI

client = OpenAI()  # uses OPENAI_API_KEY env var

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": "Say hello in one sentence"}]
)
print(response.choices[0].message.content)
```

### 22. pillow – Image Processing
```bash
pip install pillow
```
```python
from PIL import Image

# Create a simple image
img = Image.new("RGB", (100, 100), color="red")
img.save("red_square.png")
print(img.size)
```

### 23. beautifulsoup4 – HTML/XML Parsing
```bash
pip install beautifulsoup4
```
```python
from bs4 import BeautifulSoup

html = "<html><body><h1>Hello</h1></body></html>"
soup = BeautifulSoup(html, "html.parser")
print(soup.h1.text)
```

### 24. selenium – Browser Automation
```bash
pip install selenium
```
```python
from selenium import webdriver
from selenium.webdriver.chrome.options import Options

options = Options()
options.add_argument("--headless")
driver = webdriver.Chrome(options=options)

driver.get("https://example.com")
print(driver.title)
driver.quit()
```

### 25. redis – Redis Client
```bash
pip install redis
```
```python
import redis

r = redis.Redis(host="localhost", port=6379, decode_responses=True)
r.set("key", "value")
print(r.get("key"))
```

---

## Quick Install All (optional)

```bash
pip install boto3 requests numpy pandas pydantic fastapi uvicorn pyyaml python-dateutil cryptography click pytest sqlalchemy httpx aiohttp django flask scikit-learn torch openai pillow beautifulsoup4 selenium redis
```

> **Note**: Some packages (especially `torch`, `selenium`, and AWS libraries) have additional system or environment requirements.
