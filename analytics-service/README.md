## Folder Structure

```
analytics-service/
├── .mvn/
│   └── wrapper/
│       └── maven-wrapper.properties
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/pm/analyticsservice/
│   │   │       ├── kafka/
│   │   │       │   └── KafkaConsumer.java
│   │   │       └── AnalyticsServiceApplication.java
│   │   ├── proto/
│   │   │   └── patient_event.proto
│   │   └── resources/
│   │       ├── static/
│   │       ├── templates/
│   │       └── application.properties
│   └── test/
│       └── java/
│           └── com/pm/analyticsservice/
│               └── AnalyticsServiceApplicationTests.java
├── target/
├── .gitattributes
├── .gitignore
├── analytics-service.iml
├── Dockerfile
├── HELP.md
├── mvnw
├── mvnw.cmd
└── pom.xml
```

---

**Dockerfile:** `analytics-service\Dockerfile`

**Image tag:** `analytics-service:latest`

**Container name:** `analytics-service`

**Bind ports:** `4002:4002`

### Enviroment variables
```
SPRING_KAFKA_BOOTSTRAP_SERVERS=kafka:9092
```

**Run options:** `--network internal`
