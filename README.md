# Distributed Deployment of Microservices using Ansible

This repository contains Ansible configurations to automate the deployment of a microservice-based application using Docker. The microservices include RabbitMQ, Elasticsearch, Kibana, and a Sinatra-based web application. The deployment is managed via Ansible playbooks, ensuring a streamlined and reproducible setup process.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Setup](#setup)
  - [Configuration](#configuration)
  - [Installation](#installation)
- [Usage](#usage)
- [URLs](#urls)
- [License](#license)

## Features

- **Automated Deployment**: Use Ansible to automate the setup and deployment of microservices.
- **Dockerized Services**: All services are containerized using Docker.
- **Reverse Proxy**: Nginx is configured as a reverse proxy to route traffic to appropriate services.
- **Log Management**: Filebeat and Kibana are used for log shipping and visualization.

## Prerequisites

- Docker
- Ansible
- Python 3.x
- Pip

## Setup

### Configuration

1. **Clone the repository:**
   ```bash
   git clone https://github.com/zoopyserg/distributed-deployment-ansible.git
   cd distributed-deployment-ansible
   ```

2. **Copy and configure environment variables:**
   ```bash
   cp vars.yml.template vars.yml
   # Edit vars.yml to set the appropriate values
   ```

3. **Copy and configure the .env file:**
   ```bash
   cp .env.template .env
   # Edit .env to set the appropriate values
   ```

### Installation

1. **Install Python dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Run the Ansible playbook:**
   ```bash
   source .env
   ansible-playbook playbooks/main.yml
   ```

## Usage

### Starting the Application

Once the playbook has finished running, the Docker containers for RabbitMQ, Elasticsearch, Kibana, Filebeat, and the web application will be up and running.

### Accessing the Services

- **Web Application**: Visit `http://127.0.0.1/produce`
- **RabbitMQ Management**: Visit `http://127.0.0.1:15672`
- **Elasticsearch**: Visit `http://127.0.0.1:9200`
- **Kibana**: Visit `http://127.0.0.1:5601`

> Note: Only `127.0.0.1` requests work currently. Modify your configuration to allow `localhost` if needed.

## URLs

- **Produce Message**: [127.0.0.1/produce](http://127.0.0.1/produce)
- **RabbitMQ Management Interface**: [127.0.0.1:15672](http://127.0.0.1:15672)
- **Elasticsearch**: [127.0.0.1:9200](http://127.0.0.1:9200)
- **Kibana**: [127.0.0.1:5601](http://127.0.0.1:5601)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
