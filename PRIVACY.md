# DevSpace Privacy Policy

*Last updated: 2026-04-27 · Applies to: v2.2.0-preview.1*

## TL;DR

DevSpace is **local-first**. Your project data, credentials, and git history never leave your machine. **v2.2.0-preview.1 collects no telemetry, no analytics, no usage data. Period.**

---

## What this version does NOT do

- ❌ No telemetry — DevSpace does not phone home on launch or otherwise
- ❌ No usage analytics
- ❌ No automatic crash reporting
- ❌ No third-party SDKs in the binary (no advertising, no tracking)
- ❌ No cloud account required
- ❌ No external network calls except to GitHub (for the optional "Check for Updates" feature, which only happens when you click the button)

## What stays local

Everything. DevSpace stores its data in `%LOCALAPPDATA%\DevSpace\devspace.db`. Credentials are encrypted at rest using **Microsoft DataProtection (DPAPI)**, scoped to your Windows user account — meaning a different Windows user on the same machine cannot decrypt them.

## What about future versions?

Cloud sync (Phase 1) and any telemetry are **planned but not shipped**. If a future release adds either, the change will be:

- **Opt-in by default** — you will see a clear consent prompt before any data leaves your machine
- **Announced in the release notes**
- **Documented here** before the version that introduces the change ships
- **Never silent** — no data will be collected without an explicit, fresh consent

When opt-in telemetry eventually ships (no committed date), we commit to:

**Will collect (only with consent):**
- A randomly generated install ID (UUID v4 — not linked to you, your email, or any account)
- The app version (e.g. `2.2.0-preview.1`)
- Your operating system version (e.g. `Windows 11 26H2`)
- Event types like `app_started` or `feature_used` with the feature name (e.g. `git_commit`)

**Will never collect:**
- Your name, email, or any account information
- Your IP address (stripped server-side before storage)
- Project paths, file names, or file contents
- Repository data, commit messages, branch names, or git remotes
- Credentials, environment variables, or any secret values
- Keystrokes, clipboard contents, or any input outside DevSpace
- Telemetry from any application other than DevSpace

When cloud sync ships, only **settings, theme, and recent project paths** will sync. Credentials, project content, and git data will **never** be synced.

## Your rights under GDPR

Because v2.2.0-preview.1 stores nothing on any server we run, there is currently nothing to access, export, or delete on a remote system. Local data is yours; you can delete it any time by uninstalling DevSpace and removing `%LOCALAPPDATA%\DevSpace\`.

When future versions add server-stored data:
- **Right to access:** email `biswajitmailid@gmail.com` with your install ID; response within 30 days
- **Right to deletion:** same email; deletion within 30 days
- **Right to opt out:** disable telemetry/cloud sync at any time in Settings; future pings stop immediately

## Contact

Biswajit Panday — `biswajitmailid@gmail.com`

## Changes to this policy

Material changes will be announced in the DevSpace release notes. Any new data collection requires a fresh consent prompt — silent additions will never be made.
