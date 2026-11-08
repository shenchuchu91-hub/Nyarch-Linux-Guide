<div align="center">

  <img src="./assets/banner.svg" width="100%" alt="Nyarch Linux Guide Banner"/>

  <br><br>

  <p align="center">
    <img src="https://img.shields.io/badge/Distro-Nyarch_Linux-1793d1?style=for-the-badge&logo=arch-linux&logoColor=white" />
    <img src="https://img.shields.io/badge/Desktop-GNOME_to_Niri-FF69B4?style=for-the-badge&logo=gnome&logoColor=white" />
    <img src="https://img.shields.io/badge/Shell-Fish_%2B_Starship-008080?style=for-the-badge&logo=gnubash&logoColor=white" />
    <img src="https://img.shields.io/badge/Tribute-To_SHORiN--KiWATA-8A2BE2?style=for-the-badge&logo=github&logoColor=white" />
    <img src="https://img.shields.io/badge/Aesthetic-Anime%20%26%20Moe-ffb6c1?style=for-the-badge" />
  </p>

  <p align="center">
    <i>面向二次元爱好者的 Nyarch Linux 环境配置、GNOME 动态调色与 Niri 卷轴平铺窗口管理器实践指南</i>
  </p>

</div>

---

## 📑 目录 (Table of Contents)

