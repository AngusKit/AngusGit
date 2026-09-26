**English** | [简体中文](README.zh.md)

<p align="center">
  <img src="assets/banner-en.png" alt="AngusGit — Code Together, Ship Confidently" width="100%" />
</p>

<p align="center">
  <a href="https://www.anguskit.com/en/pricing"><img alt="Community Edition" src="https://img.shields.io/badge/Community-Free-3d6fa0"></a>
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/badge/License-GPL--3.0-blue"></a>
  <a href="https://www.anguskit.com/en/docs/git"><img alt="Docs" src="https://img.shields.io/badge/docs-anguskit.com-3d6fa0"></a>
  <a href="https://www.anguskit.com"><img alt="Website" src="https://img.shields.io/badge/website-anguskit.com-c96128"></a>
</p>

# AngusGit

**Code Together, Ship Confidently. Let AI Power Every Pull Request.**

AI-Native Code Collaboration — the Code product in [AngusKit](https://github.com/AngusKit/AngusKit).

> **This repository hosts documentation only.** AngusGit source code is distributed through private deployment packages, not through this GitHub repository. Earlier revisions of this repository contained application source; as of this update, distribution has moved to AngusKit's packaging pipeline (see [Get the Community Edition](#get-the-community-edition-free) below). This repository now focuses on product information, quickstart guides, and links to the full documentation site.

## What is AngusGit

AngusGit is AI-native code collaboration built around repositories and pull requests, with reviews, Issues, and a Wiki out of the box. Team, Enterprise, and Cloud editions add CICD and code traceability, and can orchestrate [AngusSecurity](https://github.com/AngusKit/AngusSecurity) gates directly in the merge flow.

## Key capabilities

- **Repository management** — full Git hosting with Smart HTTP and SSH
- **Pull Request & Review** — merge request workflow with inline review and AI-assisted review
- **CICD Pipeline** *(Team/Enterprise)* — pipelines, runners, and artifacts wired into the same platform
- **Code Traceability** *(Team/Enterprise)* — trace a change from commit to pipeline to release
- **Issues & projects** — lightweight issue tracking tied to repositories and PRs
- **Security gate orchestration** — call AngusSecurity checks before merge or release

## Screenshot

<p align="center">
  <img src="assets/screenshot-en.png" alt="AngusGit console" width="100%" />
</p>

## Get the Community Edition (free)

About **310 MB**. This zip is **AngusGM + AngusGit**. At least **2 cores / 4 GB** RAM and **80 GB** disk (put repos on a separate SSD). Docker Engine + Compose v2.

This first-run path matches the official docs: Docker Compose, the install wizard, **access mode 2** (bundled Caddy), HTTP `:80` (no certificate).

1. Resolve names to this machine (or add to `/etc/hosts` for a local trial). Public DNS name in the wizard is the **suffix** (e.g. `example.com`), not `gm.example.com`.

```bash
127.0.0.1 gm.example.com git.example.com
```

Open host **80**. Open **2222** only when you need Git SSH. Do not publish 8801 or 8803. Stop Nginx/Caddy/IIS if they already bind 80. On macOS + Docker Desktop, do not run `./install.sh` with `sudo`.

2. Download, unzip, and run the wizard from the package root:

```bash
curl --fail --location --progress-bar -o AngusGit-Community-1.0.0.zip \
  https://repo.anguskit.com/raw/raw-public/AngusKit/git/AngusGit-Community-1.0.0.zip
unzip AngusGit-Community-1.0.0.zip
cd AngusGit-1.0.0
./install.sh
```

Answer: Install mode `1` (Compose) → Access **`2`** (bundled reverse proxy — do not press Enter) → Proxy `1` (Caddy) → TLS **`4`** (HTTP `:80`, no certificate) → Database `1` (MySQL 8 in Compose) → Public DNS name = `example.com` → set admin password (default user `admin`). Wait for `Install finished.`

3. Confirm health, then open the console:

```bash
./bin/angusctl.sh doctor
```

Look for `doctor: OK`. Open `http://gm.example.com/`, sign in, then open `http://git.example.com/`.

Need the full suite? Use `AngusKit-Community-1.0.0.zip` from [AngusKit](https://github.com/AngusKit/AngusKit).

First-run guide: **[git quickstart](https://www.anguskit.com/en/docs/git/get-started/quickstart)** · Full install (host ZIP, Helm preview, TLS, offline): **[install docs](https://www.anguskit.com/en/docs/git/latest/en/manual/02-install-deploy)**

## Community vs. Team / Enterprise vs. SaaS

| | Community | Team / Enterprise | SaaS |
|---|---|---|---|
| Price | Free | Paid, private deployment | Paid, hosted |
| Users | Up to 10 | Higher / unlimited seats | Per plan |
| Git repositories | Up to 100 | Higher / unlimited | Per plan |
| Git storage | Self-managed | Self-managed or pooled | Per plan |
| CI hours | Not included (no CI in Community) | Included | Per plan |
| Security integration, code traceability, CICD, MCP | Not included | Included | Per plan |

Community Edition source is licensed under GPL-3.0 and distributed with each Community installation package. Team and Enterprise editions are proprietary, governed by the **[XCan Business License, Version 1.0](https://www.anguskit.com/licenses/XCBL-1.0)** (XCBL-1.0), distributed only under a paid subscription.

Full pricing and feature comparison: **[anguskit.com/pricing](https://www.anguskit.com/en/pricing)**

## Related AngusKit products

| Product | Focus | Repository |
|---|---|---|
| AngusKit | The full suite (this product + 5 others + AngusGM) | [AngusKit/AngusKit](https://github.com/AngusKit/AngusKit) |
| AngusAI | AI agent development | [AngusKit/AngusAI](https://github.com/AngusKit/AngusAI) |
| AngusRepo | Universal artifact management | [AngusKit/AngusRepo](https://github.com/AngusKit/AngusRepo) |
| AngusTester | AI-native software testing | [AngusKit/AngusTester](https://github.com/AngusKit/AngusTester) |
| AngusSecurity | Application security & governance | [AngusKit/AngusSecurity](https://github.com/AngusKit/AngusSecurity) |
| AngusInsight | Private product analytics | [AngusKit/AngusInsight](https://github.com/AngusKit/AngusInsight) |

## Documentation & support

- Full docs: [anguskit.com/docs/git](https://www.anguskit.com/en/docs/git)
- Contact / sales: [anguskit.com/contact](https://www.anguskit.com/en/contact) · `sales@anguskit.com`
- This repository's Issues are for **documentation feedback and install troubleshooting**. This repository does not accept source code pull requests — see [CONTRIBUTING.md](CONTRIBUTING.md).

## License

- This repository's documentation content: see [LICENSE](LICENSE) (GPL-3.0, matching the Community Edition source it describes).
- AngusGit Community Edition product source: GPL-3.0, distributed with each Community installation package.
- AngusGit Team / Enterprise Edition: proprietary, [XCan Business License, Version 1.0](LICENSE-XCBL-1.0) (XCBL-1.0) — see https://www.anguskit.com/licenses/XCBL-1.0. Distributed under a paid subscription only.
