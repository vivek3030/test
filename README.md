<h1 align="center">Hi 👋, I'm vivek kasundra</h1>
<h3 align="center">A beginner DevOps engineer from Germany</h3>

- 🔭 I’m currently working on **Python-Flask**

- 🌱 I’m currently learning **how to build CI-CD pipeline**

# Flask Application with CI/CD Pipeline

This repository contains a Flask application integrated with a CI/CD pipeline using Jenkins. The application is automatically built, tested, and deployed to a Kubernetes cluster managed by Minikube.

## Features

- Flask application for web services
- Continuous Integration and Continuous Deployment using Jenkins
- Kubernetes deployment using Minikube

## Prerequisites

Before running or deploying this project, ensure the following are installed:

1. **Python 3.8+**
   - Flask framework
   - Required dependencies (see `requirements.txt`)
2. **Docker**
   - For containerizing the application
3. **Minikube**
   - For running Kubernetes locally
4. **Jenkins**
   - For CI/CD automation

## Project Structure

```
.
├── app.py               # Main Flask application
├── Dockerfile           # Dockerfile for containerizing the app
├── requirements.txt     # Python dependencies
├── deployment.yaml      # Kubernetes Deployment and Service configuration
├── Jenkinsfile          # Jenkins pipeline definition
└── README.md            # Project documentation
```

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/vivek3030/test.git
cd test
```

### 2. Set Up Flask Application

Install the required Python packages:

```bash
pip install -r requirements.txt
```

Run the Flask application locally:

```bash
python app.py
```

The app will be available at `http://127.0.0.1:5000/`.

### 3. Dockerize the Application

Build the Docker image:

```bash
docker build -t <your-dockerhub-username>/flask-app:latest .
```

Run the Docker container:

```bash
docker run -p 5000:5000 <your-dockerhub-username>/flask-app:latest
```

### 4. Kubernetes Deployment

Start Minikube:

```bash
minikube start
```

Apply the Kubernetes configuration:

```bash
kubectl apply -f deployment.yaml
```

Access the application via Minikube’s service:

```bash
minikube service flask-app
```

### 5. CI/CD Pipeline with Jenkins

#### Jenkins Configuration

1. Install the required plugins in Jenkins:
   - GitHub Integration Plugin
   - Kubernetes CLI Plugin
   - Docker Pipeline Plugin
2. Configure a Jenkins pipeline job using the `Jenkinsfile` in this repository.
3. Set up a GitHub webhook to trigger builds automatically.

#### Pipeline Stages

- **Checkout Code**: Clone the repository from GitHub.
- **Build Docker Image**: Build and push the Docker image to a container registry.
- **Deploy to Kubernetes**: Apply Kubernetes manifests to deploy the application to Minikube.

## Useful Commands

- **Check Kubernetes Pods**:

  ```bash
  kubectl get pods
  ```

- **View Jenkins Logs**:

  ```bash
  docker logs jenkins
  ```

- **Minikube Dashboard**:

  ```bash
  minikube dashboard
  ```

## Troubleshooting

- **Pipeline Errors**:
  Check the Jenkins console output for detailed error logs.
- **Kubernetes Issues**:
  Ensure Minikube is running and accessible.
- **Permission Denied Errors**:
  Verify user permissions for Docker and Kubernetes commands.

## Virtual Environment

If you are running jenkins on your VM's.
Then use ngrox server to host your localhost jenkins.

```bash
  systemctl status jenkins
```

```bash
  ngrox http 8080
```

Then update your GitHub webhook with the above link.
sample : link/github-webhook/

Before commiting to the repository, Check and minikube is running

```bash
  minikube status
```
## Author

**Vivek Kasundra**
