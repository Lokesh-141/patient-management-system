**Dockerfile:** `api-gateway\Dockerfile`

**Image tag:** `api-gateway:latest`

**Container name:** `api-gateway`

**Bind ports:** `4004:4004`

## Enviroment Variables
```
AUTH_SERVICE_URL=http://auth-service:4005
```

**Run options:** `--network internal`
