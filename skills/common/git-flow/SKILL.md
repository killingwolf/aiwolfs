---
name: git-flow
description: 团队 Git 工作流约定。在任何团队项目中创建分支、提交代码或开 PR 时使用。
---

# 团队 Git 约定（共享 skill 示例，common 命名空间 = 全员可见）

- 分支命名：`feat/<工单号>-<简述>`、`fix/<工单号>-<简述>`
- 提交信息：Conventional Commits（feat / fix / refactor / docs / test / chore）
- 所有变更经 PR 合入，默认分支开启保护，禁止直推
- PR 描述需包含：变更动机、测试方式、影响面
