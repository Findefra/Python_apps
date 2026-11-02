# Common API List – Top Python Libraries

Ranked by real-world usage, PyPI downloads, and professional adoption (2026).

Each entry includes:
- `pip` install command
- Short, practical usage example

---

## Core / Most Used (1–25)

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

client = OpenAI()
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

img = Image.new("RGB", (100, 100), color="red")
img.save("red_square.png")
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

## Advanced / Professional Libraries (26–50)

### 26. kubernetes – Kubernetes Python Client
```bash
pip install kubernetes
```
```python
from kubernetes import client, config

config.load_kube_config()
v1 = client.CoreV1Api()
pods = v1.list_pod_for_all_namespaces()
print([p.metadata.name for p in pods.items[:5]])
```

### 27. azure-identity + azure-mgmt – Azure SDK
```bash
pip install azure-identity azure-mgmt-resource
```
```python
from azure.identity import DefaultAzureCredential
from azure.mgmt.resource import ResourceManagementClient

credential = DefaultAzureCredential()
client = ResourceManagementClient(credential, "<subscription-id>")
for rg in client.resource_groups.list():
    print(rg.name)
```

### 28. google-cloud-storage – Google Cloud Storage
```bash
pip install google-cloud-storage
```
```python
from google.cloud import storage

client = storage.Client()
buckets = list(client.list_buckets())
print([b.name for b in buckets])
```

### 29. polars – Fast DataFrame Library
```bash
pip install polars
```
```python
import polars as pl

df = pl.DataFrame({"name": ["Alice", "Bob"], "age": [25, 30]})
print(df.filter(pl.col("age") > 26))
```

### 30. langchain – LLM Application Framework
```bash
pip install langchain langchain-openai
```
```python
from langchain_openai import ChatOpenAI
from langchain_core.prompts import ChatPromptTemplate

llm = ChatOpenAI(model="gpt-4o-mini")
prompt = ChatPromptTemplate.from_template("Tell me a short fact about {topic}")
chain = prompt | llm
print(chain.invoke({"topic": "Kubernetes"}).content)
```

### 31. anthropic – Anthropic Claude API
```bash
pip install anthropic
```
```python
from anthropic import Anthropic

client = Anthropic()
message = client.messages.create(
    model="claude-sonnet-4-20250514",
    max_tokens=100,
    messages=[{"role": "user", "content": "Explain async Python in one sentence"}]
)
print(message.content[0].text)
```

### 32. celery – Distributed Task Queue
```bash
pip install celery
```
```python
from celery import Celery

app = Celery("tasks", broker="redis://localhost:6379/0")

@app.task
def add(x, y):
    return x + y

# result = add.delay(4, 6)
```

### 33. tenacity – Retry Library
```bash
pip install tenacity
```
```python
from tenacity import retry, stop_after_attempt, wait_fixed

@retry(stop=stop_after_attempt(3), wait=wait_fixed(2))
def might_fail():
    print("Trying...")
    raise Exception("Failed")
```

### 34. structlog – Structured Logging
```bash
pip install structlog
```
```python
import structlog

logger = structlog.get_logger()
logger.info("user_logged_in", user_id=42, ip="10.0.0.1")
```

### 35. rich – Beautiful Terminal Output
```bash
pip install rich
```
```python
from rich.console import Console
from rich.table import Table

console = Console()
table = Table(title="Servers")
table.add_column("Name")
table.add_column("Status")
table.add_row("web-01", "[green]healthy[/green]")
console.print(table)
```

### 36. typer – Modern CLI (built on Click)
```bash
pip install typer
```
```python
import typer

app = typer.Typer()

@app.command()
def hello(name: str = "World"):
    print(f"Hello {name}")

if __name__ == "__main__":
    app()
```

### 37. httpx + anyio – Advanced Async HTTP
```bash
pip install httpx anyio
```
```python
import httpx
import anyio

async def main():
    async with httpx.AsyncClient() as client:
        r = await client.get("https://httpbin.org/get")
        print(r.json())

anyio.run(main)
```

