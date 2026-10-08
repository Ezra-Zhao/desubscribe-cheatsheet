# Desubscribe 💸 告别订阅：SaaS 免费/自托管替代品速查

[English](CHEATSHEET.md) · [Español](README.es.md) · [Português](README.pt.md)

> 算一笔账：Notion + Slack + Figma + 网盘 + 密码管理 + 笔记……
> 一个普通人一年在 SaaS 订阅上花 **$1,260**，五年就是 **$6,300**。
> 而下面这些开源替代品，装在一台 $5/月 的小 VPS 上，**全免费**。

这份速查表只干一件事：**每行一个"冤枉钱"，配一个免费替代品、一条安装命令、一个省钱数字。**
复制命令，跑起来，取消订阅。就这么简单。

---

## 📝 1. 笔记：Notion Plus → AppFlowy / Anytype

- **你在交**：Notion Plus 约 **$10/人/月**（年付），$120/年（[官网定价](https://www.notion.so/pricing)）
- **换成**：[AppFlowy](https://appflowy.com) —— 开源 Notion 平替，文档、数据库、看板全有，数据存在自己手里。自托管走官方 `AppFlowy-SelfHost-Commercial` 仓库（含免费层）。
- **一条命令**：
  ```bash
  git clone https://github.com/AppFlowy-IO/AppFlowy-SelfHost-Commercial && cd AppFlowy-SelfHost-Commercial && cp deploy.env .env && docker compose up -d
  ```
- **也可选**：[Anytype](https://anytype.io) —— 本地优先、P2P 同步，连服务器都不用装。
- 💰 **每年省：约 $120/人**

## 💬 2. 团队聊天：Slack Pro → Mattermost

- **你在交**：Slack Pro 约 **$7.25/人/月**（年付），$87/年/人（[官网定价](https://slack.com/pricing)）
- **换成**：[Mattermost](https://mattermost.com) —— 开源团队聊天，频道、私信、机器人、Webhook 全有，界面和 Slack 几乎无缝切换。
- **一条命令**（官方 `mattermost/docker` 仓库）：
  ```bash
  git clone https://github.com/mattermost/docker && cd docker && docker compose -f docker-compose.yml -f docker-compose.without-nginx.yml up -d
  ```
  打开 http://localhost:8065 建管理员账号即用。
- 💰 **每年省：约 $87/人**（10 人小团队一年省 $870）

## 🎨 3. 设计协作：Figma Professional → Penpot

- **你在交**：Figma Professional 约 **$12/编辑/月**（年付），$144/年/编辑（[官网定价](https://www.figma.com/pricing)）
- **换成**：[Penpot](https://penpot.app) —— 开源设计协作平台，原生 SVG/CSS 标准，设计稿直接产出可用代码，[GitHub 44k+ star](https://github.com/penpot/penpot)。
- **一条命令**（官方文档方案）：
  ```bash
  curl -o docker-compose.yaml https://raw.githubusercontent.com/penpot/penpot/main/docker/images/docker-compose.yaml && docker compose -p penpot -f docker-compose.yaml up -d
  ```
  打开 http://localhost:9001。
- 💰 **每年省：约 $144/编辑**

## 📸 4. 照片备份：Google One 2TB → Immich

- **你在交**：Google One 2TB 约 **$99.99/年**（[官网](https://one.google.com/about/plans)）
- **换成**：[Immich](https://immich.app) —— 自托管照片/视频库，手机自动备份、AI 搜图、人脸识别，体验对标 Google Photos，照片只存自己硬盘。
- **一条命令**（用官方 release 的 compose 文件）：
  ```bash
  mkdir immich && cd immich && wget -O docker-compose.yml https://github.com/immich-app/immich/releases/latest/download/docker-compose.yml && wget -O .env https://github.com/immich-app/immich/releases/latest/download/example.env && docker compose up -d
  ```
  打开 http://localhost:2283，手机装 App 连上即自动备份。
- 💰 **每年省：约 $100**

## 🔑 5. 密码管理：1Password → Vaultwarden

- **你在交**：1Password 个人版 **$3.99/月**（年付，2026 年 3 月刚涨过价），$47.88/年（[官网定价](https://1password.com/pricing)）
- **换成**：[Vaultwarden](https://github.com/dani-garcia/vaultwarden) —— 非官方但完全兼容的 Bitwarden 服务器，Rust 写的，极轻量；官方 Bitwarden 客户端（手机/浏览器/桌面）全都能连。
- **一条命令**（官方 README 方案）：
  ```bash
  docker run -d --name vaultwarden -v /vw-data/:/data/ --restart unless-stopped -p 80:80 vaultwarden/server:latest
  ```
- 💰 **每年省：约 $48**

## ☁️ 6. 云盘同步：Dropbox Plus → Nextcloud

- **你在交**：Dropbox Plus 约 **$9.99/月**（年付，2TB），$119.88/年（[官网](https://www.dropbox.com/plans)）
- **换成**：[Nextcloud](https://nextcloud.com) —— 自托管私有云，文件同步、日历、通讯录、在线文档全家桶，不止是网盘。
- **一条命令**（官方 Docker 镜像）：
  ```bash
  docker run -d --name nextcloud -p 8080:80 -v nextcloud-data:/var/www/html --restart unless-stopped nextcloud
  ```
  打开 http://localhost:8080 按向导建管理员账号。
- 💰 **每年省：约 $120**

## 🗃️ 7. 数据表格：Airtable Team → NocoDB

- **你在交**：Airtable Team 约 **$20/席位/月**（年付），$240/年/席位（[官网定价](https://www.airtable.com/pricing)）
- **换成**：[NocoDB](https://nocodb.com) —— 开源 Airtable，任何 SQL 数据库秒变智能表格，自带 REST API，[GitHub 60k+ star](https://github.com/nocodb/nocodb)。
- **一条命令**（官方 README 方案）：
  ```bash
  docker run -d --name noco -v "$(pwd)"/nocodb:/usr/app/data/ -p 8080:8080 --restart unless-stopped nocodb/nocodb:latest
  ```
- 💰 **每年省：约 $240/席位** —— 全表最贵的一项

## 📋 8. 看板：Trello Premium → Wekan

- **你在交**：Trello Premium 约 **$10/人/月**（年付），$120/年/人（[官网定价](https://trello.com/pricing)）
- **换成**：[Wekan](https://wekan.github.io) —— 开源看板，卡片、 checklist、 swimlane、API 全有，Trello 用户零学习成本。
- **两条命令**（需先起 MongoDB，官方文档方案）：
  ```bash
  docker network create wekan-net
  docker run -d --name wekan-db --network wekan-net --restart=always mongo:5
  docker run -d --name wekan --network wekan-net --restart=always \
    -e MONGO_URL=mongodb://wekan-db:27017/wekan \
    -e ROOT_URL=http://localhost:8080 -p 8080:8080 wekanteam/wekan
  ```
- 💰 **每年省：约 $120/人**

## 📹 9. 视频会议：Zoom Pro → Jitsi Meet

- **你在交**：Zoom Workplace Pro 约 **$149.90/年/人**（[官网定价](https://zoom.us/pricing)）
- **换成**：[Jitsi Meet](https://jitsi.org) —— 开源视频会议，浏览器打开即用、无需注册，端到端加密；自己搭连人数都不限。
- **一条命令**（官方 `docker-jitsi-meet` 仓库）：
  ```bash
  git clone https://github.com/jitsi/docker-jitsi-meet && cd docker-jitsi-meet && cp env.example .env && docker compose up -d
  ```
- 💰 **每年省：约 $150/人**

## 🗒️ 10. 笔记归档：Evernote Personal → Joplin

- **你在交**：Evernote Personal **$129.99/年**（免费版只剩 50 条笔记，基本不可用）（[官网](https://evernote.com/compare-plans)）
- **换成**：[Joplin](https://joplinapp.org) —— 开源笔记，Markdown、网页剪藏、端到端加密，手机桌面全平台客户端。
- **一条命令**（官方 `joplin/server` 镜像，默认 SQLite 开箱即用）：
  ```bash
  docker run -d --name joplin -p 22300:22300 -e APP_PORT=22300 -e APP_BASE_URL=http://localhost:22300 --restart unless-stopped joplin/server:latest
  ```
  正式使用建议换 Postgres（见 [Joplin 官方文档](https://github.com/laurent22/joplin))。
- 💰 **每年省：约 $130**

---

## 🧾 总账

| 项目 | 年花费 |
|---|---|
| 10 个 SaaS 订阅 | 约 $1,260/人/年 |
| 1 台小 VPS（全装下） | 约 $60/年 |
| **净省** | **约 $1,200/人/年** |

团队版更夸张：10 人团队光 Slack + Notion + Airtable 一年就省 **$4,470**。

## ⚠️ 诚实说明

- 价格为 2026 年 10 月核实的各官网定价（年付口径），SaaS 经常调价，动手前请以官网为准。
- 自托管需要一台服务器：旧电脑、树莓派、NAS 或云 VPS 都行；数据归你，但备份和安全自己负责。
- 有些替代品（如 AppFlowy 自托管新版）含免费层/商业版，免费额度内的个人/小团队使用完全够用。

## 🤝 贡献

发现价格变了、命令失效了、有更好的替代品？欢迎提 Issue / PR。

MIT License © 2026 Guangyi Zhao
