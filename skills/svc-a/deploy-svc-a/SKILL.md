---
name: deploy-svc-a
description: 服务 A 的部署流程。仅在部署、发布或回滚服务 A 时使用。
---

# 服务 A 部署（svc-a 命名空间 = 仅张三可见）

1. 部署前检查：`make -C svc-a lint && make -C svc-a test`
2. 预发环境：`./scripts/deploy.sh svc-a staging`
3. 生产发布需二人复核，执行：`./scripts/deploy.sh svc-a prod`
4. 回滚：`./scripts/deploy.sh svc-a rollback --to <版本号>`

> 替换为服务 A 的真实部署步骤。
