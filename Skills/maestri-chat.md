# maestri-chat

**Agente:** Claude Code
**Local:** `~/.claude/skills/maestri-chat/SKILL.md`
**Tipo:** Chat do usuário

## Descrição

Aplica-se apenas a mensagens que abrem com o header "Maestri Chat". O agent deve responder apenas via `maestri say`.

## Comandos

| Comando | Descrição |
|---------|-----------|
| `maestri say <<'EOF' ... EOF` | Envia resposta (heredoc) |
| `maestri say 'short answer'` | Resposta curta |
| `maestri say --file <path>` | Envia conteúdo de arquivo |
| `maestri say --attach <path> 'answer'` | Anexa arquivo |
| `maestri say --progress 'text'` | Update provisório (não é a resposta final) |
| `maestri recall [thread]` | Recupera histórico da thread |

## Threads

O usuário mantém 7 threads nomeadas por cor: `blue`, `purple`, `pink`, `red`, `orange`, `yellow`, `green`.

- Na primeira mensagem ou quando a cor muda, rode `maestri recall <color>` antes de responder
- Use `maestri recall list` para ver todas as threads

## Regras

- Toda resposta via `maestri say` é um bubble visível ao usuário
- O último `maestri say` encerra o turno
- Não repetir a resposta após enviar
- `--progress` é apenas para updates curtos de status
