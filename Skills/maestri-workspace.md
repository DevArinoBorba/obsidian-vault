# maestri-workspace

**Agente:** Claude Code
**Local:** `~/.claude/skills/maestri-workspace/SKILL.md`
**Tipo:** Provisionamento

## Descrição

Cria novos workspaces e floors Maestri via CLI, opcionalmente clonando um workspace existente. Requer **Maestro Mode**.

## Comandos Principais

### Workspaces

| Comando | Descrição |
|---------|-----------|
| `maestri workspace create "Name" --dir PATH [--from "Source"] [--group] [--folder]` | Cria workspace |
| `maestri workspace move "Name" --group/--folder/--root` | Reorganiza na sidebar |
| `maestri workspace rename "Old" "New"` | Renomeia workspace |
| `maestri workspace list` | Lista hierarquia da sidebar |

### Floors

| Comando | Descrição |
|---------|-----------|
| `maestri floor create "Name" [--branch] [--existing-branch] [--no-git] [--copy-ground]` | Cria floor |
| `maestri floor list` | Lista floors do workspace |

## Conceitos

- **Workspace** — canvas isolado, rooted em um diretório (isolamento entre projetos)
- **Floor** — nível dentro de um workspace, opcionalmente com clone git isolado (isolamento dentro de projeto)

## Flags Importantes

- `--from "Source"` — clona layout do canvas (terminals, notes, trees, floors, connections)
- `--group "Group"` — arquiva workspace em um grupo na sidebar
- `--folder "Folder"` — arquiva dentro de uma pasta
- `--branch NAME` — branch para o clone isolado do floor
- `--no-git` — pula isolamento, compartilha o diretório ground
- `--copy-ground` — copia layout do ground floor

## Exemplos

```bash
maestri workspace create "New Project" --dir ~/projects/new --from "Template"
maestri floor create "Experiment" --branch feat/idea
maestri floor create "Scratch" --no-git
```
