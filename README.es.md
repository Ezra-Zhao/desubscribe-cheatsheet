# Desubscribe 💸 Date de baja: alternativas gratuitas y autoalojadas al SaaS

[中文](README.md) · [English](CHEATSHEET.md) · [Português](README.pt.md)

> Haz cuentas: Notion + Slack + Figma + almacenamiento + gestor de contraseñas + notas…
> Una persona normal gasta **$1.260 al año** en suscripciones SaaS. En cinco años, **$6.300**.
> Las alternativas de código abierto de abajo caben en un VPS de $5/mes. **Gratis.**

Esta hoja de trucos hace una sola cosa: **cada línea, una suscripción que no necesitas,
con su alternativa gratuita, un comando de instalación y la cifra que ahorras.**
Copia el comando, ejecútalo, cancela la suscripción. Así de simple.

---

## 📝 1. Notas: Notion Plus → AppFlowy / Anytype

- **Pagabas**: Notion Plus unos **$10/usuario/mes** (facturación anual), $120/año ([precios oficiales](https://www.notion.so/pricing))
- **Cámbiate a**: [AppFlowy](https://appflowy.com) — alternativa abierta a Notion: documentos, bases de datos y tableros; tus datos, en tus manos. Autoalojado con el repositorio oficial `AppFlowy-SelfHost-Commercial` (incluye plan gratuito).
- **Un comando**:
  ```bash
  git clone https://github.com/AppFlowy-IO/AppFlowy-SelfHost-Commercial && cd AppFlowy-SelfHost-Commercial && cp deploy.env .env && docker compose up -d
  ```
- **Otra opción**: [Anytype](https://anytype.io) — local primero, sincronización P2P, ni siquiera necesitas un servidor.
- 💰 **Ahorro anual: unos $120/persona**

## 💬 2. Chat de equipo: Slack Pro → Mattermost

- **Pagabas**: Slack Pro unos **$7,25/usuario/mes** (anual), $87/año/persona ([precios oficiales](https://slack.com/pricing))
- **Cámbiate a**: [Mattermost](https://mattermost.com) — chat de equipo open source: canales, mensajes directos, bots y webhooks; el cambio desde Slack es casi invisible.
- **Un comando** (repositorio oficial `mattermost/docker`):
  ```bash
  git clone https://github.com/mattermost/docker && cd docker && docker compose -f docker-compose.yml -f docker-compose.without-nginx.yml up -d
  ```
  Abre http://localhost:8065 y crea tu cuenta de administrador.
- 💰 **Ahorro anual: unos $87/persona** (un equipo de 10 ahorra $870/año)

## 🎨 3. Diseño colaborativo: Figma Professional → Penpot

- **Pagabas**: Figma Professional unos **$12/editor/mes** (anual), $144/año/editor ([precios oficiales](https://www.figma.com/pricing))
- **Cámbiate a**: [Penpot](https://penpot.app) — plataforma abierta de diseño colaborativo con estándares SVG/CSS; los diseños salen como código utilizable. [Más de 44k estrellas en GitHub](https://github.com/penpot/penpot).
- **Un comando** (método de la documentación oficial):
  ```bash
  curl -o docker-compose.yaml https://raw.githubusercontent.com/penpot/penpot/main/docker/images/docker-compose.yaml && docker compose -p penpot -f docker-compose.yaml up -d
  ```
  Abre http://localhost:9001.
- 💰 **Ahorro anual: unos $144/editor**

## 📸 4. Copia de fotos: Google One 2TB → Immich

- **Pagabas**: Google One 2TB unos **$99,99/año** ([web oficial](https://one.google.com/about/plans))
- **Cámbiate a**: [Immich](https://immich.app) — biblioteca de fotos y vídeos autoalojada: copia automática desde el móvil, búsqueda con IA y reconocimiento facial; tus fotos, en tu disco.
- **Un comando** (con los archivos compose de la release oficial):
  ```bash
  mkdir immich && cd immich && wget -O docker-compose.yml https://github.com/immich-app/immich/releases/latest/download/docker-compose.yml && wget -O .env https://github.com/immich-app/immich/releases/latest/download/example.env && docker compose up -d
  ```
  Abre http://localhost:2283, instala la app en el móvil y activa la copia automática.
- 💰 **Ahorro anual: unos $100**

## 🔑 5. Contraseñas: 1Password → Vaultwarden

- **Pagabas**: 1Password Individual **$3,99/mes** (anual; subió de precio en marzo de 2026), $47,88/año ([precios oficiales](https://1password.com/pricing))
- **Cámbiate a**: [Vaultwarden](https://github.com/dani-garcia/vaultwarden) — servidor compatible con Bitwarden escrito en Rust, ultraligero; funciona con todas las apps oficiales de Bitwarden (móvil, navegador, escritorio).
- **Un comando** (del README oficial):
  ```bash
  docker run -d --name vaultwarden -v /vw-data/:/data/ --restart unless-stopped -p 80:80 vaultwarden/server:latest
  ```
- 💰 **Ahorro anual: unos $48**

## ☁️ 6. Nube de archivos: Dropbox Plus → Nextcloud

- **Pagabas**: Dropbox Plus unos **$9,99/mes** (anual, 2TB), $119,88/año ([web oficial](https://www.dropbox.com/plans))
- **Cámbiate a**: [Nextcloud](https://nextcloud.com) — nube privada autoalojada: sincronización de archivos, calendario, contactos y ofimática. Mucho más que un disco en la nube.
- **Un comando** (imagen Docker oficial):
  ```bash
  docker run -d --name nextcloud -p 8080:80 -v nextcloud-data:/var/www/html --restart unless-stopped nextcloud
  ```
  Abre http://localhost:8080 y sigue el asistente para crear tu administrador.
- 💰 **Ahorro anual: unos $120**

## 🗃️ 7. Tablas de datos: Airtable Team → NocoDB

- **Pagabas**: Airtable Team unos **$20/puesto/mes** (anual), $240/año/puesto ([precios oficiales](https://www.airtable.com/pricing))
- **Cámbiate a**: [NocoDB](https://nocodb.com) — el Airtable open source: convierte cualquier base SQL en una hoja de cálculo inteligente con API REST. [Más de 60k estrellas en GitHub](https://github.com/nocodb/nocodb).
- **Un comando** (del README oficial):
  ```bash
  docker run -d --name noco -v "$(pwd)"/nocodb:/usr/app/data/ -p 8080:8080 --restart unless-stopped nocodb/nocodb:latest
  ```
- 💰 **Ahorro anual: unos $240/puesto** — el más caro de la lista

## 📋 8. Tableros kanban: Trello Premium → Wekan

- **Pagabas**: Trello Premium unos **$10/usuario/mes** (anual), $120/año/persona ([precios oficiales](https://trello.com/pricing))
- **Cámbiate a**: [Wekan](https://wekan.github.io) — kanban open source: tarjetas, checklists, swimlanes y API; quien venga de Trello no necesita aprender nada.
- **Dos comandos** (primero MongoDB, método de la documentación oficial):
  ```bash
  docker network create wekan-net
  docker run -d --name wekan-db --network wekan-net --restart=always mongo:5
  docker run -d --name wekan --network wekan-net --restart=always \
    -e MONGO_URL=mongodb://wekan-db:27017/wekan \
    -e ROOT_URL=http://localhost:8080 -p 8080:8080 wekanteam/wekan
  ```
- 💰 **Ahorro anual: unos $120/persona**

## 📹 9. Videollamadas: Zoom Pro → Jitsi Meet

- **Pagabas**: Zoom Workplace Pro unos **$149,90/año/persona** ([precios oficiales](https://zoom.us/pricing))
- **Cámbiate a**: [Jitsi Meet](https://jitsi.org) — videollamadas open source: se abre en el navegador, sin registro, con cifrado de extremo a extremo; autoalojado, sin límite de participantes.
- **Un comando** (repositorio oficial `docker-jitsi-meet`):
  ```bash
  git clone https://github.com/jitsi/docker-jitsi-meet && cd docker-jitsi-meet && cp env.example .env && docker compose up -d
  ```
- 💰 **Ahorro anual: unos $150/persona**

## 🗒️ 10. Archivo de notas: Evernote Personal → Joplin

- **Pagabas**: Evernote Personal **$129,99/año** (el plan gratis se quedó en 50 notas: inutilizable) ([web oficial](https://evernote.com/compare-plans))
- **Cámbiate a**: [Joplin](https://joplinapp.org) — notas open source: Markdown, recortes web y cifrado de extremo a extremo, con apps para móvil y escritorio.
- **Un comando** (imagen oficial `joplin/server`; SQLite por defecto, listo para usar):
  ```bash
  docker run -d --name joplin -p 22300:22300 -e APP_PORT=22300 -e APP_BASE_URL=http://localhost:22300 --restart unless-stopped joplin/server:latest
  ```
  Para uso serio se recomienda Postgres (ver [documentación oficial de Joplin](https://github.com/laurent22/joplin)).
- 💰 **Ahorro anual: unos $130**

---

## 🧾 La cuenta total

| Concepto | Coste anual |
|---|---|
| 10 suscripciones SaaS | unos $1.260/persona/año |
| 1 VPS pequeño (cabe todo) | unos $60/año |
| **Ahorro neto** | **unos $1.200/persona/año** |

En equipo sale aún mejor: 10 personas solo en Slack + Notion + Airtable ahorran **$4.470/año**.

## ⚠️ Notas honestas

- Precios verificados en las webs oficiales en octubre de 2026 (facturación anual); el SaaS cambia de precio a menudo: confirma en la web oficial antes de actuar.
- El autoalojamiento necesita un servidor: un PC viejo, una Raspberry Pi, un NAS o un VPS en la nube. Tus datos son tuyos, pero las copias de seguridad y la seguridad corren de tu cuenta.
- Algunas alternativas (p. ej. el nuevo autoalojado de AppFlowy) incluyen plan gratuito/capas comerciales; el tramo gratuito basta para uso personal o equipos pequeños.

## 🤝 Contribuir

¿Cambió un precio? ¿Falló un comando? ¿Conoces una alternativa mejor? Abre un Issue o un PR.

MIT License © 2026 Guangyi Zhao
