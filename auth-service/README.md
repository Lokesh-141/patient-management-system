## Folder Structure

```
auth-service/
├── .mvn/
│   └── wrapper/
│       └── maven-wrapper.properties
├── src/
│   └── main/
│       ├── java/
│       |   └── com/pm/authservice/
│       |       ├── config/
│       |       │   └── SecurityConfig.java
│       |       ├── controller/
│       |       │   └── AuthController.java
│       |       ├── dto/
│       |       │   ├── LoginRequestDTO.java
│       |       │   └── LoginResponseDTO.java
│       |       ├── model/
│       |       │   └── User.java
│       |       ├── repository/
│       |       │   └── UserRepository.java
│       |       ├── service/
│       |       │   ├── AuthService.java
│       |       │   └── UserService.java
│       |       ├── util/
│       |       │   └── JwtUtil.java
│       |       └── AuthServiceApplication.java
│       └── resources/
│           ├── application.properties
│           └── data.sql
├── target/
├── .gitattributes
├── .gitignore
├── auth-service.iml
├── Dockerfile
├── HELP.md
├── mvnw
├── mvnw.cmd
└── pom.xml
```

---

## 🐘 auth-service-db (Docker image)

| Property         | Value                                                                 |
|------------------|-----------------------------------------------------------------------|
| Image            | `postgres:latest`                                                    |
| Container Name   | `auth-service-db`                                                    |
| Bind Ports       | `5001:5432`                                                           |
| Bind Mounts      | `C:\Users\prita\db_volumes\auth-service-db:/var/lib/postgresql/data` |
| Run Options      | `--network internal`                                                 |

### Enviroment Variables
```
POSTGRES_DB=db; POSTGRES_PASSWORD=password;
POSTGRES_USER=admin_user
```

---

## 🐳 auth-service (Dockerfile)

| Property         | Value                          |
|------------------|--------------------------------|
| Dockerfile       | `auth-service/Dockerfile`      |
| Image Tag        | `auth-service:latest`          |
| Container Name   | `auth-service`                 |
| Run Options      | `--network internal`           |

### Enviroment Variables
```
JWT_SECRET=Q0oGfMkfwIAwUVsqFJTmsCDYiuZBfXE1N5htU/eVHa4=;
SPRING_DATASOURCE_PASSWORD=password;
SPRING_DATASOURCE_URL=jdbc:postgresql://auth-service-db:5432/db;
SPRING_DATASOURCE_USERNAME=admin_user;
SPRING_JPA_HIBERNATE_DDL_AUTO=update;
SPRING_SQL_INIT_MODE=always
```
