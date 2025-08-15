## Folder Structure

```
billing-service/
├── .mvn/
│   └── wrapper/
│       └── maven-wrapper.properties
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/pm/billingservice/
│   │   │       ├── grpc/
│   │   │       │   └── BillingGrpcService.java
│   │   │       └── BillingServiceApplication.java
│   │   ├── proto/
│   │   │   └── billing_service.proto
│   │   └── resources/
│   │       ├── static/
│   │       ├── templates/
│   │       └── application.properties
│   └── test/
│       └── java/
│           └── com/pm/billingservice/
│               └── BillingServiceApplicationTests.java
├── target/
├── .gitattributes
├── .gitignore
├── billing-service.iml
├── Dockerfile
├── HELP.md
├── mvnw
├── mvnw.cmd
└── pom.xml
```

---

## 🐳 billing-service (Dockerfile)

| Property         | Value                          |
|------------------|--------------------------------|
| Dockerfile       | `billing-service/Dockerfile`   |
| Image Tag        | `billing-service:latest`       |
| Container Name   | `billing-service`              |
| Bind Ports       | `4001:4001`, `9001:9001`       |
| Run Options      | `--network internal`           |
