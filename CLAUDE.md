# Whole — CoWork context

This is a private, local-first personal health record. The stack runs entirely on the user's own machine. Nothing about their health data leaves the box.

## What's running locally

| Service | URL | What it does |
|---------|-----|--------------|
| Fasten (records) | https://localhost:9090 | Pulls FHIR records from patient portals |
| Open WebUI (AI chat) | http://localhost:8080 | Chat interface over local models |
| Ollama (models) | http://localhost:11434 | Runs models locally |

Key models available: `medgemma:27b` (medical reasoning), `nomic-embed-text` (embeddings), `deepseek-r1:70b` (general reasoning).

## What this project is and isn't

Whole organizes and surfaces health records. It does not diagnose. Every suggestion made here should reinforce that the user's doctor is the decision-maker — this tool makes the user a better-prepared patient, not their own physician.

## How to check if services are up

```bash
docker ps --filter name=whole-fasten --format '{{.Names}}: {{.Status}}'
curl -s http://localhost:11434/api/version
curl -s -o /dev/null -w "%{http_code}" http://localhost:8080/
```

## How to restart Fasten if it's down

```bash
docker start whole-fasten
# or from scratch:
docker compose up -d
```

## The data lives here

```
~/whole/db/          # Fasten records database — never commit this
~/whole/export/      # Manual exports from Fasten — never commit this
```

## Tone

The people using this are often sick, often tired, and often disappointed by healthcare. Write for them: short sentences, no jargon that isn't explained, no false optimism. If something doesn't work, say so plainly and tell them what to do next.
