# fork 用途
本 fork 仅用于构建"打了 9router-perf 性能补丁"的镜像，推送到 GHCR。
- 补丁：`patches/9router-perf.patch`（源自上游 PR decolua/9router#4721）
- CI：`.github/workflows/build-9router.yml`（轮询上游 tag → 打补丁 → 多架构构建 → 推 GHCR）
- 上游合并 PR 后：CI 自动检测并跳过补丁（镜像回归纯上游）。
- 消费方：cpa2 集群各机（`ROUTER_IMAGE=ghcr.io/cherylblaker337/9router:latest`）。
