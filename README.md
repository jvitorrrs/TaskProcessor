# TaskProcessor

TaskProcessor é uma aplicação desenvolvida em .NET Core para o processamento assíncrono de tarefas via API. Utiliza RabbitMQ como sistema de fila, MongoDB como banco de dados NoSQL e possui workers dedicados para executar tarefas em segundo plano. É projetado para ser escalável, desacoplado e containerizável via Docker.

## 🔧 Tecnologias Utilizadas

- ASP.NET Core 8
- MongoDB (NoSQL)
- RabbitMQ
- Docker e Docker Compose
- GitHub Actions (CI/CD)

## 📦 Funcionalidades

- Recebimento de tarefas (jobs) via API REST
- Armazenamento das tarefas em fila (RabbitMQ) e base (MongoDB)
- Processamento assíncrono com re-tentativas e controle de concorrência
- Atualização e consulta de status da tarefa via API
- Totalmente preparado para rodar em containers

## 🚀 Executando Localmente

### Pré-requisitos

- Docker + Docker Compose
- .NET SDK 8.0 (para rodar/testar localmente sem Docker)

### Subindo com Docker Compose

```bash
docker-compose up --build
```

A aplicação estará acessível em: `http://localhost:8080/api/jobs`

### Executando Testes

```bash
dotnet test TaskProcessor/TaskProcessor.Tests/TaskProcessor.Tests.csproj
```

## ⚙️ CI/CD

Este repositório está configurado com GitHub Actions para:

- Build automático do projeto
- Execução dos testes
- Build de imagem Docker
- (Opcional) Publicação no Docker Hub

## 📂 Estrutura do Projeto

```
TaskProcessor/
├── TaskProcessor/                  # API principal
├── TaskProcessor.Application/      # Casos de uso / Application Layer
├── TaskProcessor.Domain/           # Entidades e Interfaces de domínio
├── TaskProcessor.Infrastructure/   # Repositórios, serviços externos, RabbitMQ
├── TaskProcessor.EmailJobWorker/   # Worker que processa tarefas de e-mail
├── TaskProcessor.Tests/            # Testes automatizados
```

## 📄 Licença

Este projeto não possui uma licença definida. Sinta-se à vontade para sugerir ou contribuir!
