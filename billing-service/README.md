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

**Dockerfile:** `billing-service\Dockerfile`

**Image tag:** `billing-service:latest`

**Container name:** `billing-service`

**Bind ports:** `4001:4001 9001:9001`

**Run options:** `--network internal`
