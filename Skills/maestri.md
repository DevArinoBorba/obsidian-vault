# maestri

**Agente:** Claude Code
**Local:** `~/.claude/skills/maestri/SKILL.md`
**Tipo:** Comunicação inter-agents

## Descrição

Envia mensagens para agents conectados no canvas Maestri e obtém respostas. Também lê e escreve notas conectadas (sticky notes).

## Comandos Principais

| Comando | Descrição |
|---------|-----------|
| `maestri list` | Lista agents, notes e portais conectados |
| `maestri ask "Agent" "prompt"` | Envia prompt para um agent |
| `maestri ask --batch '{...}'` | Envia para múltiplos agents em paralelo |
| `maestri check "Agent"` | Lê output atual do terminal do agent |
| `maestri note create` | Cria uma nota no canvas |
| `maestri note read "Name"` | Lê uma nota |
| `maestri note write "Name" "content"` | Substitui conteúdo da nota |
| `maestri note edit "Name" "old" "new"` | Edita parte da nota |
| `maestri note stack "Name" ["Stack"]` | Arquiva nota em um fichário |
| `maestri note delete "Name"` | Remove nota (destrutivo) |

## Notas Importantes

- Sempre rode `maestri list` primeiro para obter nomes exatos
- Agents de outro workspace aparecem como `Name @ Workspace`
- Use `maestri debug` se houver erros de conexão
- Timeout: 1min (fácil) a 10min (tarefas complexas)
- Se o agent estiver ocupado, use `maestri check` para ver progresso
