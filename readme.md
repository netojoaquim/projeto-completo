# Projeto E-commerce

Este é um projeto de e-commerce com **frontend em React**, **backend em NestJs** e **banco de dados PostgreSQL**, todo gerenciado com Docker.

---

## Pré-requisitos

* Docker
* Docker Compose

---

## Como executar

1.  **Clone o repositório:**
    ```bash
    git clone <URL_DO_REPOSITORIO>
    cd <NOME_DO_REPOSITORIO>
    ```

2.  **Crie o arquivo `.env` para o backend** (se necessário) com as variáveis de ambiente adequadas:
    ```ini
    DATABASE_URL=postgres://postgres:@postgres:5432/ecommerce_db
    # JWT_SECRET=<secret>
    DB_HOST=postgres
    DB_PORT=5432
    DB_USERNAME=postgres
    DB_PASSWORD=6415
    DB_NAME=ecommerce_db

    #tempo para redefinicao de senha
    MIN_INTERVAL_MS=20

    #configuração envio emails
    MAIL_HOST=smtp.gmail.com
    MAIL_PORT=465
    MAIL_SECURE=true
    MAIL_USER=<email>
    MAIL_PASSWORD=qtvi jbxf uhoh  #4 ultimos removido
    MAIL_FROM="Guarashop <email>"
    #horario
    TZ=America/Recife

    ```

3.  **Certifique-se de que o frontend aponta para o backend** (geralmente em um `.env` no frontend):
    ```ini
    REACT_APP_BASE_URL=http://localhost:5000
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

### Acessando o projeto

* **Frontend:** `http://localhost:3000`
* **Backend (Swagger):** `http://localhost:5000/api-docs`

---

### Parar os containers

```bash
docker-compose down
