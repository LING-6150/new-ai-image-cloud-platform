# AI Image Cloud Platform ☁️🖼️

An enterprise-grade, AI-powered cloud platform for managing images. Supports multi-tenant architecture, intelligent asset tagging, real-time collaboration, fine-grained permission control, and high-performance concurrent access.

## 🔧 Tech Stack

- **Backend:** Spring Boot, MyBatis Plus, Redis, Sa-Token, Caffeine Cache, Disruptor
- **Database:** MySQL, ShardingSphere (horizontal sharding)
- **Object Storage:** Tencent Cloud COS (can be replaced with Aliyun OSS or local storage)
- **Asynchronous Processing:** Disruptor + Delayed Audit Queues
- **WebSocket:** For real-time editing and notifications
- **Deployment:** Linux + Nginx (supports containerization)
- **Frontend:** *(Frontend repo not included here)*

## 🌟 Key Features

- Intelligent image management: uploading, tagging, thumbnail generation, WebP compression
- Real-time collaboration via WebSocket
- Role-based access control (RBAC) for users, teams, and organizations
- Admin dashboard with moderation queues, statistics, and audit logs
- Highly optimized for concurrency and scalability

## 🚀 Getting Started (Development Setup)

> Ensure you have **JDK 17**, **MySQL**, and **Redis** installed.

### 1. Clone the repository

```bash
git clone https://github.com/LING-6150/new-ai-image-cloud-platform.git
cd new-ai-image-cloud-platform
```bash
git clone https://github.com/LING-6150/new-ai-image-cloud-platform.git
cd new-ai-image-cloud-platform
2. Configure the database
Create the database:

sql
Copy
Edit
CREATE DATABASE yu_picture;
Then run the SQL statements in src/main/resources/sql/init.sql.

3. Set up application configuration
Edit src/main/resources/application.yml:

yaml
Copy
Edit
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/yu_picture
    username: root
    password: your_password
  redis:
    host: 127.0.0.1
    port: 6379
4. Build and Run the project
bash
Copy
Edit
mvn clean install -DskipTests
mvn spring-boot:run
The app will be available at: http://localhost:8123/api

⚠️ Important
Do not commit cloud API keys (e.g., Tencent Cloud secrets) to GitHub.

You can store secrets securely via environment variables or GitHub Actions Secrets.
