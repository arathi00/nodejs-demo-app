## CI/CD Pipeline for Node.js Application

## Elevate Labs DevOps Internship – Task 1

This project demonstrates an automated CI/CD pipeline for a Node.js application using **GitHub Actions, Docker, and Docker Hub**.

## Objective

The objective of this task is to automate the process of:

**Test → Build Docker Image → Push to Docker Hub**

The pipeline is automatically triggered whenever code is pushed to the `main` branch.

## Technologies Used

* Node.js
* Express.js
* GitHub
* GitHub Actions
* Docker
* Docker Hub

## Project Structure

```text
nodejs-demo-app/
│
├── .github/
│   └── workflows/
│       └── main.yml
│
├── screenshots/
│
├── .dockerignore
├── .gitignore
├── Dockerfile
├── app.js
├── package-lock.json
├── package.json
└── test.js
```

## Application

The project contains a simple Node.js application built using Express.js.

The application provides the following endpoints:

### Home

```text
GET /
```

Displays a message confirming that the Node.js application is running.

### Health Check

```text
GET /health
```

Returns the health status of the application.

Example response:

```json
{
  "status": "healthy"
}
```

## Testing

The application includes a basic automated test using Node.js's built-in test framework.

The test can be executed locally using:

```bash
npm test
```

The test completed successfully before pushing the project to GitHub.

## Docker

The application is containerized using Docker.

The Docker image is built using the `Dockerfile`.

### Build Docker Image

```bash
docker build -t nodejs-demo-app .
```

### Run Docker Container

```bash
docker run -p 3000:3000 nodejs-demo-app
```

The application can then be accessed at:

```text
http://localhost:3000
```

## CI/CD Pipeline

The CI/CD workflow is defined in:

```text
.github/workflows/main.yml
```

The workflow is triggered whenever code is pushed to the `main` branch.

### Pipeline Steps

```text
Push code to main
       ↓
Checkout code
       ↓
Set up Node.js
       ↓
Install dependencies
       ↓
Run tests
       ↓
Login to Docker Hub
       ↓
Build Docker image
       ↓
Push image to Docker Hub
```

## GitHub Actions

GitHub Actions is used to automate the CI/CD process.

The workflow performs the following operations:

1. Checks out the source code.
2. Sets up Node.js.
3. Installs project dependencies.
4. Runs automated tests.
5. Authenticates with Docker Hub using GitHub Secrets.
6. Builds the Docker image.
7. Pushes the Docker image to Docker Hub.

## Docker Hub

The Docker image is published to:

```text
arathi00/nodejs-demo-app
```

The image is tagged as:

```text
latest
```

## Security

Docker Hub credentials are not stored directly in the source code.

The following GitHub repository secrets are used:

```text
DOCKERHUB_USERNAME
DOCKERHUB_TOKEN
```

The Docker Hub access token is stored securely as a GitHub Actions secret.

## Result

The GitHub Actions workflow completed successfully.

The pipeline successfully automated:

* Application testing
* Docker image building
* Docker Hub authentication
* Docker image publishing

This demonstrates a basic CI/CD workflow for a containerized Node.js application.

## Screenshots

Screenshots showing the application, testing, Docker build, GitHub Actions workflow, and Docker Hub image are included in the `screenshots/` directory.

## Learning Outcome

Through this task, I learned how to:

* Create and manage a GitHub repository
* Use Git for version control
* Create a Dockerfile
* Build and run a Docker container
* Create a GitHub Actions workflow
* Use GitHub Actions secrets
* Automate application testing
* Build Docker images through CI/CD
* Push Docker images to Docker Hub

## Internship Task

**Elevate Labs – DevOps Internship**

**Task 1: Automate Code Deployment Using CI/CD Pipeline (GitHub Actions)**
