# DevSpace — Public Releases

Centralize your dev environment: projects, tools, credentials, and Git — in one place, on one keyboard shortcut.

> **Source code is currently private.** This repository hosts only the public binary releases of DevSpace. Use the **Issues** tab to report bugs and request features.

---

## ⚠️ Preview Build Notice

DevSpace is in **public preview**. Each release includes a hardcoded expiry date — once that date passes, most features stop working and you'll be prompted to download a newer build.

- The current expiry date is shown on every release page and inside the app (Help → About).
- Your data (projects, settings, credentials) stays on your machine. It is **not** deleted when a build expires.
- Import/Export remains available after expiry so you can carry your data forward.

This is honest beta software. Expect rough edges. Please report what you find.

---

## ⬇️ Download

Grab the latest release: **[Releases page →](https://github.com/biswajitpanday/Devspace-Releases/releases/latest)**

| Format | File | Best for |
|---|---|---|
| **Installer** | `DevSpace Setup <version>.exe` | Most users — adds Start menu / Desktop shortcut, supports clean uninstall. |
| **Portable** | `DevSpace-<version>-portable.zip` | Trying it out without installing. Extract anywhere, run `DevSpace.exe`. |

Both are unsigned during preview — see SmartScreen section below.

---

## ⚠️ Windows SmartScreen Warning — What to Expect

When you run the installer or the portable `.exe`, **Windows will show a blue "Windows protected your PC" dialog**:

> Windows protected your PC. Microsoft Defender SmartScreen prevented an unrecognized app from starting. Running this app might put your PC at risk.

This appears for any unsigned application on Windows. It does **not** mean the file is malicious — it means Microsoft hasn't yet seen this exact binary signed by a recognized publisher.

### How to run the app anyway

1. Click **More info** on the SmartScreen dialog.
2. A **Run anyway** button will appear at the bottom — click it.
3. The app launches normally.

### For the portable `.zip`

After extracting the zip, Windows may still flag the `.exe` inside (Mark-of-the-Web carries through). You can pre-clear it:

1. Right-click `DevSpace.exe` → **Properties**.
2. At the bottom of the **General** tab, tick **Unblock** if shown → **OK**.
3. Double-click to launch — no SmartScreen prompt.

### Why isn't it signed?

A trusted code-signing certificate from a reseller (DigiCert, Sectigo, etc.) costs **USD 200–400/year** for OV, more for EV. Microsoft's newer **Azure Trusted Signing** service is around **USD 10/month** but still represents a real recurring cost.

We're keeping running costs at zero during the preview phase so DevSpace stays free while it's still rough. Code signing is on the roadmap once the project is past public preview.

If you'd rather not run unsigned binaries, that's a perfectly reasonable position — please come back when we ship signed builds.

---

## 💻 System Requirements

- Windows 10 (64-bit) or Windows 11
- ~150 MB free disk space
- ~200 MB RAM at idle

macOS and Linux builds are not produced during the preview.

---

## 🔒 Privacy

DevSpace is **local-first** during the preview:

- Projects, tools, credentials, and settings live on your machine in a local SQLite database.
- Credentials are encrypted with Windows DPAPI (Microsoft.DataProtection).
- **No telemetry.** **No cloud sync.** **No account required.**
- The app makes no outbound HTTP calls except to:
  - Its own bundled local backend (`localhost:7003`).
  - Whatever URLs you explicitly open from the UI (e.g., a project's Git remote).

Cloud sync is planned for a later phase but is **not** part of this preview.

---

## ⚠️ Known Limitations (Preview)

- **Build expiry** — see notice above.
- **Unsigned binaries** — SmartScreen prompts on first launch.
- **No auto-update** — install new builds manually by downloading from this page.
- **Windows only** during preview.
- **Beta-quality bugs** are expected. Please file issues.

---

## 🐛 Reporting Issues

Source is private, but issues live here on the public repo.

- **Bug reports:** [Open a new issue →](https://github.com/biswajitpanday/Devspace-Releases/issues/new)
- **Feature requests:** [Open a new issue →](https://github.com/biswajitpanday/Devspace-Releases/issues/new) (please prefix the title with `[Feature]`)
- **Discussions / questions:** Use the **Issues** tab too — we'll convert to Discussions once volume warrants it.

When reporting a bug, please include:

- DevSpace version (Help → About → Copy System Info).
- Windows version.
- Reproduction steps.
- Screenshots if it's UI-related.

---

## 📜 License

The DevSpace **binaries** in this repository are distributed for evaluation under preview terms — free for personal and internal use, no warranty, no redistribution.

The **source code** is currently private. A formal license decision (likely MIT or proprietary-with-source-available) will accompany the first non-preview release.

---

## 🗺️ Roadmap

The headline post-preview milestones:

- Code signing (Azure Trusted Signing).
- Auto-update.
- Cloud sync (settings only — projects/credentials stay local).
- macOS build.

Track progress on this repo's release feed.

---

_Built by [Biswajit Panday](https://github.com/biswajitpanday) & [Abdullah Saleh Robin](https://github.com/robinabdullah). Thanks for trying it._
