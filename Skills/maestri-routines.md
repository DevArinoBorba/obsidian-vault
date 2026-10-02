# maestri-routines

**Agente:** Claude Code
**Local:** `~/.claude/skills/maestri-routines/SKILL.md`
**Tipo:** Automação agendada

## Descrição

Gerencia rotinas agendadas no canvas Maestri (comandos recorrentes e lembretes). Requer **Maestro Mode**.

## Comandos Principais

| Comando | Descrição |
|---------|-----------|
| `maestri routine list` | Lista todas as rotinas |
| `maestri routine show "Name"` | Detalhes de uma rotina |
| `maestri routine create "Name" --command "..." <schedule>` | Cria nova rotina |
| `maestri routine edit "Name" [options]` | Edita rotina existente |
| `maestri routine enable "Name"` | Retoma rotina |
| `maestri routine disable "Name"` | Pausa rotina |
| `maestri routine run "Name"` | Executa imediatamente (teste) |
| `maestri routine delete "Name"` | Remove rotina (destrutivo) |

## Agendamentos (escolher um)

| Flag | Exemplo | Descrição |
|------|---------|-----------|
| `--every` | `--every 30m` | Intervalo (45s, 30m, 2h, 1h30m) |
| `--daily` | `--daily 09:00` | Todo dia às 09:00 |
| `--weekly` | `--weekly mon,wed,fri@09:00` | Dias da semana |
| `--once` | `--once "2026-06-20 15:00"` | Uma única vez |

## Targets

- *(omit)* — próprio terminal (padrão)
- `--terminal "Name"` — outro terminal
- `--reminder` — notificação desktop (sem terminal)

## Opções

- `--count N` — para após N execuções
- `--until "2026-07-01"` — para em uma data
- `--pre-run "script"` — roda antes cada execução
- `--no-skip-if-busy` — executa mesmo se terminal ocupado
- `--no-notify` — não notifica ao executar
- `--disabled` — cria pausada

## Exemplos

```bash
maestri routine create "Daily digest" --command "Summarize commits" --daily 18:00
maestri routine create "Nightly audit" --command "npm audit" --daily 02:00 --terminal "Backend"
maestri routine create "Standup" --command "Time for standup" --weekly mon,tue,wed,thu,fri@09:00 --reminder
```
