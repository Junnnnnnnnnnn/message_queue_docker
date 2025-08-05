# Message Queue with Docker

This project sets up a RabbitMQ message queue using Docker.

## Prerequisites

- Docker
- Docker Compose

## Services

- **RabbitMQ**: A popular open-source message broker.

## How to Run

1.  **Start the services:**

    ```bash
    docker-compose up -d
    ```

2.  **Access RabbitMQ Management UI:**

    -   URL: [http://localhost:15672](http://localhost:15672)
    -   Username: `admin`
    -   Password: `password`

3.  **Connect to RabbitMQ:**

    -   Host: `localhost`
    -   Port: `5672`

## Configuration

The `docker-compose.yml` file defines the following:

-   **Service**: `rabbitmq`
-   **Image**: `rabbitmq:3-management`
-   **Ports**:
    -   `5672`: RabbitMQ message broker
    -   `15672`: RabbitMQ Management UI
-   **Credentials**:
    -   `RABBITMQ_DEFAULT_USER`: "admin"
    -   `RABBITMQ_DEFAULT_PASS`: "password"
-   **Volume**: `rabbitmq_data` for persistent data.
-   **Network**: `app`
