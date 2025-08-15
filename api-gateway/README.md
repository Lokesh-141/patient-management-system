## Folder Structure

```
api-gateway/
├── .mvn/
│   └── wrapper/
│       └── maven-wrapper.properties
├── src/
│   └── main/
│       ├── java/
│       │   └── com/pm/apigateway/
│       │       ├── exception/
│       │       │   └── JwtValidationException.java
│       │       ├── filter/
│       │       │   └── JwtValidationGatewayFilterFactory.java
│       │       └── ApiGatewayApplication.java
│       └── resources/
│           ├── application.yml
│           └── application-prod.yml
├── target/
├── .gitattributes
├── .gitignore
├── Dockerfile
├── HELP.md
├── mvnw
├── mvnw.cmd
└── pom.xml
```
