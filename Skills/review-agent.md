# review-agent

**Agente:** Codex
**Local:** `~/.codex/skills/.system/review-agent/SKILL.md`
**Tipo:** Revisão de código

## Descrição

Realiza revisão read-only de mudanças de código e retorna todos os findings acionáveis. Não modifica arquivos.

## Princípios

- **Read-only** — nunca modifica arquivos, cria commits, push, ou delega
- **Defect-first** — foca em problemas concretos que o autor corrigiria
- **Completo** — continua após o primeiro problema, revisa todo o diff

## Prioridades

| Nível | Descrição |
|-------|-----------|
| `P0` | Blocker universal ou falha crítica |
| `P1` | Defeito urgente (corrigir em seguida) |
| `P2` | Defeito comum (deve corrigir) |
| `P3` | Baixo impacto (ainda vale corrigir) |

## Formato de Output

```
[P1] Título imperativo — path/to/file.rs:Line

Parágrafo curto explicando o cenário afetado e por que está errado.
```

## Quando Flag

Flag APENAS se **todas** as condições forem verdadeiras:

1. Afeta correção, segurança, performance ou manutenibilidade
2. É discreto e acionável
3. Foi introduzido pela mudança revisada
4. O cenário pode ser demonstrado pelo código
5. O autor provavelmente corrigiria

## Quando NÃO Flag

- Preocupações especulativas
- Problemas pre-existentes
- Mudanças intencionais de comportamento
- Style nits que não obscurecem o código

## Se Não Houver Findings

Escrever: `No findings.`
