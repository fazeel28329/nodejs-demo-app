# Node.js CI/CD Pipeline with GitHub Actions and Docker

## Project Overview

This project demonstrates a complete CI/CD pipeline for a Node.js web application using GitHub Actions and Docker.

Whenever code is pushed to the `main` branch, GitHub Actions automatically installs dependencies, runs tests, builds a Docker image, and pushes the image to Docker Hub.

## CI/CD Workflow

```text
Developer
   ↓
Git Push
   ↓
GitHub Repository
   ↓
GitHub Actions
   ↓
Install Dependencies
   ↓
Run Tests
   ↓
Build Docker Image
   ↓
Push Image to Docker Hub
```

## Technologies Used

- Node.js
- Express.js
- Git
- GitHub
- GitHub Actions
- Docker
- Docker Hub

## Project Structure

```text
nodejs-demo-app/
├── .github/
│   └── workflows/
│       └── main.yml
├── .dockerignore
├── .gitignore
├── Dockerfile
├── app.js
├── package.json
├── package-lock.json
└── README.md
```

## Run the Application Locally

Install dependencies:

```bash
npm install
```

Start the application:

```bash
npm start
```

Open:

```text
http://localhost:3000
```

## Run Tests

```bash
npm test
```

## Build Docker Image

```bash
docker build -t nodejs-demo-app .
```

## Run Docker Container

```bash
docker run -d -p 3000:3000 --name nodejs-demo-container nodejs-demo-app
```

Then open:

```text
http://localhost:3000
```

## CI/CD Pipeline

The GitHub Actions workflow is located at:

```text
.github/workflows/main.yml
```

The pipeline is triggered automatically whenever code is pushed to the `main` branch.

The pipeline performs the following operations:

1. Checks out the source code.
2. Sets up Node.js.
3. Installs project dependencies.
4. Runs application tests.
5. Logs in to Docker Hub securely using GitHub Secrets.
6. Builds the Docker image.
7. Pushes the Docker image to Docker Hub.

## GitHub Secrets

The pipeline uses the following repository secrets:

```text
DOCKERHUB_USERNAME
DOCKERHUB_TOKEN
```

Sensitive Docker Hub credentials are not stored directly in the source code.

## Docker Hub Image

Docker image:

```text
fazeelmuhammad283/nodejs-demo-app:latest
```

Pull the image using:

```bash
docker pull fazeelmuhammad283/nodejs-demo-app:latest
```

## Result

The CI/CD pipeline was successfully implemented and tested.

A push to the `main` branch automatically triggers GitHub Actions, which tests the Node.js application, builds its Docker image, and publishes the latest image to Docker Hub.