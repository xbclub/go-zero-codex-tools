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