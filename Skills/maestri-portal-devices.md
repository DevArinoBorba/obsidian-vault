# maestri-portal-devices

**Agente:** Claude Code
**Local:** `~/.claude/skills/maestri-portal-devices/SKILL.md`
**Tipo:** Automação Android

## Descrição

Controla um emulador Android ou telefone físico no canvas Maestri. Tap, type, screenshot, lê árvore de acessibilidade e lança apps.

## Comandos Principais

### Gerenciamento

| Comando | Descrição |
|---------|-----------|
| `maestri portal devices` | Lista devices conectados e AVDs |
| `maestri portal create --simulator ID ["Name"]` | Abre portal em um device |

### Interação

| Comando | Descrição |
|---------|-----------|
| `maestri portal click "Pixel" @e3` | Tap no elemento |
| `maestri portal click "Pixel" 540,1200` | Tap nas coordenadas |
| `maestri portal type "Pixel" "text"` | Digita texto |
| `maestri portal key "Pixel" Enter` | Pressiona tecla |
| `maestri portal key "Pixel" back` | Botão voltar |
| `maestri portal scroll "Pixel" down 400` | Scroll |
| `maestri portal swipe "Pixel" @e3 @e9` | Swipe entre elementos |
| `maestri portal button "Pixel" home` | Botão físico |

### Apps e Captura

| Comando | Descrição |
|---------|-----------|
| `maestri portal launch "Pixel" com.example.app` | Lança app |
| `maestri portal terminate "Pixel" com.example.app` | Para app |
| `maestri portal navigate "Pixel" "url"` | Abre URL |
| `maestri portal screenshot "Pixel"` | Captura PNG |
| `maestri portal info "Pixel"` | Info do device |

## Botões Android

`back`, `home`, `recents`, `menu`, `power`, `volumeup`, `volumedown`

## Fluxo Recomendado

1. `snapshot` — lê a tela e obtem refs
2. Interaja com refs, coordenadas, texto e teclas
3. `snapshot` novamente para verificar resultado
4. Refresh snapshot quando refs ficarem stale
