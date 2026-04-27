<!--
This file is the README for the PUBLIC release repo: github.com/biswajitpanday/Devspace-Releases
Copy its contents into that repo's README.md (overwriting whatever is there).

Screenshots needed in the public repo at /assets/:
- hero.png             Dashboard
- tool-discovery.png   Auto-discovered tools
- git-view.png         Git commit graph
- project-details.png  Project details view (tools, credentials, quick actions)
- wizard.png           Project setup wizard
- demo.gif             Optional 10-15s demo
-->

<div align="center">

# DevSpace

### Centralize every developer project. Tools, credentials, git, terminals — one dashboard.

[![Download Latest](https://img.shields.io/github/v/release/biswajitpanday/Devspace-Releases?label=Download&color=4fc3f7&style=for-the-badge&logo=windows)](https://github.com/biswajitpanday/Devspace-Releases/releases/latest)
[![Total Downloads](https://img.shields.io/github/downloads/biswajitpanday/Devspace-Releases/total?label=Downloads&color=29b6f6&style=for-the-badge)](https://github.com/biswajitpanday/Devspace-Releases/releases)
[![Platform](https://img.shields.io/badge/Windows-10%2F11-blue?style=for-the-badge&logo=windows)](https://github.com/biswajitpanday/Devspace-Releases/releases/latest)
[![Stars](https://img.shields.io/github/stars/biswajitpanday/Devspace-Releases?style=for-the-badge&color=yellow)](https://github.com/biswajitpanday/Devspace-Releases/stargazers)

[**🌐 Website**](https://biswajitpanday.github.io/devspace/) · [**⬇️ Download**](https://github.com/biswajitpanday/Devspace-Releases/releases/latest) · [**🔒 Privacy**](PRIVACY.md) · [**🐛 Report a bug**](https://github.com/biswajitpanday/Devspace-Releases/issues)

![DevSpace dashboard](assets/hero.png)

</div>

---

## 🤔 The problem

Every developer morning looks the same:

| 🔄 Switch project | Mentally re-establish context |
| :--- | :--- |
| 🛠️ Open the *right* IDE | For *this* stack |
| 📋 Find the credentials | Notion? Sticky note? `.env`? |
| 💻 Spawn 3 terminals | Build, git, tail |
| 🌐 Open the right tabs | Docs, dashboard, ticket tracker |
| 🗄️ Launch the DB client | Connect with the right credentials |

**~30 minutes lost. Every. Single. Day.**

## ✅ The solution

DevSpace gives you **one card per project** on a dashboard. Click it and your IDE, terminals, browser tabs, and DB client launch — exactly the way you set them up.

<table>
<tr>
<td width="50%"><img src="assets/tool-discovery.png" alt="Auto-discovered tools"/></td>
<td width="50%"><img src="assets/git-view.png" alt="Git workflow"/></td>
</tr>
<tr>
<td><b>Auto-discovers 100+ tools in &lt;3 seconds</b><br>Dynamic Windows enumeration finds every IDE, CLI, browser, and DB client on your machine.</td>
<td><b>Full git workflow built in</b><br>Commit graph, blame, conflict resolver, branch compare, stash. No more terminal context-switching.</td>
</tr>
<tr>
<td width="50%"><img src="assets/project-details.png" alt="Project details"/></td>
<td width="50%"><img src="assets/wizard.png" alt="Project wizard"/></td>
</tr>
<tr>
<td><b>Project details at a glance</b><br>Tools, credentials (DPAPI-encrypted), quick actions, and git status — all in one card.</td>
<td><b>Quick setup wizard</b><br>Add a project in 3 steps. Auto-detect git, link your tools, save credentials.</td>
</tr>
</table>

---

## ⬇️ Download

<div align="center">

### [Download DevSpace v2.2.0-preview for Windows](https://github.com/biswajitpanday/Devspace-Releases/releases/latest)

</div>

| Format | File | Size | Best for |
|---|---|---|---|
| **NSIS Installer** | `DevSpace.Setup.*.exe` | ~80 MB | Most users — start menu, auto-update |
| **Portable Zip** | `DevSpace-*-portable.zip` | ~75 MB | USB-portable, no install |

**System requirements:** Windows 10 (64-bit) or Windows 11 · 4 GB RAM · 500 MB free disk

---

## ✨ Features

### One dashboard, every project
- Pin frequently-used projects · search by tag, organization, or path
- Bulk-import git repos by scanning directory trees
- Per-project: tools, credentials, quick commands, git status

### Auto-discover your dev tools
- Dynamic Windows enumeration: Registry ARP + Start Menu + PATH
- Finds **100+ apps in under 3 seconds** on a typical dev machine
- Zero hardcoded patterns — new tools appear automatically
- Smart classification: IDEs, runtimes, source control, containers, databases, terminals, browsers, and more

### Encrypted credential vault
- Per-project credentials encrypted with **Microsoft DataProtection (DPAPI)**
- Tied to your Windows user account — never plain text on disk
- One-click copy with success feedback
- Multiple credentials per project

### Full git workflow, built in
- Visual commit graph with branch / author / date filters
- Blame view, conflict resolver, branch comparison
- Stash management, cherry-pick, rebase, merge
- 4-panel layout: graph + commit details + staging + diff
- Real-time progress via SignalR · operation cancellation

### Quick actions per project
- 26+ built-in git commands · custom command terminal
- Drag-and-drop reordering · custom priority per project
- One click launches: IDE + terminal + browser + DB client

### Tool templates
- Reusable tool collections shared across projects
- Save your most-used tool sets and apply them to any project

---

## 🏗️ How it works

```mermaid
graph TB
    User([👤 You])

    subgraph Desktop["💻 Your Windows machine"]
        Electron["🖼️ Electron + React UI"]
        API["⚙️ .NET 9 WebAPI<br/>(local, port 7003)"]
        DB[("🗄️ SQLite<br/>(encrypted credentials)")]
        Git[".git CLI"]
        WinAPIs["🪟 Registry / Start Menu / PATH"]
    end

    User -->|clicks| Electron
    Electron <-->|HTTP + SignalR| API
    API --> DB
    API --> Git
    API --> WinAPIs

    style Electron fill:#28B0F7,color:#fff,stroke:#0277bd
    style API fill:#4CAF50,color:#fff,stroke:#2e7d32
    style DB fill:#FF9800,color:#fff,stroke:#e65100
    style WinAPIs fill:#7E57C2,color:#fff,stroke:#4527a0
```

A two-process desktop app: an **Electron renderer** for the UI, a **local .NET 9 WebAPI** for everything else (running on `localhost:7003`).

**Local-first.** Your data never leaves your machine. No cloud account required, no telemetry in this release.

**Stack:** Electron · React 18 · TypeScript · Tailwind CSS · Redux Toolkit · .NET 9 · Entity Framework Core · SignalR · SQLite · Clean Architecture · CQRS · DDD

---

## 🔒 Privacy & security

DevSpace is built privacy-first.

- ✅ **Local-first**: project data, credentials, and git history never leave your machine
- ✅ **No telemetry**: this release collects nothing — no app launch pings, no analytics. Future versions will be opt-in only.
- ✅ **Encryption at rest**: credentials encrypted with Windows DPAPI, scoped to your user account
- ✅ **Shell command whitelist**: 21 vetted commands with argument sanitization — no arbitrary code execution
- ✅ **No analytics, no ads, no third-party SDKs** in the binary

📄 **[Read the full privacy policy](PRIVACY.md)**

---

## 🗺️ Roadmap

| Status | Phase | What |
|---|---|---|
| ✅ Shipped | v2.2.0-preview (Apr 2026) | Public preview · tool templates · typography overhaul · market readiness |
| 🚧 In progress | Cloud sync (Phase 1) | Supabase-backed, opt-in: settings, theme, recent projects |
| 📋 Planned | macOS support | Once Windows is rock-solid |

---

## 🐛 Found a bug?

Open an issue: [github.com/biswajitpanday/Devspace-Releases/issues](https://github.com/biswajitpanday/Devspace-Releases/issues)

Bug reports with the following are gold:
- Windows version (run `winver`)
- DevSpace version (Settings → About)
- Steps to reproduce
- Screenshot if it's visual

---

## 💖 Support the project

DevSpace is free during the public preview. If it saves you time:

- ⭐ **Star this repo** — costs nothing, helps a lot
- 💼 **Hire me**: [linkedin.com/in/biswajitpanday](https://www.linkedin.com/in/biswajitpanday/) — open to opportunities in Germany
- 📰 **Share with developers** who'd find it useful
- 🐛 **Report bugs** — every report makes the next release better

---

## 📄 License

DevSpace is **free during the public preview**.

This repository contains **release binaries only**. Source code is **proprietary** and not distributed.

---

## 👤 Authors

<div align="center">

**Biswajit Panday** — Senior .NET Architect & AI Solutions Engineer (Lead)

[![Website](https://img.shields.io/badge/Website-biswajitpanday.github.io-blue?style=flat-square&logo=googlechrome&logoColor=white)](https://biswajitpanday.github.io/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-biswajitpanday-blue?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/biswajitpanday/)
[![GitHub](https://img.shields.io/badge/GitHub-biswajitpanday-black?style=flat-square&logo=github&logoColor=white)](https://github.com/biswajitpanday)
[![Email](https://img.shields.io/badge/Email-biswajitmailid%40gmail.com-red?style=flat-square&logo=gmail&logoColor=white)](mailto:biswajitmailid@gmail.com)

**Abdullah Saleh Robin** — Co-author

[![LinkedIn](https://img.shields.io/badge/LinkedIn-robinabdullah-blue?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/robinabdullah/)
[![GitHub](https://img.shields.io/badge/GitHub-robinabdullah-black?style=flat-square&logo=github&logoColor=white)](https://github.com/robinabdullah)
[![Email](https://img.shields.io/badge/Email-abdullahsalehrobin%40gmail.com-red?style=flat-square&logo=gmail&logoColor=white)](mailto:abdullahsalehrobin@gmail.com)

*Built with ❤️ on nights and weekends — concept to public preview, 18 months.*

</div>
