# imagegen

**Agente:** Codex
**Local:** `~/.codex/skills/.system/imagegen/SKILL.md`
**Tipo:** Geração de imagens

## Descrição

Gera ou edita imagens raster (fotos, ilustrações, texturas, sprites, mockups, cutouts transparentes).

## Modos

1. **Built-in (padrão):** Ferramenta `image_gen` integrada. Não requer `OPENAI_API_KEY`.
2. **CLI fallback:** `scripts/image_gen.py`. Requer `OPENAI_API_KEY`. Usar apenas quando o usuário pedir explicitamente.

## Subcomandos CLI

- `generate` — gera nova imagem
- `edit` — edita imagem existente
- `generate-batch` — gera múltiplas imagens

## Quando Usar

**Usar:**
- Gerar nova imagem (concept art, produto, hero, capa)
- Gerar imagem a partir de referências
- Editar imagem existente (inpainting, remoção, compositing)
- Produzir muitos assets/variantes

**Não usar:**
- Estender SVG/ícones vetoriais existentes
- Formas simples, diagramas, wireframes
- Edições pequenas em arquivos nativos editáveis

## Taxonomia de Use Cases

**Generate:** `photorealistic-natural`, `product-mockup`, `ui-mockup`, `infographic-diagram`, `scientific-educational`, `ads-marketing`, `productivity-visual`, `logo-brand`, `illustration-story`, `stylized-concept`, `historical-scene`

**Edit:** `text-localization`, `identity-preserve`, `precise-object-edit`, `lighting-weather`, `background-extraction`, `style-transfer`, `compositing`, `sketch-to-render`

## Schema de Prompt

```text
Use case: <taxonomy slug>
Asset type: <onde será usado>
Primary request: <prompt principal>
Input images: <Image 1: role>
Scene/backdrop: <ambiente>
Subject: <assunto>
Style/medium: <foto/ilustração/3D>
Composition/framing: <wide/close/top-down>
Lighting/mood: <iluminação + mood>
Color palette: <paleta>
Materials/textures: <superfícies>
Text (verbatim): "<texto exato>"
Constraints: <manter/evitar>
Avoid: <restrições negativas>
```

## Modelos CLI

- **gpt-image-2** (padrão) — não suporta `background=transparent`
- **gpt-image-1.5** — suporte a transparent (pedir antes de usar)

## Tamanhos Populares

- `1024x1024` — square rápido
- `1536x1024` — landscape
- `1024x1536` — portrait
- `3840x2160` — 4K landscape
- `2160x3840` — 4K portrait
