# GoTUIApp — Go TUI Command App Template

> A production-ready Go TUI application template with CI/CD, cross-platform builds, semantic versioning, and an example `sysinfo` command

[![CI](https://github.com/marko-stanojevic/hostr/actions/workflows/ci.yml/badge.svg)](https://github.com/marko-stanojevic/hostr/actions/workflows/ci.yml)
[![Go Version](https://img.shields.io/github/go-mod/go-version/marko-stanojevic/hostr)](go.mod)
[![License](https://img.shields.io/github/license/marko-stanojevic/hostr)](LICENSE)

---

## 💡 Why This Template?

Most Go TUI projects start with a single `main.go`. CI, linting, and cross-compilation get bolted on later — inconsistently, if ever. This template flips that model.

**GoTUIApp is opinionated by design.**  
It gives you a production-grade foundation so you can focus on building your TUI — not wiring pipelines.

### What makes it different?

- **CI/CD from day one** — lint, test (3 OSes), and cross-compile automatically on every PR
- **Bubble Tea architecture** — clean separation between data, model, and view
- **Cross-platform releases** — GoReleaser builds binaries for Linux, macOS, and Windows (amd64 + arm64)
- **Example included** — the `sysinfo` command shows real-world usage: live system metrics with auto-refresh
- **AI-agent ready** — `AGENTS.md` and `.github/copilot-instructions.md` guide AI assistants on project conventions

---

## 🎬 How to Use This Template

1. Click **"Use this template"** on GitHub
2. Clone your new repository
3. Replace `github.com/your-username/GoTUIApp` in `go.mod` and all Go files with your module path
4. Run `go run ./cmd/sysinfo` to verify everything works
5. Start building your own commands in `cmd/` and `internal/`

---

## 🖥️ sysinfo — Example TUI Command

The included `sysinfo` command demonstrates a full Bubble Tea application displaying live system information:

```
⬡  System Info

╭─ System ──────────────────────────────╮
│  Hostname        myhost               │
│  OS / Arch       linux / amd64        │
│  Go Version      go1.22.3             │
│  Uptime          2d 4h 12m            │
╰───────────────────────────────────────╯
╭─ CPU ─────────────────────────────────╮
│  Model           Intel Core i7-...    │
│  Cores           8                    │
│  Usage           ████████░░░░  42.3%  │
╰───────────────────────────────────────╯
╭─ Memory ──────────────────────────────╮
│  Total           15.5 GB              │
│  Used            8.2 GB               │
│  Usage           █████████░░░  53.1%  │
╰───────────────────────────────────────╯
╭─ Disk ────────────────────────────────╮
│  Total           512.0 GB             │
│  Used            210.3 GB             │
│  Usage           █████░░░░░░░  41.1%  │
╰───────────────────────────────────────╯
Updated 14:22:07  •  r refresh  •  q quit
```

Stats refresh automatically every 3 seconds. Press `r` to refresh immediately or `q` to quit.

```bash
go run ./cmd/sysinfo
```

---

## 📦 Features

### ✅ CI/CD Ready

- GitHub Actions workflows: lint → test (Linux, macOS, Windows) → cross-compile
- Automated GitHub Releases via GoReleaser on version tags
- Composite actions for reusable pipeline steps

### ✅ Development Environment

- VS Code settings, launch configs, and recommended extensions
- Devcontainer with Go pre-installed
- Makefile-style VS Code tasks for build, test, lint, and run

### ✅ Code Quality

- `golangci-lint` with a curated ruleset (`.golangci.yml`)
- Race detector enabled in all test runs
- Dependabot for automated Go module and GitHub Actions updates

### ✅ Release Automation

- GoReleaser cross-compiles for 5 platform/arch combinations
- Archives (`.tar.gz` / `.zip`), checksums, and changelog generated automatically
- Tag `v1.2.3` → release is live within minutes

### ✅ AI-Agent Ready

- `AGENTS.md` — coding conventions and error-handling patterns for AI assistants
- `.github/copilot-instructions.md` — project-specific guidance for Copilot

---

## 📂 Project Structure

```
GoTUIApp/
├── cmd/
│   └── sysinfo/
│       └── main.go              // Entry point
├── internal/
│   ├── sysinfo/
│   │   ├── sysinfo.go           // System metric collection
│   │   └── sysinfo_test.go
│   └── ui/
│       ├── model.go             // Bubble Tea model, update, view
│       └── model_test.go
├── docs/
│   ├── getting-started.md
│   ├── development.md
│   └── ci-cd.md
├── .devcontainer/
│   └── devcontainer.json
├── .github/
│   ├── actions/                 // Composite actions
│   ├── workflows/               // CI & release pipelines
│   ├── ISSUE_TEMPLATE/
│   └── copilot-instructions.md
├── .vscode/                     // Editor settings & tasks
├── .goreleaser.yml
├── .golangci.yml
├── AGENTS.md
├── CONTRIBUTING.md
└── go.mod
```

---

## 🚀 Getting Started

See the **[Getting Started Guide](docs/getting-started.md)** for full setup instructions.

```bash
git clone https://github.com/marko-stanojevic/hostr.git
cd GoTUIApp
go mod download
go run ./cmd/sysinfo
```

---

## 📘 Documentation

- 🚀 [Getting Started](docs/getting-started.md)
- 🛠️ [Development Guide](docs/development.md)
- 🔄 [CI/CD & Release Guide](docs/ci-cd.md)

---

## 🤝 Contributing

Contributions are welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

Built with ❤️ using [Bubble Tea](https://github.com/charmbracelet/bubbletea) by Charm
