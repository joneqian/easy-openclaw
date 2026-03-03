# Easy OpenClaw

一键部署 [OpenClaw](https://github.com/openclaw) 的 Docker Compose 配置。

## 快速开始

### 前置条件

- Docker
- Docker Compose

### 部署

```bash
docker compose -f openclaw-software-company.yml up -d
```

### 访问

- **Dashboard**: http://localhost:3100
- **Gateway**: http://localhost:18800

### 查看日志

```bash
docker compose -f openclaw-software-company.yml logs -f openclaw-software-company
```

### 进入容器

```bash
docker compose -f openclaw-software-company.yml exec openclaw-software-company bash
```

### 初始化配置

进入容器后运行：

```bash
openclaw onboard
```

### 停止

```bash
docker compose -f openclaw-software-company.yml down
```

## 数据持久化

数据存储在 `./openclaw-software-company-data` 目录中。

## 配置说明

| 配置项 | 说明 |
|--------|------|
| `18800:18789` | Gateway 网关端口映射 |
| `3100:3000` | Dashboard 端口映射 |
| `TZ=Asia/Shanghai` | 时区设置 |
| `privileged: true` | Docker 沙箱支持 |
