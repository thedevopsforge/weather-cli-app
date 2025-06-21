# 🌦️ Weather CLI App

A simple Python-based CLI app that fetches the current weather for any city using the public API from [`wttr.in`](https://wttr.in).

This project demonstrates containerization with Docker and CI/CD automation with GitHub Actions, following DevOps best practices.

---

## 🚀 Features

- 🐍 Lightweight Python CLI app
- 🐳 Containerized with a minimal Docker base image (`python:3.9-slim`)
- 🔁 Automated build, test, and Docker push via GitHub Actions
- 🔐 Secure use of GitHub Secrets for Docker Hub credentials
- 🏷️ Versioned Docker images using Git commit SHA tags

---

## 🧪 Local Usage

Run directly using Python:

```bash
python app.py <city>
# Example
python app.py Lagos
````

---

## 🐳 Docker Usage

### Build the image locally:

```bash
docker build -t weather-cli-app .
```

### Run the container:

```bash
docker run weather-cli-app Cairo
```

---

## 🔄 GitHub Actions CI/CD Workflow

On every push to the `main` branch:

1. Builds the Docker image
2. Tags it with the **first 7 characters** of the Git commit SHA
3. Runs the container and tests it using a sample city (`London`)
4. Pushes the image to [Docker Hub](https://hub.docker.com/r/thedevopsforge/weather-cli-app)

GitHub Secrets used:

* `DOCKER_USERNAME`
* `DOCKER_PASSWORD`

---

## 🐳 Docker Hub Image

➡️ [Click here to view the Docker image on Docker Hub](https://hub.docker.com/r/thedevopsforge/weather-cli-app)

---

## 🧩 Project Structure

```
weather-cli-app/
├── app.py                  # CLI Application
├── Dockerfile              # Docker build instructions
├── .github/workflows/
│   └── ci.yml              # GitHub Actions CI/CD workflow
└── README.md               # Documentation
```

---

## ✅ Example Output

```bash
$ python app.py Nairobi
Nairobi: 🌦 +15°C
```

---

## 📄 License

MIT License. Feel free to fork, use, or extend.

---

