# Obsidian GitHub Pull&Push

A lightweight Obsidian community plugin that synchronizes your entire Obsidian vault with a GitHub repository.

No external scripts or terminal commands are required — Git operations are handled directly by the plugin.

## Features

* **One-click sync** — Sync your vault from the ribbon icon or status bar.
* **Automatic vault detection** — The plugin automatically detects your current vault.
* **Git setup** — Automatically initializes Git when needed.
* **Pull & push** — Pull changes from GitHub, push local changes, or do both with one click.
* **Automatic sync** — Optionally sync every 5, 15, 30, or 60 minutes.
* **Sync on startup** — Optionally synchronize shortly after Obsidian starts.
* **Vault restoration** — Restore an entire vault from a GitHub repository.
* **Live logs** — See Git operations and synchronization status directly in Obsidian.
* **Multiple authentication methods** — Supports HTTPS credentials, Personal Access Tokens, Git Credential Manager, and SSH.
* **Configurable Git** — Use the Git installation on your system or specify a custom executable.

## Installation

### Community Plugins

Open Obsidian and go to:

**Settings → Community plugins → Browse**

Search for:

**GitHub Pull&Push**

Install and enable the plugin.

### Manual Installation

1. Download `main.js`, `manifest.json`, and `styles.css` from the repository.
2. Create the following folder inside your vault:

```text
.obsidian/plugins/obsidian-git-sync/
```

3. Place the three files inside the folder.
4. Restart or reload Obsidian.
5. Enable **GitHub Pull&Push** under **Settings → Community plugins**.

## Requirements

The plugin requires **Git** to be installed on your computer.

Check whether Git is already installed:

```bash
git --version
```

If it isn't installed:

**Windows**

```powershell
winget install Git.Git
```

**macOS**

```bash
brew install git
```

**Debian / Ubuntu**

```bash
sudo apt update
sudo apt install git
```

If Obsidian cannot find Git automatically, you can specify its path in the plugin settings.

## Setup

After installing the plugin:

1. Open **Settings → Community plugins → GitHub Pull&Push**.
2. Enter your GitHub repository URL.
3. Enter your Git author name and email.
4. Select the branch you want to use, usually `main`.
5. Authenticate with GitHub if required.
6. Click **Sync Vault**.

For example:

```text
https://github.com/username/my-vault.git
```

SSH repositories are also supported:

```text
git@github.com:username/my-vault.git
```

The plugin will automatically initialize Git in your vault if necessary.

## Syncing Your Vault

Once configured, click the **sync icon** in the left ribbon.

The plugin will:

1. Detect your vault.
2. Initialize Git if necessary.
3. Connect to your GitHub repository.
4. Pull remote changes if configured.
5. Commit local changes.
6. Push the changes to GitHub.

You can also access these actions from the **Command Palette**:

```text
Git Sync: Sync vault to GitHub
Git Sync: Pull latest changes from GitHub
Git Sync: Push changes to GitHub
Git Sync: View sync logs & status
```

## Automatic Sync

You can optionally enable automatic synchronization from the plugin settings.

Available intervals:

* 5 minutes
* 15 minutes
* 30 minutes
* 60 minutes

You can also enable **Sync on Startup** to automatically synchronize when Obsidian starts.

## Restoring a Vault

If you are setting up Obsidian on a new computer, you can restore your vault directly from GitHub.

1. Install Obsidian and Git.
2. Create and open an empty vault.
3. Install **GitHub Pull&Push**.
4. Enter your GitHub repository in the plugin settings.
5. Authenticate with GitHub.
6. Run:

```text
Git Sync: Pull vault from GitHub (replace local files)
```

The plugin checks the repository before replacing your local vault.

> **Warning:** This operation can replace local files. Make sure you do not have important uncommitted changes before using it.

## Authentication

The plugin uses Git's built-in authentication mechanisms.

You can use:

* Git Credential Manager
* HTTPS + Personal Access Token
* SSH

No GitHub token needs to be entered directly into the plugin.

For most users, **Git Credential Manager or SSH** is recommended.

## Configuration

The plugin provides additional options for advanced users, including:

* Git executable path
* Branch selection
* Commit message templates
* Pull before push
* Force push
* Automatic synchronization
* Vault structure validation

The default settings are designed for a simple single-user vault.

## Important

Git is a synchronization and version-control system, not a traditional backup service.

Keep an independent backup of important vault data, especially if your vault contains large attachments or files that cannot be recreated.

Be particularly careful with **Force Push** and **Pull vault from GitHub**, as these operations can overwrite existing data.

## Repository

Source code and releases:

[IlDimaz/ObsidianGitManage](https://github.com/IlDimaz/ObsidianGitManage?utm_source=chatgpt.com)

## License

MIT License
