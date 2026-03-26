# rednote-cli

[![Python](https://img.shields.io/badge/python-%3E%3D3.10-blue.svg)](https://pypi.org/project/rednote-cli/)
[![License](https://img.shields.io/badge/license-Apache%202.0-green.svg)](LICENSE)

A CLI for **RedNote (小红书海外版 / Xiaohongshu International)** — search, read, interact, and post via reverse-engineered API 📕

**RedNote CLI** 专为小红书海外版 (rednote.com) 设计的命令行工具 — 搜索、阅读、互动、发布 📕

[English](#english) | [中文](#中文)

---

# English

## What is RedNote?

**RedNote** (小红书海外版) is the international version of Xiaohongshu (小红书), a popular Chinese social media platform for sharing lifestyle content, product reviews, and creative works. 

- **Website**: https://www.rednote.com
- **Target Users**: International users outside mainland China
- **Content**: Lifestyle, fashion, food, travel, AIGC, and more

## Features

- 🔐 **Auth** — auto-extract browser cookies, QR code login, status check
- 🔍 **Search** — notes by keyword, user search, topic search
- 📖 **Reading** — note detail, comments, user profiles
- 📰 **Feed** — recommendation feed, hot/trending by category
- 👥 **Social** — follow/unfollow, favorites
- 👍 **Interactions** — like, favorite, comment, reply
- ✍️ **Creator** — post image notes with topics/hashtags
- 🔔 **Notifications** — unread count, mentions, likes
- 🛡️ **Anti-detection** — consistent browser fingerprint, Gaussian jitter
- 📊 **Structured output** — `--yaml` and `--json` support

## Installation

```bash
# Recommended: uv tool (fast, isolated)
uv tool install rednote-cli

# Or: pipx
pipx install rednote-cli
```

From source:

```bash
git clone https://github.com/loudsy-ai/rednote-cli.git
cd rednote-cli
uv tool install .
```

## Quick Start

```bash
# Login (extract cookies from browser)
rednote login

# Check status
rednote status

# Search notes
rednote search "AIGC"

# Post a note
rednote post --title "My First Post" --body "Hello RedNote!" --images ./photo.jpg

# View feed
rednote feed
```

## Usage

### Auth

```bash
rednote login                    # Extract cookies from browser
rednote login --qrcode           # QR code login
rednote status                   # Check login status
rednote whoami                   # Detailed profile
rednote logout                   # Clear saved cookies
```

### Search & Read

```bash
rednote search "keyword"         # Search notes
rednote search-user "username"   # Search users
rednote topics "hashtag"         # Search topics
rednote read <note_id>           # Read a note
rednote comments <note_id>       # View comments
rednote user <user_id>           # User profile
```

### Creator

```bash
rednote post --title "Title" --body "Content" --images ./img.jpg --topic "AIGC"
rednote my-notes                 # List your notes
rednote delete <note_id>         # Delete a note
```

### Interactions

```bash
rednote like <note_id>           # Like a note
rednote unlike <note_id>         # Unlike a note
rednote favorite <note_id>       # Favorite a note
rednote comment <note_id> "text" # Comment on a note
rednote follow <user_id>         # Follow a user
```

## Configuration

Config directory: `~/.rednote-cli/`

Required cookies:
- `a1` — Authentication token
- `webId` — Browser identifier
- `web_session` — Session token (from localStorage)
- `websectiga` — Security token
- `sec_poison_id` — Anti-bot token

## Differences from Xiaohongshu CLI

| Feature | RedNote CLI | Xiaohongshu CLI |
|---------|-------------|-----------------|
| Domain | rednote.com | xiaohongshu.com |
| API Host | webapi.rednote.com | edith.xiaohongshu.com |
| Target Users | International | Mainland China |
| Upload Host | ros-upload.xiaohongshu.com | ros-upload.xiaohongshu.com |

## Acknowledgments

This project is a modified version of [xiaohongshu-cli](https://github.com/jackwener/xiaohongshu-cli) by [jackwener](https://github.com/jackwener), adapted for RedNote (小红书海外版).

### 🙏 Special Thanks to [jackwener](https://github.com/jackwener)

This project would not be possible without the excellent work on [xiaohongshu-cli](https://github.com/jackwener/xiaohongshu-cli). We are deeply grateful for:

- **Reverse Engineering Efforts**: The comprehensive API reverse engineering work
- **Clean Architecture**: Well-structured, modular codebase
- **Anti-Detection Features**: Sophisticated browser fingerprint simulation
- **Active Maintenance**: Continuous updates and improvements

If you find this tool useful, please also consider starring the [original project](https://github.com/jackwener/xiaohongshu-cli) ⭐

---

## 致谢

本项目基于 [jackwener](https://github.com/jackwener) 的 [xiaohongshu-cli](https://github.com/jackwener/xiaohongshu-cli) 修改，适配 RedNote（小红书海外版）。

### 🙏 特别感谢 [jackwener](https://github.com/jackwener)

没有 [xiaohongshu-cli](https://github.com/jackwener/xiaohongshu-cli) 的优秀工作，就不会有这个项目。我们深深感谢：

- **逆向工程努力**: 全面的 API 逆向工程工作
- **清晰的架构**: 结构良好、模块化的代码库
- **反检测功能**: 精细的浏览器指纹模拟
- **积极维护**: 持续的更新和改进

如果你觉得这个工具有用，也请给[原项目](https://github.com/jackwener/xiaohongshu-cli)点个 Star ⭐

## 许可证

Apache License 2.0

---

## Disclaimer / 免责声明

**English**: This tool is for educational and personal use only. Use responsibly and respect RedNote's Terms of Service. The authors are not responsible for any consequences resulting from the use of this tool.

**中文**: 本工具仅供教育和个人使用。请负责任地使用，并尊重 RedNote 的服务条款。作者不对使用本工具产生的任何后果负责。
