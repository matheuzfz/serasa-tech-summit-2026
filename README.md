# 🖥️ Na Minha Máquina Funciona — Serasa Tech Summit 2026

[![Build and Deploy](https://github.com/matheuzfz/serasa-tech-summit-2026/actions/workflows/deploy.yml/badge.svg)](https://github.com/matheuzfz/serasa-tech-summit-2026/actions/workflows/deploy.yml)

![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![GitHub Actions](https://img.shields.io/badge/github%20actions-%232088FF.svg?style=for-the-badge&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white)
![Terraform](https://img.shields.io/badge/terraform-%235835CC.svg?style=for-the-badge&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)

---

## Sobre o Projeto

Este repositório decreta o **fim definitivo** da desculpa mais perigosa da engenharia de software: _"na minha máquina funciona"_. Aqui, desmontamos — com código, arquitetura e cultura — o abismo que separa o **paraíso ilusório do `localhost`** do **caos implacável da produção**. Ambientes irreprodutíveis, deploys manuais no escuro, permissões que "alguém configurou um dia" e aquele banco local que nunca refletiu a realidade: tudo isso acaba aqui. Se o seu código não sobrevive fora do seu notebook, ele não funciona — _ponto_.

---

## 🌐 Live Demo

> **A palestra foi transformada em uma experiência web imersiva.**
> Uma Single Page Application com estética **Hacker/Cyberpunk** — fundo preto, verde neon e SVGs inline gerados por IA — que traduz cada conceito da talk em uma seção interativa e navegável.
>
> **🔗 Acesse agora:** [https://matheuzfz.github.io/serasa-tech-summit-2026](https://matheuzfz.github.io/serasa-tech-summit-2026)

---

## 📋 Tópicos Abordados na Landing Page

- **🏝️ A Ilusão do Localhost** — Por que o seu ambiente local mente para você todos os dias.
- **🌐 O Labirinto de VPCs** — Topologia de rede, firewalls e o tráfego que nunca chega onde deveria.
- **⏱️ Latência & Consultas N+1** — A vingança silenciosa que só aparece em produção, com milhares de usuários simultâneos.
- **🏗️ Infraestrutura como Código (Terraform)** — Pare de clicar em consoles. Declare, versione, revise.
- **🚀 CI/CD — Pipelines que Validam** — Do commit ao deploy: automação end-to-end com GitHub Actions.
- **🤝 "DevOps não é cargo, é cultura"** — _"You build it, you run it."_ — Werner Vogels.

---

## 🛠️ Stack Tecnológica & Pipeline

### Frontend

| Camada       | Tecnologia                          |
|:-------------|:------------------------------------|
| Estrutura    | HTML5 semântico (strict)            |
| Estilização  | CSS3 puro (custom properties, animações, media queries) |
| Interação    | JavaScript Vanilla (ES6+)           |
| Ilustrações  | SVGs inline gerados por IA          |
| Design       | Estética Hacker/Cyberpunk (dark theme, verde neon `#00ff41`) |

### Infraestrutura & Deploy

O deploy é **100% automatizado via Infraestrutura como Código** utilizando **GitHub Actions**. Nenhuma etapa manual, nenhum _"sobe aí na mão"_.

```text
push → [test] → [build] → [deploy] → GitHub Pages (produção)
```

O workflow [`deploy.yml`](.github/workflows/deploy.yml) executa três jobs encadeados:

1. **`test`** — Valida a integridade do `index.html`.
2. **`build`** — Gera o site estático em `_site/` e publica como artefato do Pages.
3. **`deploy`** — Publica o artefato no ambiente `github-pages`.

### Estrutura do Repositório

```text
serasa-tech-summit-2026/
├── .github/
│   └── workflows/
│       └── deploy.yml          # Pipeline CI/CD (test → build → deploy)
├── assets/                     # Recursos estáticos (imagens, GIFs)
├── index.html                  # SPA — toda a Landing Page em um único arquivo
├── presentation.md             # Conteúdo-fonte da palestra (Markdown)
├── .markdownlint.json          # Regras de lint do Markdown
└── README.md                   # Você está aqui 👋
```

---

## 👤 Sobre o Autor

**Matheus Finkbeiner dos Santos**
Backend & SRE Engineer — Time de Delivery, Serasa Experian
📍 Joinville, SC — Brasil

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/seu-perfil-linkedin)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/matheuzfz)

---

<p align="center">
  Palestra apresentada no <strong>Serasa Tech Summit 2026</strong><br/>
  <em>"If it's not in the pipeline, it doesn't exist."</em>
</p>
