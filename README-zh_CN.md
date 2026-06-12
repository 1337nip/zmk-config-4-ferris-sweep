# NXTKB Ferris Sweep ZMK 配置

[![固件构建](https://img.shields.io/github/actions/workflow/status/nxtkb/zmk-config-4-ferris-sweep/build.yml?branch=main&label=firmware%20build&style=flat-square)](https://github.com/nxtkb/zmk-config-4-ferris-sweep/actions/workflows/build.yml)
[![文档状态](https://img.shields.io/website?url=https%3A%2F%2Fnxtkb.com%2Fzh%2Fdocs%2Fsetup%2Fkeymap%2Fferris-sweep-keymap%2F&label=docs&up_message=online&up_color=2f6f6f&down_message=offline&down_color=8b1e3f&style=flat-square)](https://nxtkb.com/zh/docs/setup/keymap/ferris-sweep-keymap/)
[![键位源码](https://img.shields.io/badge/keymap-cradio.keymap-5f6fbf?style=flat-square)](./config/cradio.keymap)
[![ZMK 配置](https://img.shields.io/badge/ZMK-cradio.conf-6b7280?style=flat-square)](./config/cradio.conf)

中文 | [English](./README.md)

这个仓库保存 NXTKB Ferris Sweep 的 ZMK 固件配置。需要查看源码、fork
配置或构建固件时，从这里开始；上手、刷写、键位图和日常使用说明，优先看
NXTKB 官方文档。

## 官方文档

- [入门指南](https://nxtkb.com/zh/docs/setup/)
- [Ferris Sweep 键位映射](https://nxtkb.com/zh/docs/setup/keymap/ferris-sweep-keymap/)
- [Ferris Sweep 配置文件](https://nxtkb.com/zh/docs/firmware/ferris-sweep-configuration/)
- [如何更新键位映射](https://nxtkb.com/zh/docs/setup/keymap/how-to-update-keymaps/)
- [如何刷写固件](https://nxtkb.com/zh/docs/firmware/how-to-flash-a-firmware/)
- [键鼠测试](https://nxtkb.com/zh/docs/setup/keymap/input-tester/)

英文文档也可直接访问：

- [Getting Started](https://nxtkb.com/docs/setup/)
- [Ferris Sweep Keymap](https://nxtkb.com/docs/setup/keymap/ferris-sweep-keymap/)
- [Ferris Sweep Configuration](https://nxtkb.com/docs/firmware/ferris-sweep-configuration/)

## 仓库结构

- `config/cradio.keymap`：层、按键绑定、本位行修饰键、条件三层、鼠标层、
  Boot 键、软关机行为和 ZMK Studio 解锁。
- `config/cradio.conf`：这个键盘的 ZMK 配置选项。
- `build.yaml`：GitHub Actions 固件构建矩阵。
- `.github/workflows/build.yml`：复用 ZMK 用户配置构建流程的固件构建工作流。

## 固件和改键流程

如果要做长期保留的配置修改：

1. Fork 这个仓库。
2. 修改 `config/cradio.keymap` 或 `config/cradio.conf`。
3. 等待 GitHub Actions 构建固件。
4. 下载构建产物，把对应 UF2 固件刷到对应半边键盘。

如果当前固件支持 ZMK Studio，日常键位的快速调整优先使用
[ZMK Studio](https://zmk.studio/)。
完整取舍请看官网的
[如何更新键位映射](https://nxtkb.com/zh/docs/setup/keymap/how-to-update-keymaps/)。

## 键位摘要

完整键位图和逐层说明请看官网：

- [Ferris Sweep 键位映射](https://nxtkb.com/zh/docs/setup/keymap/ferris-sweep-keymap/)
- [Ferris Sweep Keymap](https://nxtkb.com/docs/setup/keymap/ferris-sweep-keymap/)
- [在 keymap-drawer 查看最新键位](https://keymap-drawer.streamlit.app/?zmk_url=https%3A%2F%2Fgithub.com%2Fnxtkb%2Fzmk-config-4-ferris-sweep%2Fblob%2Fmain%2Fconfig%2Fcradio.keymap)

当前默认层级：

- 默认层 / Windows 层：输入字符，并在本位行放置修饰键。
- 数字和导航层：按住右侧 `TAB` 层键进入。
- 符号层：按住左侧 `TAB` 层键进入。
- 功能层：同时按住左右 `TAB` 层键进入，用于蓝牙档位、输出切换、
  Windows 层切换、ZMK Studio 解锁和软关机。
- 鼠标层：在符号层按 `SPACE` 进入，按 `P` 或 `Q` 退出。

## Bootloader 和刷写提示

进入 bootloader 可任选一种方法：

1. 键盘已连接时，按键位里的 `Boot` 键。
2. 双击 reset 按钮。
3. 如果 reset 按钮不可用，短接 `RST` 和 `GND` 两次。

固件文件名通常会标明目标：

- `left`：左手固件。
- `right`：右手固件。
- `reset`：清除蓝牙配对信息的 reset 固件。

如果只改了按键或键盘名称，通常只需要刷左手。如果改到分体行为、板级配置或
右手行为，也要刷受影响的半边。刷写前请先看官网的
[如何刷写固件](https://nxtkb.com/zh/docs/firmware/how-to-flash-a-firmware/)。

## 参考

- [Sweep](https://github.com/davidphilipbarr/Sweep)
- [ZMK](https://github.com/zmkfirmware/zmk)
- [ZMK Studio 文档](https://zmk.dev/docs/features/studio)
