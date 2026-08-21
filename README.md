# Recall

### Recall para Claude, ChatGPT e agentes de IA

Recall (recall.it) — sua base de conhecimento de IA / 'segundo cérebro'. Via API oficial: busca semântica nos seus cards, listagem com filtros (tags, datas, URL de origem) e leitura do conteúdo de um card. Somente leitura (a escrita ainda não é exposta pela Recall). Gere sua API key em Settings → API & MCP (plano Max).

- 📊 **4 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Recall` e **URL** `https://api.mcp.ai/p_recall`.

### Cursor

[➕ Instalar Recall no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=recall&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9yZWNhbGwifQ==)

### VS Code (Copilot Chat)

[➕ Instalar Recall no VS Code](vscode:mcp/install?name=recall&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_recall%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_recall
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Busque na minha Recall o que salvei sobre repetição espaçada
Liste meus cards do último mês
Traga o conteúdo do card X focando em 'preço'
```

---

## 4 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `recall_list_accounts` | Lista contas Recall vinculadas a este install — id e apelido. |
| `recall_list_cards` | Lista os cards da sua base Recall (leitura). |
| `recall_get_card` | Conteúdo de um card específico (chunks). |
| `recall_search` | Busca semântica na sua base Recall. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Grátis.

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: Recall (getrecall.ai), o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_recall`.


---

## Suporte

- 📧 [recall@mcp.ai](mailto:recall@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/recall-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_recall` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
