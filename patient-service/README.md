## patient-service-db

**Image ID or name:** `postgres:latest`

**Container name:** `patient-service-db`

**Bind ports:** `5000:5432`

**Bind mounts:** `C:\Users\prita\db_volumes\patient-service-db:/var/lib/postgresql/data`

### Enviroment Variables
```
POSTGRES_DB=db; POSTGRES_PASSWORD=password;
POSTGRES_USER=admin_user
```

**Run options:** `--network internal`

---

## patient-service

**Dockerfile:** `patient-service\Dockerfile`

**Image tag:** `patient-service:latest`

**Container name:** `patient-service`

### Enviroment Variables
```
BILLING_SERVICE_ADDRESS=billing-service;
BILLING_SERVICE_GRPC_PORT=9001;
SPRING_DATASOURCE_PASSWORD=password;
SPRING_DATASOURCE_URL=jdbc:postgresql://patient-service-db:5432/db;
SPRING_DATASOURCE_USERNAME=admin_user; SPRING_JPA_HIBERNATE_DDL_AUTO=update;
SPRING_KAFKA_BOOTSTRAP_SERVERS=kafka:9092;
SPRING_SQL_INIT_MODE=always
```

**Run options:** `--network internal`
