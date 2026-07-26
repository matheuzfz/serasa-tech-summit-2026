# Na Minha Máquina Funciona — Serasa Tech Summit 2026

[![Build and Deploy Presentation](https://github.com/matheuzfz/serasa-tech-summit-2026/actions/workflows/deploy.yml/badge.svg)](https://github.com/matheuzfz/serasa-tech-summit-2026/actions/workflows/deploy.yml)

> DevOps, Infraestrutura como Código e o fim da frase mais perigosa da engenharia de software: **"na minha máquina funciona"**.

## Sobre a palestra

Todo desenvolvedor já disse — ou ouviu — a famosa frase "mas na minha máquina funciona!". Ela parece inofensiva, mas é sintoma de um problema muito maior: ambientes irreprodutíveis, deploys manuais, permissões mal configuradas e um abismo cultural entre quem escreve o código e quem opera a infraestrutura.

Nesta talk, percorremos a anatomia dessa mentira: do paraíso ilusório do `localhost`, passando pelas armadilhas da máquina corporativa, pelo labirinto da topologia de rede e pela vingança da latência — até chegar na saída: **Infraestrutura como Código (Terraform)**, **pipelines de CI/CD** e a **cultura DevOps** resumida na frase de Werner Vogels: *"You build it, you run it."*

## Assistindo aos slides

Os slides são gerados automaticamente com [Reveal.js](https://revealjs.com/) (via [reveal-md](https://github.com/webpro/reveal-md)) e publicados no **GitHub Pages** a cada push na branch `main`:

**➡️ [https://matheuzfz.github.io/serasa-tech-summit-2026/](https://matheuzfz.github.io/serasa-tech-summit-2026/)**

Navegação: setas do teclado (`→` / `←`), `Esc` para visão geral dos slides.

## Rodando localmente

Pré-requisito: [Node.js](https://nodejs.org/) 20+.

```bash
# Servidor de preview com hot-reload
npx reveal-md presentation.md

# Gerar o site estático (mesmo build do CI)
npx reveal-md presentation.md --static _site
```

## Estrutura do repositório

```text
├── .github/workflows/deploy.yml   # Pipeline CI/CD (test → build → deploy)
├── .markdownlint.json             # Regras de lint do Markdown
├── assets/                        # Imagens e GIFs locais (fallback offline)
└── presentation.md                # Fonte dos slides (Reveal.js)
```

## Pipeline de CI/CD

O workflow [`deploy.yml`](.github/workflows/deploy.yml) roda em três jobs encadeados:

1. **test** — lint do `presentation.md` com `markdownlint-cli`.
2. **build** — gera o site estático em `_site/` com `reveal-md --static` e publica como artefato do Pages.
3. **deploy** — publica o artefato no ambiente `github-pages`.

## Nota sobre os memes

Cada meme dos slides usa uma tag `<img>` com link do Giphy como fonte primária e **fallback automático** para um arquivo local em `assets/` — se o Wi-Fi falhar no dia da apresentação, os slides continuam funcionando offline:

```html
<img src="LINK_DO_GIPHY" onerror="this.onerror=null; this.src='assets/arquivo.gif';" alt="Descrição" width="600">
```

Para o fallback funcionar, baixe os GIFs e salve-os em `assets/` com os nomes referenciados no `presentation.md`.

---

Palestra apresentada no **Serasa Tech Summit 2026**.
