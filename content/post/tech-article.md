---
title: Arch Linux 安装 Valkey 教程
date: 2025-04-18
tags: ["Linux"]
categories: ["技术"]
---

## Arch Linux 安装 Valkey 教程

Valkey 是一个高性能的开源键值存储数据库，本教程将指导您如何在 Arch Linux 系统上安装 Valkey。

### 步骤 1: 更新系统

首先，更新您的 Arch Linux 系统以确保所有软件包都是最新的。

```bash
sudo pacman -Syu
```

### 步骤 2: 安装编译工具和依赖

安装编译 Valkey 所需的工具和依赖库。

```bash
sudo pacman -S base-devel gcc git make
```

### 步骤 3: 下载 Valkey 源码

使用 git 下载 Valkey 源码。

```bash
git clone https://github.com/valkey-io/Valkey.git
cd Valkey
```

### 步骤 4: 编译 Valkey

在 Valkey 源码目录下，执行 make 命令进行编译。

```bash
make
```

### 步骤 5: 安装 Valkey

编译完成后，执行 make install 命令安装 Valkey 到系统。

```bash
sudo make install
```

## 直接安装 Valkey (替代 Redis)

**注意:**  Valkey 将会取代 `[extra]` 仓库中的 Redis。如果您之前安装了 Redis，Valkey 将会替换它。

您可以使用以下命令直接安装 Valkey：

```bash
sudo pacman -S valkey
```

安装完成后，您可以启动 Valkey 服务：

```bash
sudo systemctl enable valkey
sudo systemctl start valkey
```


### 步骤 6: 配置 Valkey

Valkey 的配置文件位于 `/usr/local/etc/valkey.conf`。您可以根据需要修改配置文件。

```bash
sudo cp /usr/local/etc/valkey.conf /etc/valkey.conf
sudo nano /etc/valkey.conf
```

### 步骤 7: 启动 Valkey

启动 Valkey 服务。

```bash
valkey-server /etc/valkey.conf
```

您可以使用 `valkey-cli` 连接到 Valkey 服务器进行测试。

```bash
valkey-cli ping
```

至此，您已成功在 Arch Linux 上安装并启动了 Valkey。

<!-- 请在此处撰写文章内容 -->