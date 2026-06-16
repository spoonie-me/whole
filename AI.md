# Whole — Tier 2 (the private AI layer)

This is the full version, running entirely on your GB10. Nothing about your body leaves the box.

## What's running right now

| Piece | What it does | Where |
|-------|--------------|-------|
| Fasten (`whole-fasten`) | Pulls + stores your records | https://localhost:9090 |
| Open WebUI (`open-webui`) | The chat interface you ask questions in | http://localhost:8080 |
| Ollama | Runs the models locally | http://localhost:11434 |
| `medgemma:27b` | The medical reasoning model | (in Ollama) |
| `nomic-embed-text` | Turns your records into searchable meaning | (in Ollama) |

All four are already up. Fasten auto-restarts on reboot (`--restart unless-stopped`).

## The one-time setup you have to do yourself

These steps need *your* passwords, so they can't be automated — that's the point.

1. **Open https://localhost:9090** (accept the self-signed cert warning — it's your own machine) and create your local account.
2. **Add Source** → search each provider → log in through their page. Repeat for every doctor, lab, and hospital. Drag in PDFs for anything that won't connect.
3. Once records are in, **Export** them from Fasten (Settings → Export) to a folder, e.g. `~/whole/export/`.

## Wiring records into the AI (in Open WebUI)

1. Open http://localhost:8080.
2. Go to **Workspace → Knowledge** → create a collection called `my-records`.
3. Upload the exported files from `~/whole/export/`.
4. In **Admin → Settings → Documents**, set the embedding model to `nomic-embed-text`.
5. Set your default model to `medgemma:27b`.
6. In a new chat, type `#my-records` to ground answers in your own history, then ask away:
   - "Line up my ferritin over the last four years."
   - "What changed since my last cardiology visit?"
   - "Give me three questions to ask at my next appointment."

## The line that matters

This prepares you; it does not diagnose you. The model handles the information. You — and your doctor — handle what it means.

## Re-run / move it

The whole records layer is one command. To rebuild on any machine:

```bash
docker run -d --name whole-fasten --restart unless-stopped \
  -p 9090:8080 -v ~/whole/db:/opt/fasten/db \
  ghcr.io/fastenhealth/fasten-onprem:main
```

Your data lives in `~/whole/db`. Back that folder up like you'd back up photos.
