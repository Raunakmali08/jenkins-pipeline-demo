# Jenkins CI/CD Pipeline Demo 🚀

This is a simple DevOps project to demonstrate how to set up a Jenkins CI/CD pipeline to build and deploy a Dockerized Flask application.

---

## 📌 Project Overview

This project automates the process of:
- 🛠 Building a Docker image for a Flask app
- 🚀 Running the container using Jenkins pipeline
- ✅ Triggering the pipeline on code commits

---

## 🧰 Tech Stack

- Python 3.10 (Flask)
- Docker
- Jenkins (Declarative Pipeline)
- GitHub (SCM)

---

## 📁 Folder Structure

jenkins-pipeline-demo/
│
├── app.py
├── Dockerfile
├── Jenkinsfile
└── README.md


---

## ⚙️ How the Jenkins Pipeline Works

### 🔸 Jenkinsfile
The `Jenkinsfile` contains the CI/CD stages:

```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker Image...'
                sh 'docker build -t flask-jenkins-app .'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Running Docker Container...'
                sh 'docker run -d -p 5000:5000 --name flask-jenkins-container flask-jenkins-app || true'
            }
        }
    }
}

---

🧪 Test It Locally
Build the Docker Image
docker build -t flask-jenkins-app .

---

Run the Flask App
docker run -d -p 5000:5000 --name flask-jenkins-container flask-jenkins-app

Visit 👉 http://localhost:5000
You should see:
Hello from Jenkins Pipeline!

---

📎 Useful Commands
# Check running containers
docker ps

# Stop the container
docker stop flask-jenkins-container

# Remove container
docker rm flask-jenkins-container

# Remove image
docker rmi flask-jenkins-app


---

### ✅ Final Steps:

1. Save that as `README.md` in your project folder.
2. Run these commands to update GitHub:

```bash
git add README.md
git commit -m "Add README.md for Jenkins pipeline demo"
git push

✅ Author
👨‍💻 Raunak Mali

🔗 LinkedIn

🐙 GitHub

