# Ferramentas

Recall expõe 4 ferramentas (todas somente leitura).

### 1. `recall_list_accounts`
**Input**: `account` (opcional)

Lista contas Recall vinculadas a este install — id e apelido.

### 2. `recall_list_cards`
**Input**: `tags` (opcional), `date_from` (opcional), `date_to` (opcional), `source_url_contains` (opcional), `account` (opcional)

Lista os cards da sua base Recall (leitura).

### 3. `recall_get_card`
**Input**: `card_id`, `focus_query` (opcional), `max_chunks` (opcional), `account` (opcional), `card_ids` (opcional)

Conteúdo de um card específico (chunks).

### 4. `recall_search`
**Input**: `q`, `mode` (opcional), `card_id` (opcional), `tags` (opcional), `date_from` (opcional), `date_to` (opcional), `source_url_contains` (opcional), `account` (opcional), `card_ids` (opcional)

Busca semântica na sua base Recall.

## Prompts de exemplo

```
Busque na minha Recall o que salvei sobre repetição espaçada
Liste meus cards do último mês
Traga o conteúdo do card X focando em 'preço'
```
