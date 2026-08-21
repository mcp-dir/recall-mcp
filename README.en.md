# Recall

### Recall for Claude, ChatGPT and AI agents

Recall (recall.it) — your AI knowledge base / 'second brain'. Via the official API: semantic search across your cards, list with filters (tags, dates, source URL) and read a card's content. Read-only (Recall does not expose writes yet). Generate your API key in Settings → API & MCP (Max plan).

- 📊 **4 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Recall`, URL `https://api.mcp.ai/p_recall`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=recall&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9yZWNhbGwifQ==)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=recall&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_recall%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_recall
```

---

## 4 tools

| Tool | Description |
|---|---|
| `recall_list_accounts` | Lista contas Recall vinculadas a este install — id e apelido. |
| `recall_list_cards` | Lista os cards da sua base Recall (leitura). |
| `recall_get_card` | Conteúdo de um card específico (chunks). |
| `recall_search` | Busca semântica na sua base Recall. |

---

## Pricing

Free.

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_recall` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
