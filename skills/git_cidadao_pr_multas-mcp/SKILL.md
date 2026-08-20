---
name: git_cidadao_pr_multas-mcp
description: Skill da REST API do GIT Cidadão (PR): Multas na MCP.AI: 1 endpoint em /api/git_cidadao_pr_multas. GIT Cidadão (PR): Multas, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# GIT Cidadão (PR): Multas — REST API skill

Você tem acesso à **GIT Cidadão (PR): Multas** REST API na MCP.AI.

> GIT Cidadão (PR): Multas, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/git_cidadao_pr_multas
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
curl -X POST https://api.mcp.ai/api/git_cidadao_pr_multas/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"placa":"...","renavam":"...","pkcs12_cert":"...","pkcs12_pass":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/git_cidadao_pr_multas/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `git_cidadao_pr_multas_consultar`

GIT Cidadão (PR): Multas, consulta em fonte oficial. _(POST /api/git_cidadao_pr_multas/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `placa` | string | Sim | Parâmetro de consulta "placa". |
| `renavam` | string | Sim | Parâmetro de consulta "renavam". |
| `pkcs12_cert` | string | Sim | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Sim | Parâmetro de consulta "pkcs12_pass". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_git_cidadao_pr_multas` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
