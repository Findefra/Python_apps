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

### 36. typer – Modern CLI
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

uvloop.install()

async def main():
    print("Running with uvloop")

asyncio.run(main())
```

---

## Specialized / Expert-Level Libraries (51–75)

### 51. pulumi – Infrastructure as Code (Python)
```bash
pip install pulumi pulumi-aws
```
```python
import pulumi
import pulumi_aws as aws

bucket = aws.s3.Bucket("my-bucket")
pulumi.export("bucket_name", bucket.id)
```

### 52. cdktf – Terraform CDK for Python
```bash
pip install cdktf cdktf-cdktf-provider-aws
```
```python
from cdktf import App, TerraformStack
from constructs import Construct
from cdktf_cdktf_provider_aws.provider import AwsProvider
from cdktf_cdktf_provider_aws.s3_bucket import S3Bucket

class MyStack(TerraformStack):
    def __init__(self, scope: Construct, id: str):
        super().__init__(scope, id)
        AwsProvider(self, "AWS", region="us-east-1")
        S3Bucket(self, "bucket", bucket="my-cdktf-bucket")

app = App()
MyStack(app, "python-aws")
app.synth()
```

### 53. boto3 + aioboto3 – Async AWS
```bash
pip install aioboto3
```
```python
import aioboto3
import asyncio

async def main():
    session = aioboto3.Session()
    async with session.client("s3") as s3:
        response = await s3.list_buckets()
        print([b["Name"] for b in response["Buckets"]])

asyncio.run(main())
```

### 54. moto – AWS Mocking / Testing
```bash
pip install moto[all]
```
```python
from moto import mock_aws
import boto3

@mock_aws
def test_s3():
    s3 = boto3.client("s3", region_name="us-east-1")
    s3.create_bucket(Bucket="test-bucket")
    print(s3.list_buckets())
```

### 55. localstack – Local AWS Cloud Emulator
```bash
pip install localstack
```
```python
# Start with: localstack start
# Then point boto3 to http://localhost:4566
import boto3

s3 = boto3.client("s3", endpoint_url="http://localhost:4566")
s3.create_bucket(Bucket="local-bucket")
```

### 56. great-expectations – Data Quality
```bash
pip install great-expectations
```
```python
import great_expectations as gx

context = gx.get_context()
validator = context.sources.pandas_default.read_csv("data.csv")
validator.expect_column_values_to_not_be_null("id")
```

### 57. prefect – Modern Workflow Orchestration
```bash
pip install prefect
```
```python
from prefect import flow, task

@task
def say_hello(name: str):
    print(f"Hello {name}")

@flow
def hello_flow():
    say_hello("World")

hello_flow()
```

### 58. dagster – Data Orchestration
```bash
pip install dagster
```
```python
from dagster import asset, materialize

@asset
def hello_asset():
    return "Hello from Dagster"

materialize([hello_asset])
```

### 59. llama-index – RAG Framework
```bash
pip install llama-index
```
```python
from llama_index.core import VectorStoreIndex, SimpleDirectoryReader

documents = SimpleDirectoryReader("data").load_data()
index = VectorStoreIndex.from_documents(documents)
query_engine = index.as_query_engine()
print(query_engine.query("What is this about?"))
```

### 60. crewai – Multi-Agent AI Systems
```bash
pip install crewai
```
```python
from crewai import Agent, Task, Crew

researcher = Agent(
    role="Researcher",
    goal="Find accurate information",
    backstory="Expert researcher"
)

task = Task(description="Research Python async", agent=researcher)
crew = Crew(agents=[researcher], tasks=[task])
result = crew.kickoff()
```

### 61. semantic-kernel – Microsoft AI Orchestration
```bash
pip install semantic-kernel
```
```python
import semantic_kernel as sk
from semantic_kernel.connectors.ai.open_ai import OpenAIChatCompletion

kernel = sk.Kernel()
kernel.add_service(OpenAIChatCompletion(ai_model_id="gpt-4o-mini"))
```

### 62. guardrails-ai – LLM Output Validation
```bash
pip install guardrails-ai
```
```python
from guardrails import Guard
from guardrails.hub import RegexMatch

guard = Guard().use(RegexMatch(regex="^[A-Z].*"))
result = guard.parse("Hello world")
```

### 63. instructor – Structured LLM Outputs
```bash
pip install instructor
```
```python
import instructor
from openai import OpenAI
from pydantic import BaseModel

