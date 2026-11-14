# Setup Log

各终端的接入状态与关键决策记录，供任意终端上的 AI 会话查阅（`teamai recall "setup"` 可检索到本页）。

## 2026-11-14 初始设置

**仓库来源**：fork 自 `teamai-hub/teamai-template`（2026-11-14），保留上游 MIT 内容与署名（`ATTRIBUTION.md`、`LICENSE`）。昨天在 Windows 侧的一次 workspace 级 `teamai init` 已通过 PR #1 把 teamai 脚手架（`teamai.yaml`、`members/`、`env/`、`docs/`）推入 main。

**终端状态**：

| 终端 | 状态 | 备注 |
|---|---|---|
| Windows（`C:\Users\zhanghengfeng`） | 已装 teamai-cli 0.30.0（WorkBuddy 管理的 node 全局包） | 曾在临时目录 `WorkBuddy\2026-11-13-21-34-14` 做过 **workspace 级** init，资源只对该临时目录生效；该目录里的 aiwolfs 副本被工具改成了 CRLF（5000+ 行假 diff，无实质内容）。建议改做 user 级 init 后废弃该临时副本。**2026-11-14 决定：暂不动 Windows，保留现状** |
| WSL（`stjk@ben`，Ubuntu） | ✅ 已接入（2026-11-14） | teamai-cli 0.30.0（npm 全局，fnm node v26）；`teamai init --scope user` 完成，钩子已注入 Claude Code（`~/.claude`）与 OpenCode；首次 `teamai pull` 同步 11 skills / 10 rules / 3 agents / 2 learnings，`teamai doctor` 全部通过。工作副本 `/home/stjk/ben/aiwolfs` |

**决策**：

- 全库统一 LF 换行（`.gitattributes`：`* text=auto eol=lf`），根治 Windows/WSL 之间的换行符假 diff。
- 上游命名空间（`skills/ecc/`、`skills/mattpocock/`、`rules/common/`、`agents/`）保持原样；个人资源放共享根（`skills/<name>/`、`rules/<name>.md`），单人使用无需 roles/projects 命名空间。
- README 改为中文个人版；模板的双语 README 移除，上游署名保留在 README「上游内容与许可」一节及 `ATTRIBUTION.md`。
- 经验沉淀走 teamai 标准流程：会话结束的 share-learnings 提示、`teamai push`（分支 + PR）、`teamai contribute`；个人仓库也允许直接 git push main。
- 本次个性化改造走 PR：[#2](https://github.com/killingwolf/aiwolfs/pull/2)（personalize → main），合入后各终端下次会话自动同步。
