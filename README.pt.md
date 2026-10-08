# Desubscribe 💸 Cancele as assinaturas: alternativas gratuitas e auto-hospedadas ao SaaS

[中文](README.md) · [English](CHEATSHEET.md) · [Español](README.es.md)

> Faça as contas: Notion + Slack + Figma + armazenamento + gerenciador de senhas + notas…
> Uma pessoa comum gasta **$1.260 por ano** em assinaturas SaaS. Em cinco anos, **$6.300**.
> As alternativas de código aberto abaixo cabem num VPS de $5/mês. **De graça.**

Esta folha de dicas faz uma única coisa: **cada linha, uma assinatura de que você não precisa,
com sua alternativa gratuita, um comando de instalação e o valor economizado.**
Copie o comando, execute, cancele a assinatura. Simples assim.

---

## 📝 1. Notas: Notion Plus → AppFlowy / Anytype

- **Você pagava**: Notion Plus cerca de **$10/usuário/mês** (faturamento anual), $120/ano ([preços oficiais](https://www.notion.so/pricing))
- **Troque por**: [AppFlowy](https://appflowy.com) — alternativa aberta ao Notion: documentos, bancos de dados e quadros; seus dados, nas suas mãos. Auto-hospedagem pelo repositório oficial `AppFlowy-SelfHost-Commercial` (inclui plano gratuito).
- **Um comando**:
  ```bash
  git clone https://github.com/AppFlowy-IO/AppFlowy-SelfHost-Commercial && cd AppFlowy-SelfHost-Commercial && cp deploy.env .env && docker compose up -d
  ```
- **Outra opção**: [Anytype](https://anytype.io) — local primeiro, sincronização P2P, nem precisa de servidor.
- 💰 **Economia anual: cerca de $120/pessoa**

## 💬 2. Chat da equipe: Slack Pro → Mattermost

- **Você pagava**: Slack Pro cerca de **$7,25/usuário/mês** (anual), $87/ano/pessoa ([preços oficiais](https://slack.com/pricing))
- **Troque por**: [Mattermost](https://mattermost.com) — chat de equipe open source: canais, mensagens diretas, bots e webhooks; a migração do Slack é quase invisível.
- **Um comando** (repositório oficial `mattermost/docker`):
  ```bash
  git clone https://github.com/mattermost/docker && cd docker && docker compose -f docker-compose.yml -f docker-compose.without-nginx.yml up -d
  ```
  Abra http://localhost:8065 e crie sua conta de administrador.
- 💰 **Economia anual: cerca de $87/pessoa** (uma equipe de 10 economiza $870/ano)

## 🎨 3. Design colaborativo: Figma Professional → Penpot

- **Você pagava**: Figma Professional cerca de **$12/editor/mês** (anual), $144/ano/editor ([preços oficiais](https://www.figma.com/pricing))
- **Troque por**: [Penpot](https://penpot.app) — plataforma aberta de design colaborativo com padrões SVG/CSS; os designs saem como código utilizável. [Mais de 44k estrelas no GitHub](https://github.com/penpot/penpot).
- **Um comando** (método da documentação oficial):
  ```bash
  curl -o docker-compose.yaml https://raw.githubusercontent.com/penpot/penpot/main/docker/images/docker-compose.yaml && docker compose -p penpot -f docker-compose.yaml up -d
  ```
  Abra http://localhost:9001.
- 💰 **Economia anual: cerca de $144/editor**

## 📸 4. Backup de fotos: Google One 2TB → Immich

- **Você pagava**: Google One 2TB cerca de **$99,99/ano** ([site oficial](https://one.google.com/about/plans))
- **Troque por**: [Immich](https://immich.app) — biblioteca de fotos e vídeos auto-hospedada: backup automático do celular, busca com IA e reconhecimento facial; suas fotos, no seu disco.
- **Um comando** (com os arquivos compose da release oficial):
  ```bash
  mkdir immich && cd immich && wget -O docker-compose.yml https://github.com/immich-app/immich/releases/latest/download/docker-compose.yml && wget -O .env https://github.com/immich-app/immich/releases/latest/download/example.env && docker compose up -d
  ```
  Abra http://localhost:2283, instale o app no celular e ative o backup automático.
- 💰 **Economia anual: cerca de $100**

## 🔑 5. Senhas: 1Password → Vaultwarden

- **Você pagava**: 1Password Individual **$3,99/mês** (anual; aumentou em março de 2026), $47,88/ano ([preços oficiais](https://1password.com/pricing))
- **Troque por**: [Vaultwarden](https://github.com/dani-garcia/vaultwarden) — servidor compatível com Bitwarden escrito em Rust, ultraleve; funciona com todos os apps oficiais do Bitwarden (celular, navegador, desktop).
- **Um comando** (do README oficial):
  ```bash
  docker run -d --name vaultwarden -v /vw-data/:/data/ --restart unless-stopped -p 80:80 vaultwarden/server:latest
  ```
- 💰 **Economia anual: cerca de $48**

## ☁️ 6. Nuvem de arquivos: Dropbox Plus → Nextcloud

- **Você pagava**: Dropbox Plus cerca de **$9,99/mês** (anual, 2TB), $119,88/ano ([site oficial](https://www.dropbox.com/plans))
- **Troque por**: [Nextcloud](https://nextcloud.com) — nuvem privada auto-hospedada: sincronização de arquivos, calendário, contatos e suíte de escritório. Muito mais que um disco na nuvem.
- **Um comando** (imagem Docker oficial):
  ```bash
  docker run -d --name nextcloud -p 8080:80 -v nextcloud-data:/var/www/html --restart unless-stopped nextcloud
  ```
  Abra http://localhost:8080 e siga o assistente para criar seu administrador.
- 💰 **Economia anual: cerca de $120**

## 🗃️ 7. Tabelas de dados: Airtable Team → NocoDB

- **Você pagava**: Airtable Team cerca de **$20/assento/mês** (anual), $240/ano/assento ([preços oficiais](https://www.airtable.com/pricing))
- **Troque por**: [NocoDB](https://nocodb.com) — o Airtable open source: transforma qualquer banco SQL numa planilha inteligente com API REST. [Mais de 60k estrelas no GitHub](https://github.com/nocodb/nocodb).
- **Um comando** (do README oficial):
  ```bash
  docker run -d --name noco -v "$(pwd)"/nocodb:/usr/app/data/ -p 8080:8080 --restart unless-stopped nocodb/nocodb:latest
  ```
- 💰 **Economia anual: cerca de $240/assento** — o mais caro da lista

## 📋 8. Quadros kanban: Trello Premium → Wekan

- **Você pagava**: Trello Premium cerca de **$10/usuário/mês** (anual), $120/ano/pessoa ([preços oficiais](https://trello.com/pricing))
- **Troque por**: [Wekan](https://wekan.github.io) — kanban open source: cartões, checklists, swimlanes e API; quem vem do Trello não precisa aprender nada.
- **Dois comandos** (primeiro o MongoDB, método da documentação oficial):
  ```bash
  docker network create wekan-net
  docker run -d --name wekan-db --network wekan-net --restart=always mongo:5
  docker run -d --name wekan --network wekan-net --restart=always \
    -e MONGO_URL=mongodb://wekan-db:27017/wekan \
    -e ROOT_URL=http://localhost:8080 -p 8080:8080 wekanteam/wekan
  ```
- 💰 **Economia anual: cerca de $120/pessoa**

## 📹 9. Videochamadas: Zoom Pro → Jitsi Meet

- **Você pagava**: Zoom Workplace Pro cerca de **$149,90/ano/pessoa** ([preços oficiais](https://zoom.us/pricing))
- **Troque por**: [Jitsi Meet](https://jitsi.org) — videochamadas open source: abre no navegador, sem cadastro, com criptografia de ponta a ponta; auto-hospedado, sem limite de participantes.
- **Um comando** (repositório oficial `docker-jitsi-meet`):
  ```bash
  git clone https://github.com/jitsi/docker-jitsi-meet && cd docker-jitsi-meet && cp env.example .env && docker compose up -d
  ```
- 💰 **Economia anual: cerca de $150/pessoa**

## 🗒️ 10. Arquivo de notas: Evernote Personal → Joplin

- **Você pagava**: Evernote Personal **$129,99/ano** (o plano grátis ficou em 50 notas: inutilizável) ([site oficial](https://evernote.com/compare-plans))
- **Troque por**: [Joplin](https://joplinapp.org) — notas open source: Markdown, recortes da web e criptografia de ponta a ponta, com apps para celular e desktop.
- **Um comando** (imagem oficial `joplin/server`; SQLite por padrão, pronto para usar):
  ```bash
  docker run -d --name joplin -p 22300:22300 -e APP_PORT=22300 -e APP_BASE_URL=http://localhost:22300 --restart unless-stopped joplin/server:latest
  ```
  Para uso sério, recomenda-se Postgres (ver [documentação oficial do Joplin](https://github.com/laurent22/joplin)).
- 💰 **Economia anual: cerca de $130**

---

## 🧾 A conta total

| Item | Custo anual |
|---|---|
| 10 assinaturas SaaS | cerca de $1.260/pessoa/ano |
| 1 VPS pequeno (cabe tudo) | cerca de $60/ano |
| **Economia líquida** | **cerca de $1.200/pessoa/ano** |

Em equipe fica ainda melhor: 10 pessoas só em Slack + Notion + Airtable economizam **$4.470/ano**.

## ⚠️ Notas honestas

- Preços verificados nos sites oficiais em outubro de 2026 (faturamento anual); o SaaS muda de preço com frequência: confirme no site oficial antes de agir.
- A auto-hospedagem precisa de um servidor: um PC velho, uma Raspberry Pi, um NAS ou um VPS na nuvem. Seus dados são seus, mas backups e segurança são por sua conta.
- Algumas alternativas (p. ex. a nova auto-hospedagem do AppFlowy) incluem plano gratuito/camadas comerciais; a faixa gratuita basta para uso pessoal ou equipes pequenas.

## 🤝 Contribuir

Mudou um preço? Um comando quebrou? Conhece uma alternativa melhor? Abra uma Issue ou um PR.

MIT License © 2026 Guangyi Zhao
