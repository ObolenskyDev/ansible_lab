# Ansible & DevOps Playground 🛠️

![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)

Репозиторий для практики Infrastructure as Code (IaC) и Observability.
Проект разворачивает веб-сервер (Nginx) через Ansible и стек мониторинга (Prometheus + Grafana) в Docker контейнерах.

## 🚀 Компоненты системы
1.  **Ansible:** Идемпотентная настройка Nginx.
2.  **Prometheus:** Сбор метрик с хоста (через Node Exporter).
3.  **Grafana:** Визуализация метрик (CPU, RAM, Net).

## 📦 Быстрый старт

### 1. Настройка окружения
Создайте файл с секретами для Grafana:
```bash
cp .env.example .env
# Внутри .env задайте свой пароль
```

### 2. Запуск мониторинга
```Bash
docker-compose up -d
Grafana: http://localhost:3000
Prometheus: http://localhost:9090
```

### 3. Настройка веб-сервера (Ansible)
```Bash
ansible-playbook -i hosts.ini install_nginx.yml -K
```

## Готовый мониторинг Prometheus + Grafana
![Image alt](assets/monitoring_dashboard.png)