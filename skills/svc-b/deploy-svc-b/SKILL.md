---
name: deploy-svc-b
description: 服务 B 的部署流程。仅在部署、发布或回滚服务 B 时使用。
---

# 服务 B 部署（svc-b 命名空间 = 张三、李四可见）

1. 部署前检查：`make -C svc-b lint && make -C svc-b test`
2. 预发环境：`./scripts/deploy.sh svc-b staging`
3. 生产发布需二人复核，执行：`./scripts/deploy.sh svc-b prod`
4. 回滚：`./scripts/deploy.sh svc-b rollback --to <版本号>`

> 替换为服务 B 的真实部署步骤。
