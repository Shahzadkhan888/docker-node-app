## 🚀 Live Demo
Check out the live application here: [http://51.102.248.62:3000](http://51.102.248.62:3000)

## 🛠️ The Project
This is a full-stack application with a React frontend and a Node.js backend. The goal of this project was to demonstrate a complete DevOps pipeline:
1. **Containerization**: Using a Multi-Stage Dockerfile to optimize image size.
2. **Registry**: Pushing the image to Docker Hub.
3. **Cloud Deployment**: Pulling and running the container on an AWS EC2 instance.

## 🏗️ Docker Architecture
I implemented a **Multi-Stage Build** to keep the production image lean:
- **Build Stage**: Compiles React source code.
- **Run Stage**: Serves the API and static assets via Node.js.

## 📦 How to Run Locally
```bash
docker pull shahzadk1/make:v1
docker run -p 3000:3080 shahzadk1/make:v1	
