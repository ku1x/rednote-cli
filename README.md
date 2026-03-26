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

## License

Apache License 2.0

---

# 中文

## 什么是 RedNote？

**RedNote**（小红书海外版）是小红书的国际版本，专为海外用户设计的生活方式分享平台。

- **网站**: https://www.rednote.com
- **目标用户**: 中国大陆以外的国际用户
- **内容**: 生活方式、时尚、美食、旅行、AIGC 等

## 功能特性

- 🔐 **认证** — 自动提取浏览器 Cookie、二维码登录、状态检查
- 🔍 **搜索** — 关键词搜索笔记、用户搜索、话题搜索
- 📖 **阅读** — 笔记详情、评论、用户主页
- 📰 **信息流** — 推荐流、热门分类
- 👥 **社交** — 关注/取关、收藏
- 👍 **互动** — 点赞、收藏、评论、回复
- ✍️ **创作** — 发布图文笔记、话题标签
- 🔔 **通知** — 未读数、@提及、点赞
- 🛡️ **反检测** — 一致的浏览器指纹、高斯抖动
- 📊 **结构化输出** — 支持 `--yaml` 和 `--json`

## 安装

```bash
# 推荐: uv tool (快速、隔离)
uv tool install rednote-cli

# 或: pipx
pipx install rednote-cli
```

从源码安装:

```bash
git clone https://github.com/loudsy-ai/rednote-cli.git
cd rednote-cli
uv tool install .
```

## 快速开始

```bash
# 登录（从浏览器提取 Cookie）
rednote login

# 检查状态
rednote status

# 搜索笔记
rednote search "AIGC"

# 发布笔记
rednote post --title "我的第一篇笔记" --body "你好 RedNote!" --images ./photo.jpg

# 查看信息流
rednote feed
```

## 使用方法

### 认证

```bash
rednote login                    # 从浏览器提取 Cookie
rednote login --qrcode           # 二维码登录
rednote status                   # 检查登录状态
rednote whoami                   # 详细资料
rednote logout                   # 清除保存的 Cookie
```

### 搜索与阅读

```bash
rednote search "关键词"          # 搜索笔记
rednote search-user "用户名"     # 搜索用户
rednote topics "话题"            # 搜索话题
rednote read <笔记ID>            # 阅读笔记
rednote comments <笔记ID>        # 查看评论
rednote user <用户ID>            # 用户主页
```

### 创作者

```bash
rednote post --title "标题" --body "内容" --images ./图片.jpg --topic "AIGC"
rednote my-notes                 # 我的笔记列表
rednote delete <笔记ID>          # 删除笔记
```

### 互动

```bash
rednote like <笔记ID>            # 点赞
rednote unlike <笔记ID>          # 取消点赞
rednote favorite <笔记ID>        # 收藏
rednote comment <笔记ID> "评论"  # 评论
rednote follow <用户ID>          # 关注
```

## 配置

配置目录: `~/.rednote-cli/`

必需的 Cookie:
- `a1` — 认证令牌
- `webId` — 浏览器标识
- `web_session` — 会话令牌（来自 localStorage）
- `websectiga` — 安全令牌
- `sec_poison_id` — 反机器人令牌

## 与小红书 CLI 的区别

| 功能 | RedNote CLI | 小红书 CLI |
|------|-------------|------------|
| 域名 | rednote.com | xiaohongshu.com |
| API 主机 | webapi.rednote.com | edith.xiaohongshu.com |
| 目标用户 | 国际用户 | 中国大陆用户 |
| 上传主机 | ros-upload.xiaohongshu.com | ros-upload.xiaohongshu.com |

## 致谢

本项目基于 [jackwener](https://github.com/jackwener) 的 [xiaohongshu-cli](https://github.com/jackwener/xiaohongshu-cli) 修改，适配 RedNote（小红书海外版）。

## 许可证

Apache License 2.0

---

## Disclaimer / 免责声明

**English**: This tool is for educational and personal use only. Use responsibly and respect RedNote's Terms of Service. The authors are not responsible for any consequences resulting from the use of this tool.

**中文**: 本工具仅供教育和个人使用。请负责任地使用，并尊重 RedNote 的服务条款。作者不对使用本工具产生的任何后果负责。
