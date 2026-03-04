# Claude Code 使用笔记

| 分类 | 功能 | 操作方式/说明 |
|------|------|---------------|
| **界面操作** | 切换工作模式 | Shift + Tab |
| | 默认模式 | `?` - 修改文件前一定会询问用户 |
| | 自动模式 | `accept edits` - 自动修改文件 |
| | 讨论模式 | `plan mode on` - 只讨论、不修改文件 |
| | 键盘快捷回滚 | 按两下 Esc 键，回滚到上一个阶段并恢复代码 |
| | 编辑器编辑文档 | Ctrl + G - 在编辑器中编辑需要输入的文档 |
| **终端操作** | 执行终端命令 | `!` 前缀，如 `!npm run dev` |
| | 查看任务 | `/tasks` - 查看正在运行的 bash 终端任务 |
| | 关闭任务 | `k` - 关闭任务 |
| **快捷命令** | 回滚对话 | `/rewind` - 回滚到当前对话的上个或对应阶段，恢复修改过的代码 |
| | 恢复对话 | `/resume` - 回到指定的对话 |
| | 压缩上下文 | `/compact` |
| | Agent 管理 | `/agents` |
| | 插件管理 | `/plugin` - 将 skills、hooks 等打包到 claude 中 |
| **命令行参数** | 跳过权限 | `claude --dangerously-skip-permissions` - 直接开启所有权限 |
| | 继续对话 | `claude -c` - 默认打开上一个对话（c = continue） |
| **图片操作** | 添加图片 | 截图保存到本地后，复制文件给 claude |
| **MCP** | 添加 MCP 服务 | `claude mcp add --transport http figma https://mcp.figma.com/mcp` |
| **项目配置** | 项目规则 | `claude.md` - 项目级别的规则 |
| **Agent 系统** | Agent Skill | 上下文关联大的任务，在当前对话中复用 |
| | Sub Agent | 每次都是独立运行的子 agent，适合独立任务场景 |
| | 使用方式 | `/agents` 然后根据提示操作即可 |
| | 自定义 Agent | 使用 YAML 格式配置（见下方示例） |

---

## 自定义 Sub Agent 示例

```yaml
---
name: code-reviewer
description: "当用户请求代码审核、Code Review 或检查规范时调用。此代理专门根据团队特定的 JS 和 CSS 规范对代码进行审查。"
model: sonnet
color: green
---
```
