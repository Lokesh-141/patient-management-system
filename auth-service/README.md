## auth-service-db (Docker image)

**Image ID or name:** `postgres:latest`

**Container name:** `auth-service-db`

**Bind ports:** `5001:5432`

**Bind mounts:** `C:\Users\prita\db_volumes\auth-service-db:/var/lib/postgresql/data`

### Enviroment Variables
```
POSTGRES_DB=db; POSTGRES_PASSWORD=password;
POSTGRES_USER=admin_user
```

**Run options:** `--network internal`

---

## auth-service (Dockerfile)

**Dockerfile:** `auth-service\Dockerfile`

**Image tag:** `auth-service:latest`

**Container name:** `auth-service`

### Enviroment Variables
```
JWT_SECRET=Q0oGfMkfwIAwUVsqFJTmsCDYiuZBfXE1N5htU/eVHa4=;
SPRING_DATASOURCE_PASSWORD=password;
SPRING_DATASOURCE_URL=jdbc:postgresql://auth-service-db:5432/db;
SPRING_DATASOURCE_USERNAME=admin_user;
SPRING_JPA_HIBERNATE_DDL_AUTO=update;
SPRING_SQL_INIT_MODE=always
```

**Run options:** `--network internal`
