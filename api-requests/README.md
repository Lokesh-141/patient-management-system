## Folder Structure

```
api-requests/
├── auth-service/
│   ├── login.http
│   └── validate.http
└── patient-service/
    ├── create-patient.http
    ├── delete-patient.http
    ├── get-patients.http
    └── update-patient.http
```

---
## 🐳 api-requests (Dockerfile)

| Property         | Value                          |
|------------------|--------------------------------|
| Dockerfile       | `api-gateway/Dockerfile`       |
| Image Tag        | `api-gateway:latest`           |
| Container Name   | `api-gateway`                  |
| Bind Ports       | `4004:4004`                    |
| Run Options      | `--network internal`           |

### Enviroment Variables
```
AUTH_SERVICE_URL=http://auth-service:4005
```
