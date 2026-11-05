# ⚡ Task-Queue-Processor

A high-performance, asynchronous background task processing microservice built with **FastAPI**, **Celery**, and **Redis**, orchestrated using **Docker Compose**. Designed to offload heavy operations from primary API handlers for scalable backend architecture.

---

### 🛠️ Tech Stack & Tools

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=flat-square&logo=celery&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)

---

### 🏗️ Architecture Overview

```text
 Client Request ──> [ FastAPI Router ] ──(Enqueue Task)──> [ Redis Broker ]
                                                                   │
 Client Polling <── [ Result Store ] <──(Save Result)─── [ Celery Worker ]