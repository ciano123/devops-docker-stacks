# 🐳 devops-docker-stacks

Repositório central com imagens e templates Docker infraestrutura/DevOps. Este repositório contém projetos organizados para padronizar ambientes, automatizar builds e facilitar o deploy de aplicações em containers.

## 📁 Estrutura do Repositório
devops-docker-stacks/

├── base-images/

│ └── php-laravel-base/

├── templates/

│ ├── example-app/

│ └── app-example/

└── README.md

- **base-images/**: Imagens genéricas reutilizáveis com PHP, Node.js, Apache, etc.
- **templates/**: Exemplos de uso e composições `docker-compose` prontos para deploy.

---

## 📦 Imagens em Destaque

| Projeto | Descrição | Docker Hub |
|--------|-----------|------------|
| `php-laravel-base` | Imagem base com PHP 8.4, Node.js 22 e Apache para Laravel 12 | [infrasobral/php-laravel-base:latest](https://hub.docker.com/r/infrasobral/php-laravel-base) |
| `webserver-http` | Template para servidores Apache com configurações customizadas | Em breve |

---

## 🚀 Objetivo

Fornecer um ponto único e versionado para:
- Automatizar builds de containers.
- Padronizar ambientes de desenvolvimento e produção.
- Facilitar deploy em pipelines CI/CD.
- Compartilhar boas práticas em DevOps e SRE.

---

## 🛠️ Requisitos

- Docker 20+
- Docker Compose 1.29+
- Git
- Familiaridade com terminal e containers

---

## 📖 Como Usar

Clone o repositório:
```bash
git clone https://github.com/ciano123/devops-docker-stacks.git
cd devops-docker-stacks
```
- Escolha uma pasta de projeto e siga o **README.md** específico de cada um.

---

## 🧑‍💻 Contribuições
Contribuições são bem-vindas! Siga as boas práticas:

  - Padronize os nomes de diretórios com **kebab-case**.

  -  Documente seu projeto com **README.md** claro.

  - Use **Dockerfile** e **docker-compose.yml** organizados e testáveis.

---

## 📄 Licença
- Este projeto está sendo mantido por Cassiano Souza.