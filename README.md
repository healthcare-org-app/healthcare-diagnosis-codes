# diagnosis-codes-service

diagnosis-codes-service — domain: ehr

- **Port:** 8313
- **Language:** Python 3.11 + Flask
- **Database:** `ehr` (Postgres, table `diagnosis_codes`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/diagnosis_codes/`          |
| POST      | `/api/diagnosis_codes/`          |
| GET       | `/api/diagnosis_codes/<id>`      |
| PUT/PATCH | `/api/diagnosis_codes/<id>`      |
| DELETE    | `/api/diagnosis_codes/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
