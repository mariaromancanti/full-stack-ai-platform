# Full-Stack AI Platform

A collaborative full-stack AI application designed to provide a web interface for interacting with locally deployed Large Language Models.

The platform combines a modern **Next.js frontend**, a **Django REST API**, **PostgreSQL**, **Docker**, and **Ollama** to create a complete environment for running and interacting with local AI models.

---

## Overview

This project was developed as part of the **DAS (Software Application Development)** course at ICAI School of Engineering.

The objective was to design and implement a complete full-stack application integrating:

- AI-powered conversational services
- User authentication
- REST API communication
- Persistent data storage
- Modern frontend development
- Containerized infrastructure

The application allows users to interact with locally hosted language models through a web-based chat interface while managing authentication, conversations and application data through a Django backend.

---

## Key Features

- AI-powered chat interface
- Local Large Language Model integration through Ollama
- User authentication using JWT
- Persistent conversation management
- REST API architecture
- Modern responsive frontend
- PostgreSQL database integration
- Dockerized development environment
- Multi-service orchestration with Docker Compose
- Configurable local AI models

---

## Technology Stack

### Frontend

- Next.js
- React
- JavaScript
- Material UI
- Tailwind CSS

### Backend

- Python
- Django
- Django REST Framework
- JWT Authentication

### Artificial Intelligence

- Ollama
- Llama 3.2
- Support for configurable local language models

### Database

- PostgreSQL

### Infrastructure

- Docker
- Docker Compose

---

## System Architecture

```text
                         ┌─────────────────────┐
                         │      User / Web     │
                         │       Browser       │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │      Next.js        │
                         │      Frontend       │
                         │      Port 3000      │
                         └──────────┬──────────┘
                                    │
                                    │ REST API
                                    ▼
                         ┌─────────────────────┐
                         │       Django        │
                         │      REST API       │
                         │      Port 8000      │
                         └───────┬─────┬───────┘
                                 │     │
                     ┌───────────┘     └───────────┐
                     ▼                             ▼
          ┌─────────────────────┐       ┌─────────────────────┐
          │     PostgreSQL      │       │       Ollama        │
          │      Database       │       │    Local LLMs       │
          │      Port 5432      │       │     Port 11434      │
          └─────────────────────┘       └─────────────────────┘
```

---

## Repository Structure

```text
.
├── frontend/
│   ├── app/
│   ├── components/
│   ├── Dockerfile
│   └── package.json
│
├── backend/
│   ├── restApi/
│   ├── Dockerfile
│   └── pyproject.toml
│
├── docker-compose.yml
├── .env.example
├── .gitignore
└── README.md
```

---

## Main Components

### Frontend

The frontend is built using **Next.js and React**.

It provides the main user interface of the application, including authentication, navigation and interaction with the AI chat functionality.

---

### Backend

The backend is implemented using **Django and Django REST Framework**.

It provides REST API endpoints responsible for:

- authentication;
- user management;
- conversation management;
- communication with the AI service;
- database operations.

JWT is used to manage authentication between the frontend and backend.

---

### AI Service

The application integrates **Ollama** to run Large Language Models locally.

The default configuration uses:

```text
llama3.2:3b
```

The model can be changed through environment variables without modifying the application code.

Other Ollama-compatible models can also be configured.

---

### Database

**PostgreSQL** is used for persistent application data.

The database is deployed as an independent Docker service and communicates directly with the Django backend.

---

## Getting Started

### Prerequisites

The easiest way to run the complete platform is using:

- Docker
- Docker Compose

---

### 1. Clone the Repository

```bash
git clone https://github.com/mariaromancanti/full-stack-ai-platform.git
cd full-stack-ai-platform
```

---

### 2. Configure Environment Variables

Create a local `.env` file using the provided template:

```bash
cp .env.example .env
```

Update the values according to your local environment if necessary.

> The `.env` file is intentionally excluded from version control.

---

### 3. Start the Platform

```bash
docker-compose up -d
```

Docker Compose will start the required services:

- frontend;
- backend;
- PostgreSQL;
- Ollama.

---

### 4. Access the Application

Once all services are running:

```text
Frontend        http://localhost:3000
Backend API     http://localhost:8000
API Docs        http://localhost:8000/api/docs/
Django Admin    http://localhost:8000/admin
Ollama API      http://localhost:11434
```

---

## AI Model Configuration

The AI model can be configured through the local `.env` file.

Example:

```bash
OLLAMA_MODELS=llama3.2:3b
OLLAMA_MODEL=llama3.2:3b
```

Different Ollama-compatible models can be used depending on the available computational resources.

---

## Running Individual Services

The complete platform can be started with:

```bash
docker-compose up -d
```

To inspect the running services:

```bash
docker-compose ps
```

To view logs:

```bash
docker-compose logs -f
```

To stop the platform:

```bash
docker-compose down
```

---

## Security

Sensitive configuration is managed through environment variables.

The repository contains an `.env.example` template, while actual `.env` files are excluded from version control.

For a production deployment, additional measures would include:

- secure secret management;
- production database credentials;
- `DEBUG=False`;
- restricted `ALLOWED_HOSTS`;
- production CORS configuration;
- HTTPS;
- secure authentication and deployment infrastructure.

---

## Project Highlights

This project demonstrates the integration of several areas of software and AI engineering within a single application:

- Full-stack application development
- REST API design
- Authentication systems
- Local LLM integration
- Database design and persistence
- Containerization
- Multi-service architectures
- Frontend-backend communication
- Collaborative software development

---

## Future Improvements

Potential future extensions include:

- Retrieval-Augmented Generation (RAG)
- Cloud deployment
- Model selection from the frontend
- Streaming AI responses
- Conversation analytics
- Vector database integration
- Automated testing and CI/CD
- Monitoring and observability
- Role-based access control
- Cloud-based model inference

---

## Academic Context

Developed as part of the **DAS course** within the **Mathematical Engineering and Artificial Intelligence** program at **ICAI School of Engineering – Universidad Pontificia Comillas**.

---

## Collaboration

This project was developed collaboratively by:

**María Román Cantillana**  
Mathematical Engineering & Artificial Intelligence  
ICAI School of Engineering

**Lucía Tamarit**

The original development history and individual contributions are preserved in the Git commit history.

---

## Author Profile

**María Román Cantillana**

Mathematical Engineering & Artificial Intelligence  
ICAI School of Engineering – Universidad Pontificia Comillas

GitHub: [mariaromancanti](https://github.com/mariaromancanti)
