# go-zero Codex Skills（AI 指令）

本仓库用于发送给 AI 自动设置技能环境。**禁止**通过“skill 导入”或“系统技能安装器”等方式加载技能。
AI 必须按以下流程在当前项目内完成初始化：

1. 将 `.codex` 目录克隆/复制到当前项目根目录。
2. 运行初始化脚本：

```bash
./scripts/init-codex-skills.sh
```

执行后效果：
- 克隆或更新 `ai-context` 与 `zero-skills` 到 `.codex/skills/*/repo`。
- 若检测到已安装 Go，则安装并编译 `mcp-zero` 到 `.mcp-zero/`。
- 生成或更新 `.codex/mcp.json` 与 `.codex/config.toml`。

约束：
- 如果目标目录已存在但不是 git 仓库，脚本会退出并提示如何处理。
- 若未安装 Go，则跳过 `mcp-zero` 安装；需要时提示用户安装 Go。
