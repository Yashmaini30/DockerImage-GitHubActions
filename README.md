# CI/CD for Docker Flask App

This repository includes a **CI/CD pipeline** using **GitHub Actions** to automate testing, building, and publishing a Flask application Docker image to DockerHub.

## 📌 CI/CD Workflow Details

This workflow consists of two jobs:

1. **Build and Test:**

   - Runs on every push and pull request to the `main` branch.
   - Sets up a Python environment and installs dependencies.
   - Runs tests using `pytest`.

2. **Build and Publish:**

   - Runs only if the **Build and Test** job succeeds.
   - Builds and pushes a Docker image to DockerHub.
   - Uses `docker/login-action` for authentication.

## 🚀 Deploying the Application
The application is automatically built and published as a Docker image using GitHub Actions. Instead of manually building the image, you can simply **pull and run the latest version** from DockerHub.

### ✅ Pulling and Running the Container

*Docker image successfully pushed to DockerHub.*
![Screenshot 2025-03-29 165200](https://github.com/user-attachments/assets/b89616ec-6394-40d6-9d8b-118e4683d550)

Once the Docker image is published, you can run it locally using:

```bash
# Pull the latest image from DockerHub
docker pull ${{ secrets.DOCKERHUB_USERNAME }}/flask-app:latest

# Run the container
docker run -p 5000:5000 ${{ secrets.DOCKERHUB_USERNAME }}/flask-app:latest
```

![Screenshot 2025-03-29 165459](https://github.com/user-attachments/assets/f6cf5290-5d26-4782-8adf-ea284e1e38e5)

This eliminates the need to manually build the image, as the CI/CD pipeline handles that automatically.

## 📂 Project Structure

This repository follows a structured format:

```
.
├── app.py             # Flask application code
├── test_app.py        # Unit tests using pytest
├── DOCKERFILE            # Dockerfile for containerizing the app
├── requirements.txt       # Dependencies for the application
├── .github/
│   ├── workflows/
│       ├── cicd.yml  # GitHub Actions workflow
└── README.md              # Documentation
```

## 🖼️ CI/CD Workflow Screenshots

Here are some screenshots of the GitHub Actions workflow:

*GitHub Actions workflow execution.*

![Screenshot 2025-03-29 164906](https://github.com/user-attachments/assets/8d5a904b-0315-46fb-800e-29365f29fe1e)

---
![Screenshot 2025-03-29 164936](https://github.com/user-attachments/assets/9a491a97-2c7c-4abb-9498-c31e005eeeab)

---
![Screenshot 2025-03-29 164947](https://github.com/user-attachments/assets/2884ad52-e2ef-4cab-944f-5198dafac6f0)

---

## ✅ CI/CD Status

Once the workflow runs, you can check the status in the **Actions** tab of your GitHub repository.
---
![Screenshot 2025-03-29 164850](https://github.com/user-attachments/assets/30f8da4c-89ff-4a0f-8031-743eb5f93303)

---

💡 *This ensures automated testing and deployment of the Flask application using Docker!* 🚀

![Screenshot 2025-03-29 165521](https://github.com/user-attachments/assets/fef7ee7a-dd27-4cb3-9654-bc4418a37619)

﻿# DockerImage-GitHubActions
