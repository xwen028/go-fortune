# 🥠 Go-Fortune App: CI/CD Workshop Project

This repository contains a Golang-based web application developed as part of the **DipSA 58 CI/CD Workshop** at NUS-ISS. The project demonstrates modern DevOps practices through the construction of a complete CI/CD pipeline with GitHub Actions.

---

## 📦 Project Overview

The app serves randomized "fortune" messages and supports:

- 🖥️ **REST API & MVC web view** using `Gin` and `GoView`
- ✍️ Add/Delete new fortunes through API
- ⚙️ Configurable via CLI flags: `--fortune`, `--static`, and `--port`

---

## 🚀 CI/CD Pipeline Highlights

Using GitHub Actions, the automated pipeline performs:

- ✅ **Code scanning** using [Trivy](https://github.com/aquasecurity/trivy)
- 🐳 **Docker containerization** with Git commit as tag
- ☁️ **Image push** to Docker Hub
- 🔐 **Image signing** via [Cosign](https://github.com/sigstore/cosign)
- 💬 **Slack integration** for build success/failure notifications
- 🚫 **Conditional trigger**: ignores commits with `#NORUN`

---

## 🔧 Command Line Options

| Option      | Description                        | Default       |
|-------------|------------------------------------|---------------|
| `--fortune` | Fortune file, one fortune per line | `./fortune.txt` |
| `--static`  | Static assets directory            | `./static`      |
| `--port`    | Port to bind to                    | `3000`          |

---

## 🗂️ Project Structure

- `main.go`: Application logic and HTTP routes
- `fortune.txt`: Random messages served to users
- `.github/workflows/`: CI/CD automation scripts
- `Dockerfile`: Instructions for containerization
- `cosign.pub`: Public key for image verification

---

## 🔐 Verifying Docker Image

After deployment, verify the image using Cosign:

```bash
cosign verify --key cosign.pub ghcr.io/chukmunnlee/go-fortune:<tag>
```

---

## 📚 Learning Outcome

This workshop strengthened my practical skills in containerization, CI/CD automation, secure DevOps practices, and cloud-native deployment pipelines.
