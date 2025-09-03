# vs-code-dev-env
VSCode setup, extensions, debugging, remote development workflows. 
Used in all other repos as development environment.

# 🛠️ VS Code Setup Guide for Python + Docker Projects

This guide helps you configure Visual Studio Code to work with Python-based RESTful applications and Docker containers.

---

## ✅ Prerequisites

- https://www.python.org/downloads/
- https://www.docker.com/products/docker-desktop/
- https://code.visualstudio.com/

---

## 🧩 Recommended VS Code Extensions

- **Python** (by Microsoft)  
- **Docker** (by Microsoft)  
- **REST Client** (by Huachao Mao)  
- **Markdown All in One** (optional)

---

## 📁 Project Structure

my-project/ 
├── app.py 
├── Dockerfile 
├── requirements.txt 
├── README.md 
└── .vscode/ 
    └── settings.json

---

## ⚙️ Example `.vscode/settings.json`

```json
{
  "python.pythonPath": "python3",
  "python.formatting.provider": "black",
  "editor.formatOnSave": true,
  "docker.dockerPath": "/usr/local/bin/docker"
}
________________________________________
🐳 Dockerfile Example
FROM python:3.10-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["python", "app.py"]
________________________________________
▶️ Run Locally
docker build -t my-app .
docker run -p 8080:8080 my-app
________________________________________
🧪 Test with REST Client
Create a file test.http:
GET http://localhost:8080/health
Click “Send Request” in VS Code to test your API.
________________________________________
📦 Publish to DockerHub
docker tag my-app yourusername/my-app
docker push yourusername/my-app
________________________________________
📚 Resources
•	https://code.visualstudio.com/docs/python/python-tutorial 
•	https://code.visualstudio.com/docs/containers/overview 

---

