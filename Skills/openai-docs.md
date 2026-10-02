# openai-docs

**Agente:** Codex
**Local:** `~/.codex/skills/.system/openai-docs/SKILL.md`
**Tipo:** Documentação oficial

## Descrição

Fornece documentação oficial da OpenAI, API, modelos e Codex. Sempre busca a fonte oficial antes de responder.

## Fontes Oficiais

- `developers.openai.com`
- `platform.openai.com`
- `learn.chatgpt.com`

## Rotas

| Rota | Quando Usar |
|------|-------------|
| `references/mcp-diagnostics.md` | Integração local de docs (quando pedido) |
| `references/model-migration.md` | Migração de modelos, upgrades |
| `references/model-selection.md` | Comparação de modelos (custo, latência, qualidade) |
| `references/official-docs.md` | APIs, ChatGPT Work, comparações |
| `references/codex-self-knowledge.md` | Setup amplo do Codex, orientação |

## Regras

- **Sempre buscar a fonte oficial primeiro** antes de responder
- Preservar o modelo explicitamente pedido (nunca substituir por mais novo)
- Citar a página que suporta a afirmação
- Para tasks de software genéricas, responder diretamente
- Para implementação/debug de API, usar `openai-platform-api-key` primeiro
