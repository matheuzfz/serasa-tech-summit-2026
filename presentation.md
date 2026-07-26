---
title: "Na Minha Máquina Funciona — Serasa Tech Summit 2026"
theme: dracula
revealOptions:
  transition: slide
  transitionSpeed: default
  slideNumber: true
---

<!-- Slide 1: Capa -->

# SERASA TECH SUMMIT 2026

## "Na Minha Máquina Funciona"

### DevOps, IaC e o fim da desculpa mais antiga da TI

---

<!-- Slide 2: Sobre Mim -->

## Sobre Mim

- **Backend & SRE** — vivo entre o código e a infraestrutura
- De **Joinville**, Santa Catarina
- **Maker** nas horas vagas: impressão 3D, automação e projetos que piscam LEDs
- Já disse "na minha máquina funciona" mais vezes do que gosto de admitir

---

<!-- Slide 3: A Anatomia da Mentira -->

## A Anatomia da Mentira

> "Funciona na minha máquina."

A frase mais dita — e menos verdadeira — da engenharia de software.

<img src="https://media.giphy.com/media/l0HlMG1EX2H38cZeE/giphy.gif" onerror="this.onerror=null; this.src='assets/this-is-fine.gif';" alt="Meme This is Fine: cachorro cercado de fogo dizendo que está tudo bem" width="600">

---

<!-- Slide 4: O Paraíso chamado Localhost -->

## O Paraíso chamado Localhost

No seu ambiente local, tudo é perfeito:

- Banco de dados rodando na porta padrão, sem senha
- Todas as dependências instaladas (na versão certa!)
- Zero firewall, zero proxy, zero latência
- Você é **root** da sua própria máquina

---

<!-- Slide 5: O Paraíso chamado Localhost (continuação) -->

## É quase mágico ✨

<img src="https://media.giphy.com/media/sEqG2g9RGj91PgSRnz/giphy.gif" onerror="this.onerror=null; this.src='assets/bob-esponja-magica.gif';" alt="Meme Bob Esponja criando um arco-íris mágico com as mãos" width="600">

O problema: **produção não é mágica. É física.**

---

<!-- Slide 6: A Armadilha da Máquina Corporativa -->

## A Armadilha da Máquina Corporativa

O notebook da empresa chega cheio de "proteção":

- Antivírus varrendo seu `node_modules` a cada build
- VPN que derruba suas conexões a cada 30 minutos
- Proxy corporativo bloqueando metade da internet

Segurança sem contexto vira um portão trancado... no meio de um gramado aberto.

<img src="assets/portao-inutil.gif" onerror="this.onerror=null; this.src='assets/portao-inutil.gif';" alt="Meme do portão inútil: portão fechado no meio de um gramado sem cerca nenhuma" width="600">

---

<!-- Slide 7: O Perigo da Abstração -->

## O Perigo da Abstração

Frameworks e SDKs escondem o mundo real de você:

- `fetch()` esconde DNS, TCP, TLS, proxy e timeout
- ORM esconde locks, índices e o plano de execução da query
- `docker run` esconde cgroups, namespaces e limites de recurso

**Abstração não elimina complexidade. Ela só adia a conta.**

---

<!-- Slide 8: O Labirinto da Topologia de Rede -->

## O Labirinto da Topologia de Rede

Entre o seu código e o usuário existem:

- Load balancers, API gateways e service meshes
- VPCs, subnets, security groups e NAT
- DNS interno, DNS externo e TTLs que ninguém lembra

---

<!-- Slide 9: O Labirinto da Topologia de Rede (continuação) -->

## Você, debugando em produção

<img src="https://media.giphy.com/media/l0IylOPCNkiqOgMyA/giphy.gif" onerror="this.onerror=null; this.src='assets/charlie-conspiracy.gif';" alt="Meme Charlie Conspiracy: personagem apontando para um quadro cheio de conspirações conectadas por barbante" width="600">

Se a sua explicação para o bug precisa de barbante vermelho, **a arquitetura precisa de revisão.**

---

<!-- Slide 10: A Vingança da Latência -->

## A Vingança da Latência

No `localhost`, cada chamada leva ~0 ms.

Em produção: rede real, regiões distantes, TLS handshake, filas...

Uma query de 1 ms vira 200 ms. Multiplique por 50 chamadas.

<img src="https://media.giphy.com/media/yFqqeswEdw84o/giphy.gif" onerror="this.onerror=null; this.src='assets/preguica-zootopia.gif';" alt="Meme da preguiça Flash de Zootopia reagindo em câmera lentíssima" width="600">

---

<!-- Slide 11: Permissões e Variáveis -->

## Permissões e Variáveis

Os dois clássicos do "só quebra em produção":

- **Permissões:** local você é admin; em produção, a role da aplicação não tem acesso ao bucket
- **Variáveis de ambiente:** o `.env` perfeito existe só na sua máquina — e nunca foi commitado (ainda bem)

Se a configuração mora na cabeça de alguém, **o ambiente não é reproduzível.**

---

<!-- Slide 12: A Virada de Chave -->

## A Virada de Chave

> "You build it, you run it."
>
> — **Werner Vogels**, CTO da Amazon

Quem escreve o código deve sentir as consequências dele em produção. Responsabilidade de ponta a ponta muda a forma como escrevemos software.

---

<!-- Slide 13: Terraform e IaC -->

## Terraform e IaC

Infraestrutura como Código transforma ambiente em artefato:

```hcl
resource "aws_s3_bucket" "app" {
  bucket = "serasa-tech-summit-2026"
}
```

- Ambiente **descrito em código**, versionado no Git
- `terraform plan` mostra o que vai mudar **antes** de mudar
- Dev, staging e prod nascem da **mesma fonte**
- O fim do "cliquei no console e não lembro o quê"

---

<!-- Slide 14: CI/CD — A Ponte Incorruptível -->

## CI/CD: A Ponte Incorruptível

Entre o `git push` e a produção, ninguém toca em nada manualmente:

1. **Test** — lint, testes unitários, validação
2. **Build** — artefato imutável, gerado uma única vez
3. **Deploy** — o mesmo artefato promovido entre ambientes

A pipeline não esquece passos, não tem pressa e não diz "na minha máquina funcionava".

Estes slides foram publicados exatamente assim — meta, eu sei.

---

<!-- Slide 15: A Cultura DevOps -->

## A Cultura DevOps

Ferramenta sem cultura é só gasto de dinheiro.

**Para Devs:** produção não é "problema da infra" — instrumente, observe, assuma o pager.

**Para Infra:** pare de dizer "não" e comece a dizer "como" — automatize, dê autonomia com guardrails.

**DevOps não é um cargo. É um contrato de confiança entre times.**

---

<!-- Slide 16: Obrigado / Perguntas -->

# Obrigado!

**Perguntas?**

<img src="https://media.giphy.com/media/1d7F9xyq6j7C1ojbC5/giphy.gif" onerror="this.onerror=null; this.src='assets/cachorro-sorrindo.gif';" alt="Meme do cachorro sorrindo timidamente para a câmera" width="600">

Slides disponíveis em: **matheuzfz.github.io/serasa-tech-summit-2026**
