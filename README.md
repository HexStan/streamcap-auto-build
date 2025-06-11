# 📦 StreamCap Docker 每夜版

本仓库包含一个 GitHub Actions 工作流，用于**每天自动构建并推送 [`ihmily/StreamCap`](https://github.com/ihmily/StreamCap) 项目的 Docker 镜像**，构建时间为**北京时间每日凌晨 0 点**。

## 🛠 工作流简介

工作流名称：`Daily Docker Build`，主要执行以下操作：

1. **每天定时触发**（北京时间 00:00，对应 UTC 16:00），或手动触发（通过 GitHub 网页界面）。
2. **克隆** `ihmily/StreamCap` 仓库的 `main` 分支代码。
3. **生成当前日期的 Docker 标签**（例如：`2025-06-12`）。
4. **构建并推送 Docker 镜像**到 Docker Hub，包含以下两个标签：

   * `hexstan/streamcap-main:latest`
   * `hexstan/streamcap-main:<YYYY-MM-DD>`（如：`hexstan/streamcap-main:2025-06-12`）

## ✅ 使用示例

拉取最新构建的镜像：

```bash
docker pull hexstan/streamcap-main:latest
```

拉取某天构建的特定版本镜像：

```bash
docker pull hexstan/streamcap-main:2025-06-12
```
