

# 📦 infrasobral/php-laravel-base

Imagem base Docker para aplicações **Laravel 12**, utilizando:

- Debian 12
- PHP 8.4 com extensões essenciais
- Apache 2.4
- Node.js 22 + NPM
- Composer

Ideal para projetos da entidade **PMS** e demais aplicações PHP modernas.

---

## 🧰 Tecnologias incluídas

- **PHP 8.4** com suporte a:
  - MySQL, PostgreSQL, SQLite, XML, MBString, SOAP, Zip, GD, Bcmath
- **Node.js 22** + NPM
- **Apache 2.4**
- **Composer**
- **Debian 12**

---

## 🚀 Como usar

### 1. Puxar a imagem

```bash
docker pull pmsorg/php-laravel-base:1.0
```

### 2. Criar um container com Laravel
```bash
docker run -d \
  --name meu-app-laravel \
  -p 8080:80 \
  -v $(pwd)/meu-projeto:/var/www/html \
  infrasobral/php-laravel-base:latest

```
- Acesse o Laravel em: http://localhost:8080

---

## Desenvolvimento com Docker Compose
Você pode usar esta imagem como base em um docker-compose.yml personalizado, exemplo:
```bash
services:
  app:
    image: pmsorg/php-laravel-base:1.0
    ports:
      - "8080:80"
    volumes:
      - ./meu-projeto:/var/www/html

```
## 🏷️ Tags disponíveis
- 1.0: Primeira versão estável

- latest: Última versão publicada

---
## 📄 Licença
- Distribuído para uso livre pela entidade PMS.

---
## 📫 Manutenção
- Esta imagem é mantida por Cassiano Souza.
