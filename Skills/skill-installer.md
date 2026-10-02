# skill-installer

**Agente:** Codex
**Local:** `~/.codex/skills/.system/skill-installer/SKILL.md`
**Tipo:** Instalação de skills

## Descrição

Instala skills do Codex em `$CODEX_HOME/skills` a partir de uma lista curada ou repositório GitHub.

## Fontes

- **Curada:** `https://github.com/openai/skills/tree/main/skills/.curated`
- **Experimental:** `https://github.com/openai/skills/tree/main/skills/.experimental`
- **Outros repos:** Qualquer repo GitHub (incluindo privados)

## Scripts

| Script | Descrição |
|--------|-----------|
| `scripts/list-skills.py` | Lista skills com anotações de instaladas |
| `scripts/list-skills.py --format json` | Lista em JSON |
| `scripts/install-skill-from-github.py --repo <owner>/<repo> --path <path>` | Instala de repo GitHub |
| `scripts/install-skill-from-github.py --url <url>` | Instala via URL |

## Comportamento

- Padrão: download direto para repos públicos
- Fallback: git sparse checkout (se download falhar com auth)
- Aborta se o diretório de destino já existir
- Instala em `$CODEX_HOME/skills/<skill-name>` (padrão: `~/.codex/skills`)
- Múltiplos `--path` instalam múltiplas skills em uma execução

## Flags

- `--ref <ref>` — branch/tag (padrão: `main`)
- `--dest <path>` — diretório de destino
- `--method auto|download|git` — método de instalação
- `--name` — nome customizado para a skill

## Skills Pré-instaladas

As skills em `https://github.com/openai/skills/tree/main/skills/.system` já vêm pré-instaladas.
