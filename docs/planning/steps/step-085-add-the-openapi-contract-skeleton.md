# Step 085 — Add the OpenAPI contract skeleton

**Phase:** `05-shared-packages`

## Purpose

Create the first OpenAPI contract document.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p contracts/openapi

cat > contracts/openapi/openapi.yaml <<'EOF'
openapi: 3.1.0
info:
  title: monorepo-starter API
  version: 0.0.0
paths:
  /health:
    get:
      summary: Health check
      responses:
        "200":
          description: OK
          content:
            application/json:
              schema:
                type: object
                properties:
                  ok:
                    type: boolean
                required:
                  - ok
EOF
```

## Validate

```bash
test -f contracts/openapi/openapi.yaml
```

## Commit

```bash
git add .
git commit -m "feat(contracts): add openapi skeleton"
git push
```