### 38. alembic – Database Migrations
```bash
pip install alembic
```
```python
# alembic init migrations
# alembic revision --autogenerate -m "create users table"
# alembic upgrade head
```

### 39. prometheus-client – Metrics
```bash
pip install prometheus-client
```
```python
from prometheus_client import Counter, start_http_server

REQUESTS = Counter("app_requests_total", "Total requests")
REQUESTS.inc()
start_http_server(8000)
```

### 40. opentelemetry-api – Observability
```bash
pip install opentelemetry-api opentelemetry-sdk
```
```python
from opentelemetry import trace
from opentelemetry.sdk.trace import TracerProvider

trace.set_tracer_provider(TracerProvider())
tracer = trace.get_tracer(__name__)

with tracer.start_as_current_span("my-operation"):
    print("Tracing...")
```

### 41. paramiko – SSH Client
```bash
pip install paramiko
```
```python
import paramiko

client = paramiko.SSHClient()
client.set_missing_host_key_policy(paramiko.AutoAddPolicy())
client.connect("example.com", username="user", password="pass")
stdin, stdout, stderr = client.exec_command("uptime")
print(stdout.read().decode())
client.close()
```

### 42. fabric – High-level SSH / Deployment
```bash
pip install fabric
```
```python
from fabric import Connection

c = Connection("user@example.com")
result = c.run("uname -a", hide=True)
print(result.stdout)
```

### 43. docker – Docker SDK
```bash
pip install docker
```
```python
import docker

client = docker.from_env()
containers = client.containers.list()
print([c.name for c in containers])
```

### 44. apache-airflow – Workflow Orchestration
```bash
pip install apache-airflow
```
```python
from airflow import DAG
from airflow.operators.python import PythonOperator
from datetime import datetime

def hello():
    print("Hello from Airflow")

with DAG("example", start_date=datetime(2026, 1, 1), schedule=None) as dag:
    PythonOperator(task_id="hello", python_callable=hello)
```

### 45. dask – Parallel Computing
```bash
pip install dask[complete]
```
```python
import dask.array as da

x = da.random.random((10000, 10000), chunks=(1000, 1000))
print(x.mean().compute())
```

### 46. ray – Distributed Computing & ML
```bash
pip install ray
```
```python
import ray

ray.init()

@ray.remote
def f(x):
    return x * x

futures = [f.remote(i) for i in range(4)]
print(ray.get(futures))
```

### 47. transformers – Hugging Face
```bash
pip install transformers
```
```python
from transformers import pipeline

classifier = pipeline("sentiment-analysis")
result = classifier("I love using advanced Python libraries!")
print(result)
```

### 48. litellm – Unified LLM API
```bash
pip install litellm
```
```python
from litellm import completion

response = completion(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": "Hello"}]
)
print(response.choices[0].message.content)
```

### 49. pydantic-settings – Settings Management
```bash
pip install pydantic-settings
```
```python
from pydantic_settings import BaseSettings

class Settings(BaseSettings):
    app_name: str = "MyApp"
    debug: bool = False

    class Config:
        env_file = ".env"

settings = Settings()
print(settings.app_name)
```

### 50. uvloop – High-performance Event Loop
```bash
pip install uvloop
```
```python
import asyncio
import uvloop

uvloop.install()  # replaces the default event loop

async def main():
    print("Running with uvloop")

asyncio.run(main())
```

---

## Quick Install Groups

**Core set:**
```bash
pip install boto3 requests numpy pandas pydantic fastapi uvicorn httpx redis sqlalchemy
```

**Advanced / DevOps / Cloud:**
```bash
pip install kubernetes docker paramiko fabric azure-identity google-cloud-storage prometheus-client opentelemetry-api structlog tenacity rich typer
```

**AI / LLM stack:**
```bash
pip install openai anthropic langchain langchain-openai transformers litellm
```
