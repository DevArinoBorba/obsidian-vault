# skill-creator

**Agente:** Codex
**Local:** `~/.codex/skills/.system/skill-creator/SKILL.md`
**Tipo:** Criação de skills

## Descrição

Cria ou atualiza uma skill do Codex com instruções adequadamente scoped e recursos de suporte.

## Princípios

1. **Assuma que o Codex já é capaz** — inclua apenas o que muda decisões
2. **Preserve a intenção do usuário** — não expanda escopo
3. **Especificidade proporcional ao risco** — detalhes apenas quando necessário
4. **Discovery barato e preciso** — nome e description claros
5. **Disclose progressivamente** — SKILL.md enxuto, references para detalhes

## Anatomia de uma Skill

```
skill-name/
|-- SKILL.md                 Obrigatório (frontmatter + markdown)
|   |-- YAML frontmatter     name + description
|   `-- Markdown body       Instruções carregadas ao usar
|-- agents/                  Opcional (openai.yaml)
|-- scripts/                 Opcional (executáveis)
|-- references/              Opcional (docs carregados conforme necessidade)
`-- assets/                  Opcional (arquivos de output)
```

## Frontmatter

```yaml
---
name: my-skill
description: "Descrição curta e discriminante de quando usar"
---
```

## Nomenclatura

- Letras minúsculas, dígitos e hífens
- Máximo 64 caracteres
- Preferir nomes curtos e orientados a ação
- Namespace por tool/domínio quando melhorar discovery

## Validação

```bash
scripts/quick_validate.py <path/to/skill-folder>
```

## Inicialização

```bash
scripts/init_skill.py <skill-name> --path <output-dir> [--resources scripts,references,assets]
```
