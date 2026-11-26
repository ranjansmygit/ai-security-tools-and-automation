agent-audit-logger/
├── .github/
│   └── copilot-instructions.md       # Project architecture & coding rules for GitHub Copilot
├── alembic/
│   ├── versions/                     # Auto-generated database migration scripts
│   └── env.py                        # Async Alembic migration configuration
├── app/
│   ├── api/
│   │   ├── __init__.py
│   │   ├── events.py                 # POST /v1/events (tamper-evident log ingestion)
│   │   ├── audit_trail.py            # GET /v1/audit-trail (filtered & full-text search)
│   │   └── reports.py                # GET /v1/reports/export (streaming CSV/JSON reports)
│   ├── core/
│   │   ├── __init__.py
│   │   ├── config.py                 # Pydantic settings & environment variable loader
│   │   ├── security.py               # PII/secret masking & SHA-256 hash-chain utilities
│   │   └── telemetry.py              # OpenTelemetry SDK setup & custom span attributes
│   ├── db/
│   │   ├── __init__.py
│   │   └── session.py                # Async SQLAlchemy engine & PostgreSQL session factory
│   ├── models/
│   │   ├── __init__.py
│   │   └── audit_event.py            # Append-only PostgreSQL ORM model (JSONB + hash columns)
│   ├── schemas/
│   │   ├── __init__.py
│   │   └── audit_event.py            # Pydantic v2 request/response & query filter schemas
│   ├── services/
│   │   ├── __init__.py
│   │   ├── audit_service.py          # Business logic for hashing, saving & querying events
│   │   └── export_service.py         # Async CSV & JSON report stream generators
│   ├── __init__.py
│   └── main.py                       # FastAPI app entrypoint, middleware & OTel instrumentation
├── grafana/
│   ├── dashboards/
│   │   └── agent_audit.json          # Pre-built dashboard (tool calls, errors, latency)
│   └── provisioning/
│       ├── dashboards/
│       │   └── dashboard.yml         # Auto-loads JSON dashboards on Grafana startup
│       └── datasources/
│           └── datasource.yml        # Auto-connects PostgreSQL & OTel datasources
├── otel/
│   └── otel-collector-config.yaml    # OpenTelemetry Collector receivers, processors & exporters
├── sdk/
│   ├── __init__.py
│   └── audit_client.py               # Lightweight @audit_tool Python decorator for your agents
├── tests/
│   ├── __init__.py
│   ├── conftest.py                   # Async pytest fixtures & test database setup
│   ├── test_events.py                # Tests for ingestion, redaction & SHA-256 hash chain
│   ├── test_search.py                # Tests for multi-filter & JSONB search queries
│   └── test_export.py                # Tests for CSV/JSON compliance report exports
├── .env.example                      # Template for DB credentials, API keys & OTel endpoints
├── .gitignore                        # Standard Python, Docker & IDE ignore rules
├── alembic.ini                       # Alembic CLI configuration
├── docker-compose.yml                # Orchestrates FastAPI, PostgreSQL 16, OTel Collector & Grafana
├── Dockerfile                        # Multi-stage Python 3.12 production container build
├── pyproject.toml                    # Dependencies (FastAPI, SQLAlchemy, OTel, pytest) & linters
└── README.md                         # Setup instructions, API docs & architecture overview
