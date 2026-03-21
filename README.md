# AI-BankApp-DevOps

A Spring Boot banking application used as a base for learning end-to-end DevOps — from Docker to Kubernetes to GitOps.

## Tech Stack

- **Backend:** Spring Boot 3.4.1, Java 21, Spring Security, JPA/Hibernate
- **Frontend:** Thymeleaf, Bootstrap 5, Glassmorphism UI with dark/light theme
- **Database:** MySQL 8.0
- **AI:** Ollama (self-hosted LLM chatbot, zero cost)
- **DevOps:** Docker, GitHub Actions, Kubernetes, Helm, Terraform, Prometheus, Grafana, ArgoCD


## Features

- User registration & login with BCrypt passwords
- Deposit, withdraw, transfer between accounts
- Transaction history with color-coded entries
- Dark/light theme toggle (persists across sessions)
- AI chatbot that knows your balance and recent transactions
- Prometheus metrics at `/actuator/prometheus`
- Health check at `/actuator/health`


## 👨‍💻 Credits

Inspired by the original project by **trainwithshubham**:  
👉 [https://github.com/trainwithshubham/<repo>](https://github.com/TrainWithShubham/AI-BankApp-DevOps)
