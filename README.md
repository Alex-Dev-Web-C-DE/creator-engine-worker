# Creator Engine Worker

Cloudflare Worker — HTTP API for Creator Engine v0.5 (Promise Extraction + Alignment).

## Endpoints

- `GET /health` — Health check
- `POST /extract` — Extract promises and align against contract

### POST /extract

Request body:

    {
      "sales_text": "...",
      "contract_text": "..."
    }

Response:

    {
      "status": "ok",
      "data": {
        "promises": [...],
        "contract_terms": [...],
        "alignments": [...]
      }
    }

## Deploy

    npx wrangler deploy
    npx wrangler secret put OPENAI_API_KEY

## Live

https://creator-engine.boring-saas-infra.workers.dev
