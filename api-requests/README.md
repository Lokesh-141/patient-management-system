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

**Dockerfile:** `api-gateway\Dockerfile`

**Image tag:** `api-gateway:latest`

**Container name:** `api-gateway`

**Bind ports:** `4004:4004`

### Enviroment Variables
```
AUTH_SERVICE_URL=http://auth-service:4005
```

**Run options:** `--network internal`
