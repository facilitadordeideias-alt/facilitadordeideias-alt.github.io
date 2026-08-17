<div align="center">

<img src="./og-image.png" alt="Vitor Henrique — Transformando negócios em máquinas de venda" width="720">

# Vitor Henrique · Vital Assessoria

**Transformando negócios em máquinas de venda.**

Landing pages de Growth Marketing, processo comercial e posicionamento estratégico —
estáticas, sem build, publicadas direto no GitHub Pages.

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-online-3fd06a?style=for-the-badge&logo=github&logoColor=0b0d0c&labelColor=0b0d0c)](https://facilitadordeideias-alt.github.io)
[![Site](https://img.shields.io/badge/vitalevender.com.br-canonical-f2f4f1?style=for-the-badge&labelColor=0b0d0c)](https://vitalevender.com.br)
[![HTML](https://img.shields.io/badge/HTML-est%C3%A1tico-e34f26?style=for-the-badge&logo=html5&logoColor=fff&labelColor=0b0d0c)](#-stack)
[![Build](https://img.shields.io/badge/build-nenhum-8b978e?style=for-the-badge&labelColor=0b0d0c)](#-como-rodar-local)

</div>

---

## ✦ Sobre

Este repositório hospeda a presença online de **Vitor Henrique** — fundador e CEO da
**Vital Assessoria de Marketing**, em Rondônia — e da própria Vital.

São páginas estáticas, escritas à mão, sem framework e sem etapa de build: o navegador
recebe exatamente o que está no repositório. O objetivo é simples — **captar diagnósticos
de 30 minutos pelo WhatsApp** com uma página rápida, bem indexada e bonita no
compartilhamento social.

## ✦ Páginas

| Arquivo | O que é | Público |
|---|---|---|
| [index.html](index.html) | Landing page pessoal do Vitor Henrique — hero, dores, três pilares, método em 4 etapas, sobre, depoimentos e CTA | Empresários buscando destravar venda |
| [Vital - Landing Page.dc.html](Vital%20-%20Landing%20Page.dc.html) | Landing page institucional da Vital Assessoria — método, serviços e diagnóstico | Clientes da assessoria |
| [OG Image.dc.html](OG%20Image.dc.html) | Template 1200×630 usado para gerar o card social | Origem do `og-image.png` |

## ✦ Estrutura

```
.
├── index.html                     # ← página publicada (raiz do GitHub Pages)
├── Vital - Landing Page.dc.html   # landing da Vital Assessoria
├── OG Image.dc.html               # template do card social 1200×630
├── support.js                     # runtime dc — gerado, não editar à mão
├── image-slot.js                  # web component <image-slot> (placeholder de imagem)
├── og-image.png                   # card Open Graph / Twitter
├── vitor-cutout.png               # recorte do Vitor usado no hero
├── check-cutout.png               # conferência do recorte
└── uploads/                       # fotos e assets de origem
```

## ✦ Stack

Deliberadamente mínima:

- **HTML estático** com estilos inline — sem CSS externo, sem bundler, sem `node_modules`
- **`support.js`** — runtime `dc` que interpreta `<x-dc>`, `<sc-for>`, `<sc-if>` e o bloco
  `<script type="text/x-dc">` com a classe `Component extends DCLogic`
- **`image-slot.js`** — web component `<image-slot>` para slots de imagem preenchíveis
- **Fontes** — [Archivo](https://fonts.google.com/specimen/Archivo) (títulos e corpo) +
  [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono) (labels e detalhes)
- **SEO** — canonical, Open Graph, Twitter Card e JSON-LD `schema.org/Person` já no `<head>`
- **Acessibilidade** — todas as animações respeitam `prefers-reduced-motion`

> `support.js` é **gerado** a partir do `dc-runtime`. Não edite o arquivo diretamente.

## ✦ Paleta

| | Token | Hex | Uso |
|---|---|---|---|
| ⬛ | Base | `#0b0d0c` | Fundo principal |
| ⬛ | Superfície | `#0e1210` / `#101613` | Cards e faixas |
| 🟩 | Verde Vital | `#3fd06a` | CTA, destaques, links em hover |
| 🟧 | Laranja | `#f26a1b` | Brilho de fundo (14% de opacidade) |
| ⬜ | Texto | `#f2f4f1` | Títulos |
| ⬜ | Texto suave | `#b4bfb8` / `#8b978e` | Corpo e legendas |
| ⬛ | Borda | `#1d2621` | Divisórias e contornos |

A landing da Vital usa uma variação mais quente: base `#0e1310`, acento `#a8e06a`.

## ✦ Como rodar local

Não há dependências para instalar. Basta servir a pasta por HTTP — abrir o arquivo com
`file://` quebra os scripts.

```bash
# Python
python -m http.server 8000

# ou Node
npx serve .
```

Depois abra <http://localhost:8000>.

## ✦ Props editáveis

As páginas expõem propriedades no bloco `data-props`, ajustáveis sem mexer no layout:

| Página | Prop | Tipo | Padrão | Efeito |
|---|---|---|---|---|
| `index.html` | `showQuotes` | booleano | `true` | Mostra ou esconde a seção de depoimentos |
| `index.html` | `ctaMode` | `Formulário` \| `Só WhatsApp` | `Formulário` | Alterna entre formulário de contato e botão direto |
| `Vital - Landing Page` | `showMetrics` | booleano | `true` | Mostra ou esconde os números |
| `Vital - Landing Page` | `ctaMode` | `Formulário` \| `Só WhatsApp` | `Formulário` | Mesmo comportamento acima |

## ✦ Antes de publicar

Alguns pontos ainda estão com conteúdo de exemplo:

- [ ] **Número do WhatsApp** — hoje é o placeholder `wa.me/5569000000000`, presente em 3 links
- [ ] **Depoimentos** — os três cards da seção "Quem já passou por aqui" são fictícios
      (a própria página avisa: *"Substitua por depoimentos reais antes de publicar"*)
- [ ] **Formulário** — o botão apenas troca o rótulo; ainda não envia para lugar nenhum
- [ ] **Domínio** — o canonical aponta para `vitalevender.com.br`, mas não existe arquivo
      `CNAME` no repositório; sem ele o Pages serve apenas em `facilitadordeideias-alt.github.io`

## ✦ Deploy

O deploy é o próprio `git push`: o GitHub Pages publica a branch `main` a partir da raiz e
serve o `index.html`.

```bash
git add .
git commit -m "Atualiza landing page"
git push
```

## ✦ Contato

- 💬 WhatsApp — diagnóstico gratuito de 30 minutos
- 📸 [@facilitadordeideias](https://www.instagram.com/facilitadordeideias/)
- 📸 [@vitalevender](https://www.instagram.com/vitalevender/)
- 🌐 [vitalevender.com.br](https://vitalevender.com.br)

<div align="center">

---

**Vitor Henrique** — Fundador & CEO, Vital Assessoria de Marketing · Rondônia, Brasil

<sub>Não faço promessa sem entender seu contexto — cada negócio é único, cada estratégia também.</sub>

</div>
