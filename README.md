# 🚀 Flask CI/CD Pipeline with Docker & GitHub Actions

This project demonstrates a simple CI/CD pipeline using:
- **Flask** as the web application
- **Docker** for containerization
- **GitHub Actions** for automation
- **EC2** for deployment via SSH

## 📁 Project Structure

```
.
├── Dockerfile          # Docker image definition
├── app.py              # Flask app
├── requirements.txt    # Python dependencies
├── test_app.py         # Unit test for Flask app
├── .github
│   └── workflows
│       └── main.yml    # CI/CD workflow
```

## ✅ Features

- 🐳 Docker container for the app
- ✅ Pytest-based unit testing
- 🔄 Automatic build and test on every push
- 🚀 Auto-deploy to EC2 using `appleboy/ssh-action`

## 📦 Docker Commands

```bash
# Build the image
docker build -t flask-cicd-app .

# Run the container
docker run -d -p 5000:5000 flask-cicd-app
```

## 🧪 Run Tests Locally

```bash
pip install -r requirements.txt
pytest test_app.py
```

## 🔐 GitHub Secrets Required

| Secret Name         | Description                             |
|---------------------|-----------------------------------------|
| `HOST`              | Public IP or DNS of your EC2 instance   |
| `HOST_SSH_KEY`      | Content of your EC2 private `.pem` key  |

## 🔄 CI/CD Workflow Steps

1. ✅ Checkout code
2. 🐍 Set up Python & install dependencies
3. 🔬 Run unit tests
4. 🐳 Build and push Docker image to Docker Hub
5. 🚀 SSH into EC2 and deploy the container

## 🌐 Access the App

After deployment, visit:

```bash
http://<your-ec2-ip>:5000
```

You should see:

```
🚀 Hello from Jenkins CI/CD Pipeline with Docker and Flask!
```

## 🙋‍♂️ Author

Made by [gnanajothit](https://github.com/gnanajothit)
