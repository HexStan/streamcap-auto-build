# 📦 StreamCap Docker 自动构建版

本项目基于 GitHub Actions 工作流自动构建并推送 [`ihmily/StreamCap`](https://github.com/ihmily/StreamCap) 项目的 Docker 镜像。

## 🛠 工作流简介

暂时只有一个工作流`Docker Build Nightly`，主要执行以下操作：

1. 每天定时触发（北京时间 00:00，对应 UTC 16:00），或手动触发。
2. 克隆 `ihmily/StreamCap` 仓库的 `main` 分支代码。
3. 生成当前日期的 Docker tag（例如：`2025-06-12`）。
4. 构建并推送 Docker 镜像到 [StreamCap 每夜版仓库](https://hub.docker.com/r/hexstan/streamcap-nightly)，包含以下两个tag：

   * `hexstan/streamcap-nightly:latest`
   * `hexstan/streamcap-nightly:<YYYY-MM-DD>`（如：`hexstan/streamcap-nightly:2025-06-12`）

## ✅ 使用示例

拉取最新构建的每夜版镜像：

```bash
docker pull hexstan/streamcap-nightly:latest
```

拉取某天构建的特定每夜版镜像：

```bash
docker pull hexstan/streamcap-nightly:2025-06-12
```
