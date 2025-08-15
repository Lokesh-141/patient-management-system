## Folder Structure

```
patient-service/
├── .mvn/
│   └── wrapper/
│       └── maven-wrapper.properties
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/pm/patientservice/
│   │   │       ├── controller/
│   │   │       │   └── PatientController.java
│   │   │       ├── dto/
│   │   │       │   ├── validators/
│   │   │       │   |   └── CreatePatientValidationGroup.java
│   │   │       │   ├── PatientRequestDTO.java
│   │   │       |   └── PatientResponseDTO.java
│   │   │       ├── exception/
│   │   │       │   ├── EmailAlreadyExistsException.java
│   │   │       │   ├── GlobalExceptionHandler.java
│   │   │       |   └── PatientNotFoundException.java
│   │   │       ├── grpc/
│   │   │       │   └── BillingServiceGrpcClient.java
│   │   │       ├── kafka/
│   │   │       │   └── KafkaProducer.java
│   │   │       ├── mapper/
│   │   │       │   └── PatientMapper.java
│   │   │       ├── model/
│   │   │       │   └── Patient.java
│   │   │       ├── repository/
│   │   │       │   └── PatientRepository.java
│   │   │       └── service/
│   │   │           ├── PatientService.java
│   │   │           └── PatientServiceApplication.java
│   │   ├── proto/
│   │   │   ├── billing_service.proto
│   │   │   └── patient_event.proto
│   │   └── resources/
│   │       ├── static/
│   │       ├── templates/
│   │       ├── application.properties
│   │       └── data.sql
│   └── test/
│       └── java/
│           └── com/pm/patientservice/
│               └── PatientServiceApplicationTests.java
├── target/
├── .gitattributes
├── .gitignore
├── Dockerfile
├── HELP.md
├── mvnw
├── mvnw.cmd
└── pom.xml
```

---

## 🐘 patient-service-db (Docker image)

| Property         | Value                                                                 |
|------------------|-----------------------------------------------------------------------|
| Image            | `postgres:latest`                                                    |
| Container Name   | `patient-service-db`                                                 |
| Bind Ports       | `5000:5432`                                                           |
| Bind Mounts      | `C:\Users\prita\db_volumes\patient-service-db:/var/lib/postgresql/data` |
| Run Options      | `--network internal`

### Enviroment Variables
```
POSTGRES_DB=db;
POSTGRES_PASSWORD=password;
POSTGRES_USER=admin_user
```

---

## 🐳 patient-service (Dockerfile)

| Property         | Value                          |
|------------------|--------------------------------|
| Dockerfile       | `patient-service/Dockerfile`   |
| Image Tag        | `patient-service:latest`       |
| Container Name   | `patient-service`              |
| Run Options      | `--network internal`           |

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
