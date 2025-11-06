# CI-CD-Pipeline-with-GitHub-Actions-Docker-No-Cloud-Needed-
This project demonstrates a Continuous Integration and Continuous Deployment (CI/CD) pipeline using GitHub Actions and Docker, built and deployed locally — with no cloud services required.

🧩 Features

Automates the build → test → push process using GitHub Actions

Builds and pushes Docker image to Docker Hub automatically

Uses GitHub Secrets for secure Docker Hub authentication

Supports local deployment using Docker

⚙️ Technologies Used

Node.js (Express) — Simple web server

Docker — Containerization

GitHub Actions — CI/CD automation

Docker Hub — Image registry

📁 Project Structure
ci-cd-docker-actions/
├── app/
│   ├── server.js
│   └── package.json
├── docker-compose.yml
├── .github/
│   └── workflows/
│       └── ci-cd.yml
└── README.md

🧠 Workflow File (.github/workflows/ci-cd.yml)
name: CI/CD Pipeline with Docker Hub

on:
  push:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Code
        uses: actions/checkout@v4

      - name: Build Docker Image
        run: docker build -t ${{ secrets.DOCKER_USERNAME }}/cicd-demo:latest ./app

      - name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}

      - name: Push Docker Image
        run: docker push ${{ secrets.DOCKER_USERNAME }}/cicd-demo:latest

🧪 Run the App Locally

To pull and run your image from Docker Hub:

docker pull jayasri4002/cicd-demo:latest
docker run -d -p 3000:3000 jayasri4002/cicd-demo:latest


Then open in your browser:
👉 http://localhost:3000

Expected Output:

Hello from CI/CD Pipeline with GitHub Actions & Docker!

📸 Screenshots
Step	Description	Screenshot
1️⃣	GitHub Actions CI/CD Workflow Success	✅ Upload your Actions success image here
2️⃣	Docker Hub Repository showing image	✅ Upload your Docker Hub image proof
3️⃣	Local App Running on Port 3000	✅ Upload your localhost screenshot
📦 Deliverables

✅ GitHub repository with working workflow
✅ Docker Hub image: jayasri4002/cicd-demo

✅ Successful GitHub Actions build logs
✅ Screenshot of running app locally

🧾 Summary

This project automates the full DevOps pipeline — from source code to Docker image deployment — using GitHub Actions and Docker Hub.
It demonstrates practical CI/CD concepts, automation, and containerization — essential for modern software delivery.

👩‍💻 Developed by:

Yakkala Jayasri
GitHub: Jayasri98494

Docker Hub: jayasri4002
