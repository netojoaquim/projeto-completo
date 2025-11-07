# Projeto E-commerce

Este é um projeto de e-commerce com **frontend em React**, **backend em Node.js/Express** e **banco de dados PostgreSQL**, todo gerenciado com Docker.

---

## 🐋 Pré-requisitos

* Docker
* Docker Compose

---

## 🚀 Como executar

1.  **Clone o repositório:**
    ```bash
    git clone <URL_DO_REPOSITORIO>
    cd <NOME_DO_REPOSITORIO>
    ```

2.  **Crie o arquivo `.env` para o backend** (se necessário) com as variáveis de ambiente adequadas:
    ```ini
    DATABASE_URL=postgres://postgres:@postgres:5432/ecommerce_db
    NODE_ENV=production
    ```

3.  **Certifique-se de que o frontend aponta para o backend** (geralmente em um `.env` no frontend):
    ```ini
    REACT_APP_BASE_URL=http://backend:5000
    ```

4.  **Suba os containers com Docker Compose:**
    ```bash
    docker-compose up --build
    ```
    Isso irá:
    * Criar o container do PostgreSQL na porta `5433` (externa)
    * Criar o container do backend na porta `5000`
    * Criar o container do frontend na porta `3000`

---

### ઍ Acessando o projeto

* **Frontend:** `http://localhost:3000`
* **Backend (Swagger):** `http://localhost:5000/api-docs`

---

### 🛑 Parar os containers

```bash
docker-compose down