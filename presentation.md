---
theme: black
revealOptions:
  width: 1920
  height: 1080
  margin: 0.1
  minScale: 0.2
  maxScale: 2.0
  transition: fade
---

<style>
  .reveal h1, .reveal h2, .reveal h3 { font-weight: bold; text-transform: uppercase; margin-bottom: 40px; }
  .reveal h1 { font-size: 3.5em; color: #ffffff; }
  .reveal h2 { font-size: 2.8em; color: #f8db03; }
  .reveal p, .reveal li { font-size: 1.8em; line-height: 1.5; text-align: left; }
  .reveal ul { display: block; margin-left: 1.5em; margin-bottom: 30px; }
  .container { display: grid; grid-template-columns: 1.2fr 1fr; gap: 50px; align-items: center; width: 100%; margin-top: 40px; }
  .col-text { width: 100%; }
  .col-img img { max-width: 100%; max-height: 700px; border-radius: 15px; box-shadow: 0 15px 35px rgba(0,0,0,0.5); }
  .split-screen { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; margin-top: 50px; }
  .split-screen > div { background: rgba(255,255,255,0.08); padding: 40px; border-radius: 20px; text-align: left; }
  .highlight-quote { font-size: 3em !important; font-style: italic; color: #f8db03; line-height: 1.2; margin-top: 100px; }
</style>

<!-- Slide 1: Capa -->

# Serasa Tech Summit 2026

## "Na Minha Máquina Funciona"

DevOps, IaC e o fim da desculpa mais antiga da TI

---

<!-- Slide 2: Sobre Mim -->

## Sobre Mim

<div class="container">

<div class="col-text">

* Backend & SRE no time de Delivery do Serasa
* 10 anos atuando com infraestrutura de TI
* 2 anos atuando com desenvolvimento backend
* De Joinville, Santa Catarina
* Maker e entusiasta de impressão 3D

</div>

<div class="col-img">

<img src="assets/Sobre%20mim.jpg" alt="Foto de Matheuzfz">

</div>

</div>

---

<!-- Slide 3: A Anatomia da Mentira -->

## A Anatomia da Mentira

<div class="container">

<div class="col-text">

"Funciona na minha máquina."

A frase mais dita — e menos verdadeira — da engenharia de software.

</div>

<div class="col-img">

<img src="https://media.giphy.com/media/l0HlMG1EX2H38cZeE/giphy.gif" onerror="this.onerror=null; this.src='assets/this-is-fine.gif';" alt="Meme This is Fine: cachorro cercado de fogo dizendo que está tudo bem">

</div>

</div>

---

<!-- Slide 4: O Paraíso chamado Localhost -->

## O Paraíso chamado Localhost

No seu ambiente local, tudo é perfeito:

* Banco de dados rodando na porta padrão, sem senha
* Todas as dependências instaladas (na versão certa!)
* Zero firewall, zero proxy, zero latência
* Você é **root** da sua própria máquina

---

<!-- Slide 5: O Paraíso chamado Localhost (continuação) -->

## É Quase Mágico ✨

<div class="container">

<div class="col-text">

No localhost, tudo responde instantaneamente e nada falha.

O problema: **produção não é mágica. É física.**

</div>

<div class="col-img">

<img src="https://media.giphy.com/media/sEqG2g9RGj91PgSRnz/giphy.gif" onerror="this.onerror=null; this.src='assets/bob-esponja-magica.gif';" alt="Meme Bob Esponja criando um arco-íris mágico com as mãos">

</div>

</div>

---

<!-- Slide 6: A Armadilha da Máquina Corporativa -->

## A Armadilha da Máquina Corporativa

<div class="container">

<div class="col-text">

O notebook da empresa chega cheio de "proteção":

* Antivírus varrendo seu `node_modules` a cada build
* VPN que derruba suas conexões a cada 30 minutos
* Proxy corporativo bloqueando metade da internet

Segurança sem contexto vira um portão trancado... no meio de um gramado aberto.

</div>

<div class="col-img">

<img src="assets/portao-inutil.gif" onerror="this.onerror=null; this.src='assets/portao-inutil.gif';" alt="Meme do portão inútil: portão fechado no meio de um gramado sem cerca nenhuma">

</div>

</div>

---

<!-- Slide 7: O Perigo da Abstração -->

## O Perigo da Abstração

Frameworks e SDKs escondem o mundo real de você:

* `fetch()` esconde DNS, TCP, TLS, proxy e timeout
* ORM esconde locks, índices e o plano de execução da query
* `docker run` esconde cgroups, namespaces e limites de recurso

**Abstração não elimina complexidade. Ela só adia a conta.**

---

<!-- Slide 8: O Labirinto da Topologia de Rede -->

## O Labirinto da Topologia de Rede

Entre o seu código e o usuário existem:

* Load balancers, API gateways e service meshes
* VPCs, subnets, security groups e NAT
* DNS interno, DNS externo e TTLs que ninguém lembra

---

<!-- Slide 9: O Labirinto da Topologia de Rede (continuação) -->

## Você, Debugando em Produção

<div class="container">

<div class="col-text">

Cada hipótese vira um fio no quadro de investigação.

Se a sua explicação para o bug precisa de barbante vermelho, **a arquitetura precisa de revisão.**

</div>

<div class="col-img">

<img src="https://media.giphy.com/media/l0IylOPCNkiqOgMyA/giphy.gif" onerror="this.onerror=null; this.src='assets/charlie-conspiracy.gif';" alt="Meme Charlie Conspiracy: personagem apontando para um quadro cheio de conspirações conectadas por barbante">

</div>

</div>

---

<!-- Slide 10: A Vingança da Latência -->

## A Vingança da Latência

<div class="container">

<div class="col-text">

No `localhost`, cada chamada leva ~0 ms.

Em produção: rede real, regiões distantes, TLS handshake, filas...

Uma query de 1 ms vira 200 ms. **Multiplique por 50 chamadas.**

</div>

<div class="col-img">

<img src="https://media.giphy.com/media/yFqqeswEdw84o/giphy.gif" onerror="this.onerror=null; this.src='assets/preguica-zootopia.gif';" alt="Meme da preguiça Flash de Zootopia reagindo em câmera lentíssima">

</div>

</div>

---

<!-- Slide 11: Permissões e Variáveis -->

## Permissões e Variáveis

Os dois clássicos do "só quebra em produção":

* **Permissões:** local você é admin; em produção, a role da aplicação não tem acesso ao bucket
* **Variáveis de ambiente:** o `.env` perfeito existe só na sua máquina — e nunca foi commitado (ainda bem)

Se a configuração mora na cabeça de alguém, **o ambiente não é reproduzível.**

---

<!-- Slide 12: A Virada de Chave (Werner Vogels) -->

## A Virada de Chave

<p class="highlight-quote">"You build it, you run it."</p>

Werner Vogels — CTO da Amazon

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

* Ambiente **descrito em código**, versionado no Git
* `terraform plan` mostra o que vai mudar **antes** de mudar
* Dev, staging e prod nascem da **mesma fonte**
* O fim do "cliquei no console e não lembro o quê"

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

<div class="split-screen">

<div>

### Para Devs

Produção não é "problema da infra".

* Instrumente seu código
* Observe suas métricas
* Assuma o pager

</div>

<div>

### Para Infra

Pare de dizer "não", comece a dizer "como".

* Automatize tudo
* Dê autonomia com guardrails
* Infraestrutura como Código

</div>

</div>

DevOps não é um cargo. É um contrato de confiança entre times.

---

<!-- Slide 16: Obrigado / Perguntas -->

# Obrigado!

<div class="container">

<div class="col-text">

**Perguntas?**

Slides disponíveis em:

matheuzfz.github.io/serasa-tech-summit-2026

</div>

<div class="col-img">

<img src="https://media.giphy.com/media/1d7F9xyq6j7C1ojbC5/giphy.gif" onerror="this.onerror=null; this.src='assets/cachorro-sorrindo.gif';" alt="Meme do cachorro sorrindo timidamente para a câmera">

</div>

</div>
