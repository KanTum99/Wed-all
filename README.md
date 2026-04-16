# 🧡 Termux Setup Guide 2026 💛

> *Complete setup guide with troubleshooting & error fixes - Mistral Vibe Edition*

[![Termux](https://img.shields.io/badge/Termux-≥0.118.0-orange?style=flat-square&logo=android)](https://termux.com)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-orange.svg?style=flat-square)](https://github.com)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-yellow?style=flat-square)](http://makeapullrequest.com)

---

## 📋 Table of Contents
- [Installation](#-installation)
- [Quick Setup One-Liner](#-quick-setup-one-liner)
- [Languages Installation](#-languages-installation)
- [Troubleshooting & Error Fixes](#-troubleshooting--error-fixes)
  - [Package Installation Errors](#package-installation-errors)
  - [Storage Permission Issues](#storage-permission-issues)
  - [Command Not Found Errors](#command-not-found-errors)
  - [Python/Pip Issues](#pythonpip-issues)
- [Quick Fix Commands](#-quick-fix-commands)
- [Important Commands](#-important-commands)
- [Emergency Recovery](#-emergency-recovery)
- [Optimization & Maintenance](#-optimization--maintenance)
- [Advanced Troubleshooting](#-advanced-troubleshooting)
- [Pro Tips](#-pro-tips)
- [Support](#-support)

---

## 🚀 Installation

### Download Termux
Ensure you have the latest version of Termux installed from:
- [GitHub Releases](https://github.com/termux/termux-app/releases)
- [F-Droid](https://f-droid.org/packages/com.termux/)

### Copy & Paste Commands
Run the following commands in your Termux terminal:

```bash
# Update system
pkg update && pkg upgrade -y

# Install essential packages
pkg install -y git python python2 wget ruby proot clang

# Setup storage access
termux-setup-storage

# Install programming languages
apt install -y php git golang nano

# Install fun tools
apt install -y cmatrix figlet cowsay toilet lolcat

# Install network tools
pkg install -y curl unzip openssh tor net-tools unrar w3m

# Install Python packages
pip install colorama --upgrade
pip2 install wget requests

# Install additional tools
pkg install -y pacman4console vim
```

---

⚡ Quick Setup One-Liner

```bash
pkg update && pkg upgrade && pkg install git python python2 && pkg install wget ruby proot clang && termux-setup-storage && apt install php git golang -y && apt install nano && apt install cmatrix && pkg install figlet && pkg install wget && pkg install cowsay && pkg install toilet && pkg install ruby && gem install lolcat && pkg install curl && pkg install unzip && pkg install openssh && pkg install tor && pkg install net-tools && pkg install unrar && pkg install clang && pkg install w3m && pkg install proot && pip2 install wget && pip2 install requests && pkg install pacman4console && pkg install vim && pip install colorama && gem install bundler && pip install --upgrade pip
```

---

📚 Languages Installation

Ensure the following languages are installed for development:

Language Command Status
🐍 Python apt install python -y ✅
🐍 Python 2 apt install python2 -y ✅
💎 Ruby apt install ruby -y ✅
🐘 PHP apt install php -y ✅
🐹 Go apt install golang -y ✅
🔵 C/C++ apt install clang -y ✅
🎯 Dart apt install dart -y ✅
📜 Node.js pkg install nodejs-lts -y ✅
🦀 Rust pkg install rust -y ✅

---

🛠️ Troubleshooting & Error Fixes

Package Installation Errors

```bash
# If packages fail to install
pkg update --fix-missing
pkg upgrade -y
termux-change-repo  # Change to a faster mirror
```

Storage Permission Issues

Run the following command to grant Termux access to shared storage:

```bash
termux-setup-storage
```

If the command fails:

1. Go to Android Settings → Apps → Termux → Permissions
2. Make sure Storage access is allowed
3. Restart Termux

Command Not Found Errors

```bash
# Fix missing commands
pkg update
pkg install command-not-found -y
source $PREFIX/etc/profile.d/command-not-found.sh
```

Python/Pip Issues

```bash
# Fix Python environment
pkg reinstall python -y
pip install --upgrade pip
pip install wheel setuptools

# Fix externally-managed-environment error
python -m venv ~/myenv
source ~/myenv/bin/activate

# Fix SSL certificate errors
pkg install ca-certificates -y
```

---

🔧 Quick Fix Commands

Reset Environment

```bash
# Refresh shell environment
source ~/.bashrc
exec bash  # Restart shell
```

Clear Cache & Free Space

```bash
# Clean system cache
pkg clean
apt autoremove -y
rm -rf ~/.cache/* ~/.tmp/*
```

Fix Broken Packages

```bash
# Reinstall broken packages
pkg reinstall $(pkg list-installed | grep -v ok | cut -d/ -f1)
```

---

📝 Important Commands

Command Description
pkg list-all List all available packages
pkg search <tool> Search for a package
pkg show <package> Show package details
termux-info Display Termux system info
termux-open <file> Open a file
termux-clipboard-set Copy text to clipboard
pkg list-installed Show installed packages
pkg upgrade Upgrade all packages

List All Termux Commands

```bash
pkg install texinfo -y && info > commands.txt && cat commands.txt
```

Check for Updates

```bash
pkg --check-mirror update
```

---

🚨 Emergency Recovery

System Won't Start

```bash
# If Termux crashes completely
# Uninstall and reinstall the app
# Then restore from backup or start fresh
```

Complete Reset

```bash
# Nuclear option - reset everything
rm -rf $PREFIX
pkg update && pkg upgrade
```

Backup Before Fixing

```bash
# Always backup first!
tar -zcf backup-before-fix.tar.gz /data/data/com.termux/files/home
```

---

🔄 Optimization & Maintenance

Clean Cache & Old Files

```bash
pkg clean
apt autoremove -y
```

Backup & Restore

Backup:

```bash
tar -zcvf termux-backup.tar.gz /data/data/com.termux/files/home
```

Restore:

```bash
tar -zxvf termux-backup.tar.gz -C /data/data/com.termux/files
```

---

🔬 Advanced Troubleshooting

Library Issues

```bash
# Fix shared library problems
pkg install libandroid-support -y
pkg reinstall $PREFIX/bin/*
```

Permission Problems

```bash
# Fix file permissions
chmod 755 $PREFIX/bin/*
chmod +x ~/storage/shared/termux-scripts/*.sh 2>/dev/null || true
```

Memory Issues

```bash
# Check system resources
free -m
df -h

# If low on memory:
pkg clean
rm -rf ~/.cache
```

---

💡 Pro Tips

· 🎯 Use tmux for multitasking
· 🔋 Enable termux-wake-lock to prevent sleep
· 📁 Store scripts in ~/storage/shared/termux-scripts
· 📱 Use termux-api for Android integration
· 🚀 Use zsh instead of bash for better autocomplete
· 💾 Always backup before major changes

---

☕ Support My Work

https://img.shields.io/badge/Buy%20Me%20a%20Coffee-orange?style=flat-square&logo=buy-me-a-coffee
https://img.shields.io/badge/Ko--fi-yellow?style=flat-square&logo=ko-fi

---

<div align="center">

Made with 🧡 & 💛 for the Termux Community

"Keep your terminal running, and it will never betray you"

⬆ Back to Top

</div>