class User(BaseModel):
    name: str
    age: int

client = instructor.from_openai(OpenAI())
user = client.chat.completions.create(
    model="gpt-4o-mini",
    response_model=User,
    messages=[{"role": "user", "content": "Extract: Alice is 30"}]
)
print(user)
```

### 64. chromadb – Vector Database
```bash
pip install chromadb
```
```python
import chromadb

client = chromadb.Client()
collection = client.create_collection("docs")
collection.add(documents=["Python is great"], ids=["1"])
results = collection.query(query_texts=["Python"], n_results=1)
print(results)
```

### 65. qdrant-client – Vector Search
```bash
pip install qdrant-client
```
```python
from qdrant_client import QdrantClient
from qdrant_client.models import Distance, VectorParams

client = QdrantClient(":memory:")
client.create_collection(
    collection_name="test",
    vectors_config=VectorParams(size=4, distance=Distance.COSINE)
)
```

### 66. netmiko – Network Device Automation
```bash
pip install netmiko
```
```python
from netmiko import ConnectHandler

device = {
    "device_type": "cisco_ios",
    "host": "192.168.1.1",
    "username": "admin",
    "password": "password"
}

with ConnectHandler(**device) as conn:
    output = conn.send_command("show ip interface brief")
    print(output)
```

### 67. napalm – Network Automation Abstraction
```bash
pip install napalm
```
```python
from napalm import get_network_driver

driver = get_network_driver("eos")
device = driver("192.168.1.1", "admin", "password")
device.open()
print(device.get_facts())
device.close()
```

### 68. scrapy – Advanced Web Scraping Framework
```bash
pip install scrapy
```
```python
import scrapy

class QuotesSpider(scrapy.Spider):
    name = "quotes"
    start_urls = ["https://quotes.toscrape.com"]

    def parse(self, response):
        for quote in response.css("div.quote"):
            yield {"text": quote.css("span.text::text").get()}
```

### 69. playwright – Modern Browser Automation
```bash
pip install playwright
playwright install
```
```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch()
    page = browser.new_page()
    page.goto("https://example.com")
    print(page.title())
    browser.close()
```

### 70. locust – Load Testing
```bash
pip install locust
```
```python
from locust import HttpUser, task, between

class WebsiteUser(HttpUser):
    wait_time = between(1, 3)

    @task
    def index(self):
        self.client.get("/")
```

### 71. hypothesis – Property-Based Testing
```bash
pip install hypothesis
```
```python
from hypothesis import given, strategies as st

@given(st.integers(), st.integers())
def test_addition_commutative(a, b):
    assert a + b == b + a
```

### 72. freethreaded / concurrent.futures advanced patterns
```bash
# Standard library + optional
pip install concurrent-log-handler
```
```python
from concurrent.futures import ThreadPoolExecutor, ProcessPoolExecutor

def work(x):
    return x * x

with ThreadPoolExecutor(max_workers=4) as executor:
    results = list(executor.map(work, range(10)))
print(results)
```

### 73. orjson – Ultra-fast JSON
```bash
pip install orjson
```
```python
import orjson

data = {"name": "Alice", "age": 30}
encoded = orjson.dumps(data)
print(orjson.loads(encoded))
```

### 74. msgspec – High-performance Serialization
```bash
pip install msgspec
```
```python
import msgspec

class User(msgspec.Struct):
    name: str
    age: int

user = User(name="Alice", age=30)
print(msgspec.json.encode(user))
```

### 75. cython – Python to C Compiler
```bash
pip install cython
```
```python
# example.pyx
# def add(int a, int b):
#     return a + b

# Compile with: cythonize -i example.pyx
```

---

## Quick Install Groups

**Core set:**
```bash
pip install boto3 requests numpy pandas pydantic fastapi uvicorn httpx redis sqlalchemy
```

**Advanced / DevOps / Cloud:**
```bash
pip install kubernetes docker paramiko fabric azure-identity google-cloud-storage prometheus-client opentelemetry-api structlog tenacity rich typer aioboto3 moto
```

**AI / LLM / Agents stack:**
```bash
pip install openai anthropic langchain langchain-openai transformers litellm llama-index crewai instructor chromadb
```

**Specialized / Expert:**
```bash
pip install pulumi prefect dagster great-expectations playwright locust hypothesis orjson msgspec netmiko
```
