# OpenClaw 项目学习路径指南

## 项目概述

OpenClaw 是一个运行在用户自己设备上的个人 AI 助手，支持多种消息渠道（WhatsApp、Telegram、Slack、Discord 等），并提供语音交互、Canvas 可视化等功能。

## 学习路径

### 1. 基础了解

**建议学习顺序：**

1. **README.md** - 了解项目的基本概念、功能和架构
2. **docs/start/getting-started.md** - 快速入门指南
3. **docs/concepts/architecture.md** - 系统架构概述

**关键文件：**

- `README.md` - 项目概览和快速开始
- `docs/start/getting-started.md` - 详细的安装和配置指南
- `docs/concepts/architecture.md` - 架构设计文档

### 2. 核心组件学习

**Gateway（控制平面）**

- **文件位置：** `src/gateway/`
- **主要功能：** WebSocket 控制平面，管理会话、通道和事件
- **关键文件：**
  - `src/gateway/server.ts` - Gateway 服务器实现
  - `src/gateway/client.ts` - Gateway 客户端实现
  - `src/gateway/events.ts` - 事件处理

**Agent（AI 代理）**

- **文件位置：** `src/agents/`
- **主要功能：** AI 代理运行时，处理用户请求
- **关键文件：**
  - `src/agents/context.ts` - 代理上下文管理
  - `src/agents/skills.ts` - 技能系统

**Channels（消息渠道）**

- **文件位置：** `src/telegram/`, `src/discord/`, `src/slack/` 等
- **主要功能：** 各种消息平台的集成
- **关键文件：**
  - `src/telegram/bot.ts` - Telegram 机器人实现
  - `src/discord/client.ts` - Discord 客户端实现
  - `src/slack/client.ts` - Slack 客户端实现

### 3. 工具系统

**文件位置：** `src/browser/`, `src/canvas-host/`, `src/nodes/`

- **浏览器控制：** `src/browser/` - 管理 Chrome/Chromium 浏览器
- **Canvas：** `src/canvas-host/` - 可视化工作区
- **节点控制：** `src/nodes/` - 设备控制（相机、屏幕录制等）

### 4. 配置系统

**文件位置：** `src/config/`

- **主要功能：** 管理应用配置
- **关键文件：**
  - `src/config/config.ts` - 配置管理
  - `src/config/schema.ts` - 配置 schema

### 5. 扩展和技能

**扩展：** `extensions/` - 通道插件
**技能：** `skills/` - 各种技能实现

### 6. 应用开发

**文件位置：** `apps/`

- **macOS 应用：** `apps/macos/`
- **iOS 应用：** `apps/ios/`
- **Android 应用：** `apps/android/`

## 学习建议

1. **从基础开始：** 先了解项目的整体架构和核心概念
2. **实践为主：** 按照文档尝试安装和配置 OpenClaw
3. **逐步深入：** 从 Gateway 开始，然后学习 Agent、Channels 和 Tools
4. **参考示例：** 查看已有的扩展和技能实现
5. **测试驱动：** 运行测试用例了解功能实现

## 关键技术栈

- **TypeScript** (ESM)
- **Node.js** ≥ 22
- **pnpm** 包管理
- **WebSocket** 通信
- **前端**：Vite, Lit
- **移动应用**：iOS/Android
- **桌面应用**：macOS

## 开发环境设置

```bash
# 克隆仓库
git clone https://github.com/openclaw/openclaw.git
cd openclaw

# 安装依赖
pnpm install

# 构建项目
pnpm build

# 开发模式运行
pnpm gateway:watch
```

## 学习资源

- **官方文档**：`docs/` 目录下的各种文档
- **架构文档**：`docs/concepts/architecture.md`
- **配置指南**：`docs/gateway/configuration.md`
- **通道文档**：`docs/channels/` 目录下的各种通道文档
- **工具文档**：`docs/tools/` 目录下的工具文档

通过以上学习路径，你可以逐步掌握 OpenClaw 的核心功能和架构，从而能够进行开发和扩展。
