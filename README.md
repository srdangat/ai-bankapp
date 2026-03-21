# Docker Setup for BankApp

## Manual Docker Setup (Step-by-Step)

### Create a Docker network
```bash
docker network create bankapp-net
```
---

### Create a Docker volume for MySQL data
```bash
docker volume create bankapp-mysql-data
```
---

### Create a Docker volume for Ollama models
```bash
docker volume create ollama-models
```
---

### Run MySQL container
```bash
docker run -d \
  --name bankapp-mysql \
  --network bankapp-net \
  -e MYSQL_ROOT_PASSWORD=Test@123 \
  -e MYSQL_DATABASE=bankappdb \
  -v bankapp-mysql-data:/var/lib/mysql \
  -p 3306:3306 \
  mysql:8.0
```
---

### Run Ollama container
```bash
docker run -d \
  --name bankapp-ollama \
  --network bankapp-net \
  -v ollama-models:/root/.ollama/models \
  -p 11434:11434 \
  ollama/ollama
```
---

### Pull the TinyLLaMA model for Ollama
```bash
docker exec -it bankapp-ollama ollama pull tinyllama
```
---

### Build BankApp Docker image
```bash
docker build -t bankapp:latest .
```
---

### Run BankApp container
```bash
docker run -d \
  --name bankapp \
  --network bankapp-net \
  -e MYSQL_HOST=bankapp-mysql \
  -e MYSQL_PORT=3306 \
  -e MYSQL_DATABASE=bankappdb \
  -e MYSQL_USER=root \
  -e MYSQL_PASSWORD=Test@123 \
  -e OLLAMA_URL=http://bankapp-ollama:11434 \
  -p 8080:8080 \
  bankapp:latest
```

---

## Run with Docker Compose (recommended)

### Start everything
```bash
docker compose up -d --build
```
---

`Visit http://localhost:8080`

### Why Use Docker Compose?

* Single command to start everything
* Easier networking (service names act as hostnames)
* Built-in dependency handling
---