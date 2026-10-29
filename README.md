# Project 2: Containerize and Run Locally

This repository contains a multi-stage Docker containerized web application (web), an isolated caching service (cache), and a locally invocable serverless function handler (local-fn).

## Prerequisites
- Docker Engine (WSL 2 / Linux) with Docker Compose v2
- AWS SAM CLI

## Quick Start & Verification Instructions

Clone the repository and run the following commands in order:

1. Build and Run the Compose Stack:
   docker compose up -d

2. Verify Services Are Running:
   docker compose ps
   curl -s -o /dev/null -w "%{http_code}\n" http://localhost:8080

3. Clean Up the Stack:
   docker compose down

4. Invoke the Local AWS SAM Function:
   cd local-fn
   sam local invoke HelloWorldFunction
   cd ..
