# aiwolfs — 我的 AI 资源仓库

个人 AI 资源管理仓库：集中积累 skills、rules、agents 和使用经验（learnings），通过 [teamai-cli](https://github.com/Tencent/teamai-cli) 在所有终端的所有受支持 AI 工具之间自动同步。

## 接入一台新终端

每台机器（Windows / WSL / 服务器）只需初始化一次，之后每个 AI 会话开始时自动拉取最新资源：

```bash
npm install -g teamai-cli
teamai init https://github.com/killingwolf/aiwolfs --scope user
```

- `--scope user`：资源装到用户主目录，本机所有项目共享（个人多终端场景推荐）
- 不带该参数则为工作区级安装，只对当前目录生效
- 初始化后检查：`teamai doctor`（各项应通过）、`teamai list`（查看已同步的资源）
- 支持的工具包括 Claude Code、Codex、Cursor、Copilot、Qoder、Trae、WorkBuddy、CodeBuddy、OpenCode 等

## 目录结构

```text
skills/               技能
├─ ecc/                 上游：工程实践（everything-claude-code，MIT）
├─ mattpocock/          上游：工程方法论（mattpocock/skills，MIT）
└─ <name>/              我自己的技能（文件夹 + SKILL.md，或单文件 skills/<name>.md）
rules/                规则
├─ common/              上游：编码 / 评审 / 测试 / 安全等基线
└─ <name>.md            我自己的规则（frontmatter 加 paths: 可限定生效范围）
agents/               评审子代理：code-reviewer / database-reviewer / security-reviewer
docs/                 个人笔记与文档（setup-log.md 记录了各终端与决策历史）
learnings/            使用经验与教训（首次沉淀时自动创建）
env/                  随仓库分发的环境变量
members/              成员注册
teamai.yaml           teamai 配置
```

## 积累经验的几种方式

1. **会话结束提示** — 会话中纠正过 AI、拒绝过工具调用或 AI 反复重试时，teamai 会在结束时提议 share-learnings 流程，把值得记的经验整理成 learning 入库。
2. **主动 push** — 在工具里写好 skill/rule（如 `~/.claude/skills/<name>/SKILL.md`）后运行 `teamai push`：自动开分支、提 PR，合入 main 后分发到所有终端。
3. **导入存量** — `teamai import --from-tools` 扫描本机各 AI 工具的规则，分类确认后入库。
4. **直接 git 提交** — 个人仓库，也欢迎直接 commit & push（`.gitattributes` 已约定全库 LF 换行，跨平台不会再出现整库假 diff）。
5. **检索** — `teamai recall "关键词"` 搜索 learnings / docs；`teamai recall --check "关键词"` 快速判断相关性。

## 上游内容与许可

仓库骨架 fork 自 [teamai-hub/teamai-template](https://github.com/teamai-hub/teamai-template)。内置的部分 skills / rules / agents 来自以下开源项目（按命名空间组织）：

| 命名空间 | 上游 | 许可 |
|---|---|---|
| `skills/ecc/`、`rules/common/`、`agents/` | [everything-claude-code](https://github.com/affaan-m/everything-claude-code) | ✅ MIT |
| `skills/mattpocock/` | [mattpocock/skills](https://github.com/mattpocock/skills) | ✅ MIT |

- MIT 许可全文：[`LICENSE`](./LICENSE)（ECC）与 [`skills/mattpocock/LICENSE`](./skills/mattpocock/LICENSE)
- 逐文件的上游路径映射：[`ATTRIBUTION.md`](./ATTRIBUTION.md)

> 所有内置内容均为 MIT 许可，可按 MIT 条款复制、修改、再分发；请保留版权与许可声明。