- [🌸 前言与背景 (Overview)](#-前言与背景-overview)
- [🌐 核心资源与官方下载导航 (Resources)](#-核心资源与官方下载导航-resources)
- [🐾 Nyarch Linux 基础入门篇 (Getting Started)](#-nyarch-linux-基础入门篇-getting-started)
- [🪟 GNOME 桌面环境调校与动态配色 (GNOME & Material You)](#-gnome-桌面环境调校与动态配色-gnome--material-you)
- [🌀 进阶：Niri 卷轴平铺窗口管理器实践 (Niri WM & Tribute)](#-进阶niri-卷轴平铺窗口管理器实践-niri-wm--tribute)
- [🎮 游戏与日常生态调优 (Gaming & Desktop Practices)](#-游戏与日常生态调优-gaming--desktop-practices)
- [💖 结语与开源传承 (Conclusion)](#-结语与开源传承-conclusion)

---

## 🌸 前言与背景 (Overview)

Arch Linux 以滚动更新与丰富的 AUR 生态著称，而 **Nyarch Linux** 则在此基石上预置了开箱即用的二次元主题、中文字体与现代桌面配置，兼顾美观性与实用度。

本文档系统性梳理了从 Nyarch 官方镜像安装、GNOME Material You 动态调色逻辑、到进阶迁移至 Niri 卷轴平铺窗口管理器的完整流程，旨在为喜爱二次元桌面风格的 Linux 探索者提供一份条理清晰、可复现的参考文档。

---

## 🌐 核心资源与官方下载导航 (Resources)

部署前请认准官方正版站点与镜像源：

### 1. Nyarch Linux 官方站点
- 🐾 **官方网站**: [https://nyarchlinux.moe/](https://nyarchlinux.moe/)
- 🐱 **GitHub 组织**: [https://github.com/NyarchLinux](https://github.com/NyarchLinux)
- 📥 **镜像下载 (ISO)**: 
  - [SourceForge 镜像发布页](https://sourceforge.net/projects/nyarchlinux/)
  - [GitHub Releases 镜像页](https://github.com/NyarchLinux/NyarchLinux/releases)

### 2. Arch Linux 上游基石
- 🐧 **Arch Linux 官方主站**: [https://archlinux.org/](https://archlinux.org/)
- 📖 **ArchWiki 官方中文文档**: [https://wiki.archlinux.org/title/Main_page_(简体中文)](https://wiki.archlinux.org/title/Main_page_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))
- 📦 **AUR (Arch 用户软件仓库)**: [https://aur.archlinux.org/](https://aur.archlinux.org/)
- 🚀 **国内常用镜像站**:
  - [清华大学开源镜像站 (TUNA)](https://mirrors.tuna.tsinghua.edu.cn/archlinux/)
  - [中国科学技术大学开源镜像站 (USTC)](https://mirrors.ustc.edu.cn/archlinux/)

---

## 🐾 Nyarch Linux 基础入门篇 (Getting Started)

### 1. 发行版特性
- 搭载 Calamares 图形化安装程序，简化基础安装流程；
- 预装中文语言包、开源中文字体与预调教桌面主题；
- 继承纯正 Arch 架构：底层包管理器为 `pacman`，无缝使用全部 AUR 软件生态。

### 2. 初次启动后的基础配置
安装完成后，建议在终端中执行以下步骤：

```bash
# 1. 测速并更新国内镜像源
sudo pacman-mirrors -i -c China -m rank  # 或编辑 /etc/pacman.d/mirrorlist

# 2. 更新系统软件包
sudo pacman -Syu

# 3. 安装常用的 AUR 助手 (推荐 yay 或 paru)
sudo pacman -S --needed base-devel git
git clone https://aur.archlinux.org/yay.git && cd yay && makepkg -si
```

---

## 🪟 GNOME 桌面环境调校与动态配色 (GNOME & Material You)

Nyarch Linux 默认提供的桌面会话之一为 **GNOME Shell**。其在视觉上的核心特性为动态色彩提取：

### 1. Material You 动态色彩提取机制
Nyarch 通过监听壁纸切换事件（`~/.config/nyarch/after_wp_change.sh`）：
- 提取当前壁纸的主题基色（Accent Color）；
- 动态编译生成 `~/.config/gtk-4.0/gtk.css`；
- 实时重载 **Tela-circle-MaterialYou** 图标主题，使窗口控件与壁纸色系保持视觉协调。

### 2. 常用美化组件推荐
- **图标主题**: `Tela-circle-icon-theme`（圆润柔和，配合动态色彩效果良好）；
- **终端环境**:
  - `Fastfetch`：配置二次元字符画与系统信息显示；
  - `Starship`：跨 Shell 的渐变色彩 Powerline 提示符；
  - `Fish Shell`：开箱即用的语法高亮与智能补全。

---

## 🌀 进阶：Niri 卷轴平铺窗口管理器实践 (Niri WM & Tribute)

当对键盘流平铺与多任务效率有更高要求时，**Niri 卷轴式平铺窗口管理器** 是一种现代且优雅的 Wayland 解决方案。

### 💖 致敬与致谢：SHORiN-KiWATA（Shorin 大老师）
在探索 Niri 卷轴窗口管理器与 Material 材质外壳的过程中，深深受惠于国内 Arch 社区开发者 **[@SHORiN-KiWATA](https://github.com/SHORiN-KiWATA)**（Shorin 大老师）的开源项目。  
本人的 Niri 窗口过滤规则 (`shorin-windowrules.kdl`) 与部分桌面外壳配置借鉴了其前期的开源探索。感谢大老师对中文 Linux 桌面社区的无私奉献与启发！

### 1. Niri 卷轴式平铺的核心机制
- **传统平铺 (i3 / Hyprland)**：按屏幕网格固定切分，窗口增多时单个视口变窄；
- **Niri 卷轴式 (Scrollable Tiling)**：窗口横向无限排列，通过 <kbd>Super</kbd> + <kbd>H/L</kbd> 水平平移浏览，各应用始终保持设定的最佳阅读宽度。

### 2. 配置结构参考
在开源配置库 [`shenchuchu91-hub/dotfiles`](https://github.com/shenchuchu91-hub/dotfiles) 中：
- `~/.config/niri/config.kdl`：核心窗口管理与按键映射
- `~/.config/niri/layout.kdl`：间隙与卷轴比例控制
- `~/.config/niri/animations.kdl`：平移动画与弹簧曲线
- `~/.config/niri/blur.kdl`：毛玻璃模糊与窗口透明度
- `~/.config/niri/shorin-windowrules.kdl`：常见国产软件（QQ、微信、媒体播放器）的浮动/平铺智能过滤规则

---

## 🎮 游戏与日常生态调优 (Gaming & Desktop Practices)

1. **混合显卡笔记本调度**：
   - 搭载 NVIDIA 独显的双显卡设备在运行游戏时需显式注入 Prime 变量。
   - 可参考自研工具 [`moe-game-launcher`](https://github.com/shenchuchu91-hub/moe-game-launcher)，便捷指定独立显卡渲染并开启 144Hz 锁帧。
2. **Wayland 下的中文输入法支持**：
   - 安装 `fcitx5` + `fcitx5-chinese-addons`，在全局环境中配置 `XMODIFIERS=@im=fcitx` 与 `GTK_IM_MODULE=fcitx`。
3. **高帧率与平滑视觉**：
   - 支持根据屏幕原生刷新率（如 1080p @ 144Hz）配置 Gamescope 目标帧率，保证游戏过程中的输入响应速度。

---

## 💖 结语与开源传承 (Conclusion)

开源社区的魅力在于经验的共享与沉淀。希望这份梳理能为同样喜爱二次元美化与 Wayland 桌面探索的同好提供切实的帮助。

欢迎提出建议与反馈！✨

---

<div align="center">

🌸 **相关开源仓库与规范** 🌸  
[Dotfiles 桌面配置](https://github.com/shenchuchu91-hub/dotfiles) · [Moe Game Launcher 游戏启动器](https://github.com/shenchuchu91-hub/moe-game-launcher) · [一键拉取命令库](https://github.com/shenchuchu91-hub/linux) · [全局免责与安全规范](https://github.com/shenchuchu91-hub/disclaimer)

<sub>Made with 💖 by <b>shenchuchu91-hub</b></sub>

</div>
