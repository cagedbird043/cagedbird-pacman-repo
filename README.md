# CagedBird Private Pacman Repository 🎖️

[![Arch](https://img.shields.io/badge/Arch-x86__64%20%7C%20aarch64-blue?logo=arch-linux)](https://miceworld.top/cagedbird-pacman-repo/)
[![Speed](https://img.shields.io/badge/Accelerated_by-Tencent_EdgeOne-orange)](https://miceworld.top)

本项目托管由 CI/CD 自动构建的 **sing-box-ref1nd** 系列软件包，通过腾讯云 EdgeOne (Anycast) 全球加速分发。

## 🚀 快速接入

### 1. 配置 Pacman 软件源

编辑 `/etc/pacman.conf`，将以下内容置于所有源的最上方（以获得最高优先级）：

```ini
[cagedbird-repo]
SigLevel = Optional TrustAll
Server = https://miceworld.top/cagedbird-pacman-repo/$arch
```

### 2. 同步并安装

```bash
sudo pacman -Syy
sudo pacman -S sing-box-ref1nd
```

## 🏗️ 架构说明

- **编译源**: [sing-box-auto-build-ci](https://github.com/Mice-Tailor-Infra/sing-box-auto-build-ci)
- **加速链路**: GitHub Pages -> **Tencent EdgeOne (Anycast)** -> End User
- **微架构优化**:
  - `x86_64`: 默认打包 **v3** 等级指令集优化版。
  - `aarch64`: 针对 ARM 开发板、手机及 Apple Silicon 优化。
