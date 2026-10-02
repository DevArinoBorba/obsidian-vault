# maestri-manager

**Agente:** Claude Code
**Local:** `~/.claude/skills/maestri-manager/SKILL.md`
**Tipo:** Orquestração de equipe

## Descrição

Cria e conecta terminals de agents no canvas Maestri, gerencia roles e envia notificações push.

## Comandos Principais

| Comando | Descrição |
|---------|-----------|
| `maestri notify "msg"` | Envia notificação push ao usuário |
| `maestri recruit "Name" [--preset] [--role] [--floor] [--workspace] [--command] [--dir]` | Cria novo agent |
| `maestri recruit "New" --preset "X" --replace "Old"` | Substitui agent mantendo o terminal |
| `maestri dismiss "Name"` | Remove agent do canvas |
| `maestri connect "From" "To"` | Conecta dois elements (agent/note/portal) |
| `maestri preset list` | Lista presets de agents |
| `maestri role list` | Lista roles disponíveis |
| `maestri role create "Name" "Prompt" [--scope]` | Cria nova role |
| `maestri role show "Name"` | Mostra prompt completo da role |
| `maestri role edit "Name" "old" "new"` | Edita parte do prompt |
| `maestri role write "Name" "prompt"` | Substitui prompt inteiro |
| `maestri role assign "Recruit" "Role"` | Atribui role a um recruit |

## Fluxo de Trabalho

1. **Inventário** — `maestri list` primeiro
2. **Planejar** — Identificar roles faltantes
3. **Definir** — Criar roles com `maestri role create`
4. **Recrutar** — Criar agents com `maestri recruit`
5. **Conectar** — `maestri connect` entre agents que precisam colaborar
6. **Delegar** — `maestri ask` ou `maestri ask --batch` para paralelizar

## Boas Práticas

- **Reutilizar antes de recrutar** — Sempre verifique `maestri list` antes de criar novo agent
- Nomeie com codinomes únicos (não reuse o nome da role)
- Use `--replace` em vez de `dismiss` + `recruit` para trocar o agent
- Bake colaboração nas prompts das roles (mencionar peers e notes)
