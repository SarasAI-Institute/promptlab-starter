# PromptLab API contract

UUID strings identify prompts and collections. Times are aware UTC ISO8601. Prompt fields: title
(1–200 chars), content (nonempty, literal {{variables}}), description (null or up to 500 chars), collection_id
(existing ID or null). Saved prompts add id, created_at and updated_at. Collections use name (1–100),
description (null or up to 500), id and created_at. In-memory data persists within one process only.

| Method/path | Success | Failures and details |
|---|---|---|
|GET /health|200 {status:"healthy",version:string}|No domain failure; availability is separate|
|GET /prompts|200 {prompts:[Prompt],total:int}|Unknown collection filter gives empty list|
|GET /prompts/{id}|200 Prompt|404 {detail:"Prompt not found"}|
|POST /prompts|201 Prompt|400 unknown collection;422 invalid fields|
|PUT /prompts/{id}|200 Prompt, full editable replacement|404 missing;400 unknown collection;422 invalid fields|
|PATCH /prompts/{id}|200 Prompt, supplied fields only|404 missing;400 unknown collection;422 invalid merged fields|
|DELETE /prompts/{id}|204 empty|404 missing|
|GET /collections|200 {collections:[Collection],total:int}|No domain failure for empty storage|
|POST /collections|201 Collection|422 invalid fields|
|GET /collections/{id}|200 Collection|404 {detail:"Collection not found"}|
|DELETE /collections/{id}|204 empty|404 missing|

Query parameters collection_id and search combine with AND. Search is a case-insensitive substring
of title OR description. Empty filters have no effect. Results sort newest-created first; equal timestamps
retain insertion order. total is the filtered count. PATCH preserves omitted fields; explicit null clears
optional values; null title/content is422. Empty PATCH succeeds and refreshes updated_at. PUT/PATCH
retain id/created_at and refresh updated_at even for an accepted no-op. Invalid writes do not mutate state.

For collection deletion, choose and document detach, cascade or prevention while referenced.
Test your chosen behavior and publish its response/status contract in your API documentation.
No current prompt may point to a deleted collection. API schema errors return FastAPI's detail array with
loc/msg/type; domain errors use {detail:string}. Do not hard-code dependency-specific English error prose.

## Requests and response examples

```sh
curl -X POST http://localhost:8000/collections -H 'Content-Type: application/json' -d '{"name":"Research"}'
curl -X POST http://localhost:8000/prompts -H 'Content-Type: application/json' -d '{"title":"Summary","content":"Summarize {{input}}"}'
curl 'http://localhost:8000/prompts?search=summary'
curl http://localhost:8000/prompts/PROMPT_ID
curl -X PUT http://localhost:8000/prompts/PROMPT_ID -H 'Content-Type: application/json' -d '{"title":"Revised","content":"Revised {{input}}"}'
curl -X PATCH http://localhost:8000/prompts/PROMPT_ID -H 'Content-Type: application/json' -d '{"description":"For reports"}'
curl -X DELETE http://localhost:8000/prompts/PROMPT_ID
curl http://localhost:8000/collections
curl http://localhost:8000/collections/COLLECTION_ID
curl -X DELETE http://localhost:8000/collections/COLLECTION_ID
curl http://localhost:8000/health
```

Replace ID placeholders with actual returned IDs. A created prompt has this shape (timestamps/IDs vary):
`{"title":"Summary","content":"Summarize {{input}}","description":null,"collection_id":null,"id":"UUID","created_at":"2026-01-01T00:00:00Z","updated_at":"2026-01-01T00:00:00Z"}`.
A collection is `{"name":"Research","description":null,"id":"UUID","created_at":"2026-01-01T00:00:00Z"}`.
List wrappers are as above; deletion has no response body. Inspect /openapi.json or /docs for the exact
current schema. Document any schema extensions you introduce while implementing version history and tagging.
