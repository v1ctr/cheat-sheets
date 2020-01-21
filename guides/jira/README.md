# How to install dockerized Jira

1. Create `.env` file
    ```bash
    touch .env
    ```
2. Insert following environment variables in `.env` file
    ```
    ATL_PROXY_NAME=localhost
    ATL_PROXY_PORT=8080
    ATL_JDBC_USER=jirauser
    ATL_JDBC_PASSWORD=<password>
    ATL_JDBC_URL=jdbc:postgresql://postgres:5432/jira
    ATL_DB_DRIVER=org.postgresql.Driver
    ATL_DB_TYPE=postgres72
    
    POSTGRES_USER=jirauser
    POSTGRES_DB=jira
    POSTGRES_PASSWORD=<password>
    ```
3. Run docker-compose
    ```bash
    docker-compose up -d
    ```
Jira can now be viewed at http://localhost:8080.