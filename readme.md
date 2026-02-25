# go-zero AI 助手初始化指南

## 人类朋友的使用方式

让 AI 执行：

```
阅读 https://raw.githubusercontent.com/xbclub/go-zero-codex-tools/main/readme.md 并执行初始化步骤
```

AI 会自动完成 skills 安装。

---

> 以下内容供 AI 代码助手（Codex / Qwen Code / 等）阅读并自动执行。

## 目标

为当前项目安装 go-zero 相关的知识库，让 AI 能够更好地辅助 go-zero 开发。

## 初始化步骤

### 确定 Skills 目录

根据当前使用的工具确定 skills 目录位置，如不确定则询问用户。

### Clone 仓库到 Skills 目录

将以下仓库浅层 clone 到当前项目的 skills 目录：

```bash
git clone --depth 1 https://github.com/zeromicro/ai-context.git <skills-dir>/ai-context
git clone --depth 1 https://github.com/zeromicro/zero-skills.git <skills-dir>/zero-skills
git clone --depth 1 https://github.com/xbclub/gorm-zero-skills.git <skills-dir>/gorm-zero-skills
```

如果目录已存在则跳过。

### 为 ai-context 创建 SKILL.md

ai-context 仓库本身没有 SKILL.md，需要在 `<skills-dir>/ai-context/` 目录下创建：

```markdown
---
name: gozero-ai-context
description: go-zero 工作流指令与决策规则
---

## 文件优先级

1. `00-instructions.md` - AI 指令（必读）
2. `workflows.md` - 工作流模式
3. `tools.md` - MCP 工具使用
4. `patterns.md` - 代码模式

## 核心规则

- Spec-First：先创建 `.api` 规范再生成代码
- 使用 mcp-zero 工具，而非手动生成
- 生成完整实现，而非空桩
- 为新服务生成 README.md 文档

## 详细模式

查阅 zero-skills 获取完整实现模式。
```

## 验证

初始化完成后，目录结构应为：

```
<workspace>/
├── .qwen/ 或 .codex/
│   └── skills/
│       ├── ai-context/
│       │   ├── SKILL.md
│       │   └── ...
│       ├── zero-skills/
│       │   ├── SKILL.md
│       │   └── ...
│       └── gorm-zero-skills/
│           ├── SKILL.md
│           └── ...
```