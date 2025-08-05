# Docker를 이용한 메시지 큐

이 프로젝트는 Docker를 사용하여 RabbitMQ 메시지 큐를 설정합니다.

## 사전 요구 사항

- Docker
- Docker Compose

## 서비스

- **RabbitMQ**: 인기 있는 오픈소스 메시지 브로커입니다.

## 실행 방법

1.  **서비스 시작:**

    ```bash
    docker-compose up -d
    ```

2.  **RabbitMQ 관리 UI 접속:**

    -   URL: [http://localhost:15672](http://localhost:15672)
    -   사용자 이름: `admin`
    -   비밀번호: `password`

3.  **RabbitMQ 연결:**

    -   호스트: `localhost`
    -   포트: `5672`

## 설정

`docker-compose.yml` 파일은 다음을 정의합니다:

-   **서비스**: `rabbitmq`
-   **이미지**: `rabbitmq:3-management`
-   **포트**:
    -   `5672`: RabbitMQ 메시지 브로커
    -   `15672`: RabbitMQ 관리 UI
-   **자격 증명**:
    -   `RABBITMQ_DEFAULT_USER`: "admin"
    -   `RABBITMQ_DEFAULT_PASS`: "password"
-   **볼륨**: 영구 데이터를 위한 `rabbitmq_data`.
-   **네트워크**: `app`
