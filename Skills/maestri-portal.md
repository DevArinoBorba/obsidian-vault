# maestri-portal

**Agente:** Claude Code
**Local:** `~/.claude/skills/maestri-portal/SKILL.md`
**Tipo:** Automação de browser

## Descrição

Usa um portal de browser no canvas Maestri para navegar na web, interagir com páginas, preencher formulários e inspecionar conteúdo.

## Comandos Principais

### Gerenciamento

| Comando | Descrição |
|---------|-----------|
| `maestri portal create URL ["Name"] [--size WxH]` | Cria portal |
| `maestri portal edit "Portal" --url URL` | Muda URL |
| `maestri portal close "Portal"` | Remove portal (destrutivo) |

### Navegação e Leitura

| Comando | Descrição |
|---------|-----------|
| `maestri portal navigate "Portal" "url"` | Navega para URL |
| `maestri portal info "Portal"` | URL, título, viewport |
| `maestri portal screenshot "Portal"` | Captura screenshot |
| `maestri portal snapshot "Portal"` | Árvore de acessibilidade com refs (`@e1`, `@e2`...) |
| `maestri portal text "Portal" @e1` | Texto do elemento |
| `maestri portal html "Portal"` | HTML completo |
| `maestri portal evaluate "Portal" "JS"` | Executa JavaScript |

### Interação

| Comando | Descrição |
|---------|-----------|
| `maestri portal click "Portal" @e3` | Clica no elemento |
| `maestri portal fill "Portal" @e2 "text"` | Preenche input |
| `maestri portal type "Portal" "text"` | Digita texto |
| `maestri portal key "Portal" "Enter"` | Pressiona tecla |
| `maestri portal select "Portal" @e5 "Option"` | Seleciona dropdown |
| `maestri portal check/uncheck "Portal" @e6` | Toggle checkbox |
| `maestri portal hover "Portal" @e3` | Passa mouse |
| `maestri portal scroll "Portal" down 300` | Scroll |

### Responsivo

| Comando | Descrição |
|---------|-----------|
| `maestri portal resize "Portal" 390 844` | Muda viewport |
| `maestri portal ua "Portal" ios` | Muda user agent |

## Seletores

- `@e3` — ref do snapshot (mais confiável)
- `#submit` — CSS selector
- `350,200` — coordenadas x,y

## Fluxo Recomendado

1. `snapshot` — entenda a estrutura e obtenha refs
2. Interaja com refs: `click @e3`, `fill @e2 "valor"`
3. `snapshot` novamente para verificar resultado
4. Se refs estiverem stale, rode snapshot novamente
