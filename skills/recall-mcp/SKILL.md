---
name: recall-mcp
description: Skill da REST API do Recall na MCP.AI: 3 endpoints em /api/recall. Recall (recall.it) — sua base de conhecimento de IA / 'segundo cérebro'. Via API oficial: busca semântica nos seus cards, listagem com filtros (tags, datas, URL de origem) e leitura do conteúdo de um card. Somente leitura (a escrita ainda não é exposta pela Recall). Gere sua API key em Settings → API & MCP (plano Max). Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Recall — REST API skill

Você tem acesso à **Recall** REST API na MCP.AI.

> Recall (recall.it) — sua base de conhecimento de IA / 'segundo cérebro'. Via API oficial: busca semântica nos seus cards, listagem com filtros (tags, datas, URL de origem) e leitura do conteúdo de um card. Somente leitura (a escrita ainda não é exposta pela Recall). Gere sua API key em Settings → API & MCP (plano Max).

## Base URL

```
https://api.mcp.ai/api/recall
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/recall/cards \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/recall/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (3)

#### `recall_list_cards`

Lista os cards da base Recall. _(POST /api/recall/cards)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `tags` | string[] | Não | IDs de tag (UUIDs), máx. 50. |
| `date_from` | string | Não | Início (ISO 8601). |
| `date_to` | string | Não | Fim (ISO 8601). |
| `source_url_contains` | string | Não | Trecho na URL de origem (1-500). |

#### `recall_get_card`

Conteúdo (chunks) de um card. focus_query foca os trechos; max_chunks (1-50). _(POST /api/recall/cards/{card_id})_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `card_id` | string | Sim | ID do card. |
| `focus_query` | string | Não | Consulta pra focar chunks (1-1000). |
| `max_chunks` | integer | Não | Máx. de chunks (1-50, default 20). |

#### `recall_search`

Busca semântica na base. q obrigatório; mode focused|exhaustive; filtros card_id/tags/datas/source_url_contains. _(POST /api/recall/search)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `q` | string | Sim | Consulta (1-1000). |
| `mode` | string | Não | focused (default) ou exhaustive. |
| `card_id` | string | Não | Limita a busca a um card. |
| `tags` | string[] | Não | IDs de tag (UUIDs), máx. 50. |
| `date_from` | string | Não | Início (ISO 8601). |
| `date_to` | string | Não | Fim (ISO 8601). |
| `source_url_contains` | string | Não | Trecho na URL de origem (1-500). |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_recall` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
