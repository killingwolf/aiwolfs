---
name: deploy-svc-c
description: 服务 C 的部署流程。仅在部署、发布或回滚服务 C 时使用。
---

# 服务 C 部署（svc-c 命名空间 = 仅李四可见）

1. 部署前检查：`make -C svc-c lint && make -C svc-c test`
2. 预发环境：`./scripts/deploy.sh svc-c staging`
3. 生产发布需二人复核，执行：`./scripts/deploy.sh svc-c prod`
4. 回滚：`./scripts/deploy.sh svc-c rollback --to <版本号>`

> 替换为服务 C 的真实部署步骤。
