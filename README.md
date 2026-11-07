<div align="center">

  <img src="./assets/banner.svg" width="100%" alt="Nyarch Linux Guide Banner"/>

  <br><br>

  <p align="center">
    <img src="https://img.shields.io/badge/Distro-Nyarch_Linux-1793d1?style=for-the-badge&logo=arch-linux&logoColor=white" />
    <img src="https://img.shields.io/badge/Desktop-GNOME_to_Niri-FF69B4?style=for-the-badge&logo=gnome&logoColor=white" />
    <img src="https://img.shields.io/badge/Shell-Fish_%2B_Starship-008080?style=for-the-badge&logo=gnubash&logoColor=white" />
    <img src="https://img.shields.io/badge/Tribute-To_SHORiN--KiWATA-8A2BE2?style=for-the-badge&logo=github&logoColor=white" />
    <img src="https://img.shields.io/badge/Aesthetic-Anime%20%26%20Loli%20Style-ffb6c1?style=for-the-badge&logo=safari&logoColor=white" />
  </p>

  <p align="center">
    <i>🌸 献给所有热爱二次元、追求极客桌面美学与极致生产力的 Linux 玩家 🌸</i>
    <br>
    <sub>“代码可以严谨，但桌面一定要可爱！愿这份热爱在开源世界薪火相传。”</sub>
  </p>

</div>

---

## 📑 目录 (Table of Contents)

- [🌸 前言：这份指南的初心与热爱](#-前言这份指南的初心与热爱)
- [🌐 核心资源与官方下载导航](#-核心资源与官方下载导航)
- [🐾 Nyarch Linux 萌新入坑入门篇](#-nyarch-linux-萌新入坑入门篇)
- [🪟 从 GNOME 开始深度挖掘与调校](#-从-gnome-开始深度挖掘与调校)
- [🌀 进阶蜕变：走向 Niri 卷轴美学（致敬 Shorin 大老师）](#-进阶蜕变走向-niri-卷轴美学致敬-shorin-大老师)
- [🎮 二次元玩家的实战生态与避坑心法](#-二次元玩家的实战生态与避坑心法)
- [💖 结语：开源精神与热爱的传承](#-结语开源精神与热爱的传承)

---

## 🌸 前言：这份指南的初心与热爱

许多朋友在听说 **Arch Linux** 时，脑海里往往是黑乎乎的 tty 纯命令行、冷冰冰的代码或者极其繁琐的安装过程。

但当我们遇见了 **Nyarch Linux**，一切都变了——它以 Arch Linux 的强悍滚动更新与庞大 AUR 生态为底座，同时注入了**专属于二次元爱好者的灵魂**：开箱即用的萌系配色、二次元壁纸与终端字符画、丝滑的现代桌面。

这篇指南记录了我从一个萌新小白，在 Nyarch Linux 上一步一步从 **GNOME 深度挖掘**、到**调教出独一无二的 Material You 动态美学**、再到**吸收 Shorin 大老师的 Niri 卷轴架构**的全过程。

**不为别的，只为给每一个来到 Linux 世界的二次元同好一份温暖的热爱，并将这份开源探索的浪漫传承下去！** ✨

---

## 🌐 核心资源与官方下载导航

在折腾之前，请认准官方正版站点与社区源，避免迷路：

### 1. Nyarch Linux 官方阵地
- 🐾 **官方网站**: [https://nyarchlinux.moe/](https://nyarchlinux.moe/) *(二次元风格满满的官网)*
- 🐱 **GitHub 官方组织**: [https://github.com/NyarchLinux](https://github.com/NyarchLinux)
- 📥 **镜像下载页面 (ISO)**: 
  - [SourceForge 镜像发布页](https://sourceforge.net/projects/nyarchlinux/)
  - [GitHub Releases 镜像页](https://github.com/NyarchLinux/NyarchLinux/releases)

### 2. Arch Linux 上游基石网站
- 🐧 **Arch Linux 官方主站**: [https://archlinux.org/](https://archlinux.org/)
- 📖 **ArchWiki 官方中文文档**: [https://wiki.archlinux.org/title/Main_page_(简体中文)](https://wiki.archlinux.org/title/Main_page_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)) *(Linux 界的最强百科全书)*
- 📦 **AUR (Arch 用户软件仓库)**: [https://aur.archlinux.org/](https://aur.archlinux.org/)
- 🚀 **国内高速镜像站 (Pacman)**:
  - [清华大学开源软件镜像站 (TUNA)](https://mirrors.tuna.tsinghua.edu.cn/archlinux/)
  - [中国科学技术大学开源镜像站 (USTC)](https://mirrors.ustc.edu.cn/archlinux/)

---

## 🐾 Nyarch Linux 萌新入坑入门篇

### 1. 为什么是 Nyarch？
传统 Arch Linux 安装需要手动分区、配置引导、安装基础包，对新手极具门槛。而 Nyarch Linux：
- 自带美观易用的 Calamares 图形化安装器；
- 预装了中文语言包、二次元字体与预调教的桌面主题；
- 兼具 Arch 的全部灵活性：包管理器依然是纯正的 `pacman`，全网海量软件依然一键 `yay`。

### 2. 初次启动后的三步曲
安装完成后，在终端中跑这三步即可快速进入状态：

```bash
# 1. 测速并更新国内镜像源
sudo pacman-mirrors -i -c China -m rank  # 或更新 /etc/pacman.d/mirrorlist

# 2. 全量滚包升级系统
sudo pacman -Syu

# 3. 安装常用的 AUR 包管理助手 (推荐 yay 或 paru)
sudo pacman -S --needed base-devel git
git clone https://aur.archlinux.org/yay.git && cd yay && makepkg -si
```

---

## 🪟 从 GNOME 开始深度挖掘与调校

很多二次元新手刚进系统时，看到的第一个桌面就是 **GNOME Shell**。GNOME 并不是一个简单的“开箱即用桌面”，它的可挖掘潜力深不见底：

### 1. Material You 动态色彩提取系统
Nyarch 的一大神技是：**换一张壁纸，整个系统桌面和图标都会自动跟着壁纸变色！**
在 `~/.config/nyarch/after_wp_change.sh` 脚本中，系统会监听壁纸切换：
- 自动提取壁纸中的主色调（Accent Color）；
- 动态重编译生成 `~/.config/gtk-4.0/gtk.css`；
- 实时重新渲染并加载 **Tela-circle-MaterialYou** 图标主题！

> 💡 **调校经验**：如果你放了一张可爱的粉色萝莉壁纸，整个文件夹、选中高亮、终端光标都会瞬间变成梦幻的樱花粉色！

### 2. GNOME 下的二次元美化组合拳
- **图标包**: `Tela-circle-icon-theme`（圆润柔和，完美搭配 Material 动态取色）；
- **终端神器**:
  - `Fastfetch`：配置二次元字符画与萌娘 Logo，打开终端就是满满的心动；
  - `Starship`：配置彩色渐变 Powerline 提示符，显示 Git 分支、时间、系统状态；
  - `Fish Shell`：告别 Bash 的呆板，自带语法高亮与智能补全。

---

## 🌀 进阶蜕变：走向 Niri 卷轴美学（致敬 Shorin 大老师）

当你玩熟了 GNOME，渴望更极致的键盘流极客效率与无边界桌面时，**Niri 卷轴窗口管理器** 就是终极答案。

### 💖 致敬：感谢导师 SHORiN-KiWATA（Shorin 大老师）
在此必须由衷地致敬国内 Arch 圈的极客前辈 **[@SHORiN-KiWATA](https://github.com/SHORiN-KiWATA)**（Shorin 大老师）！

> **致谢声明**：  
> 本人当前系统深度依赖的 **Niri 卷轴窗口规则配置 (`shorin-windowrules.kdl`)** 与 **Dank Material Shell (DMS) 材质外壳体系**，正是深度套用并借鉴了大老师的开源心血。大老师在 Wayland 桌面平铺、窗口吸附、国内软件防撕裂等领域的探索，为广大中文 Linux 爱好者照亮了前路！

### 1. 为什么是 Niri 卷轴平铺？
- **传统平铺 (i3 / Hyprland)**：屏幕切成一个个小格子，窗口越多格子越小；
- **Niri 卷轴式 (Scrollable Tiling)**：窗口横向无限延伸！就像展开一幅二次元长卷轴，按 <kbd>Super</kbd> + <kbd>H/L</kbd> 丝滑平移，每个应用都保留最舒适的浏览宽度！

### 2. 我的 Niri 核心配置结构
在我的开源配置库 [`shenchuchu91-hub/dotfiles`](https://github.com/shenchuchu91-hub/dotfiles) 中：
- `~/.config/niri/config.kdl`：核心窗口管理与快捷键映射
- `~/.config/niri/layout.kdl`：间隙与卷轴比例控制
- `~/.config/niri/animations.kdl`：如丝般顺滑的弹簧果冻动画
- `~/.config/niri/blur.kdl`：背景高斯模糊与毛玻璃透明特效
- `~/.config/niri/shorin-windowrules.kdl`：针对国内各类软件（QQ、微信、播放器）的浮动/平铺智能过滤规则！

---

## 🎮 二次元玩家的实战生态与避坑心法

玩 Linux 绝不能耽误玩游戏和日常看番：

1. **混合显卡（核显+独显）防偷跑**：
   - 游戏本（如 HP Victus + RTX 5060）如果不用特定环境变量，默认会傻傻地用核显跑游戏。
   - 使用我制作的开源工具 [`moe-game-launcher`](https://github.com/shenchuchu91-hub/moe-game-launcher)，输入 `moe 游戏.exe` 即可自动绑定 5060 满血渲染并开启 144Hz 锁帧与 FSR 锐化！
2. **Wayland 下的输入法光标跟随**：
   - 使用 `fcitx5` + `fcitx5-chinese-addons`，在环境配置中加上 `XMODIFIERS=@im=fcitx` 与 `GTK_IM_MODULE=fcitx`。
3. **二次元小黄鸭补帧 (LSFG)**：
   - 终端里配置 `abbr lsfg 'LSFG_PROCESS="miyu"'`，开启高帧率丝滑二次元动态视觉！

---

## 💖 结语：开源精神与热爱的传承

Shorin 大老师用他的教程和工具带了无数新手入门，而今天，我把我在 Nyarch Linux 上的摸索、调教和配置毫无保留地整理出来。

**开源的真正魅力，从来不是一个人走得有多远，而是把点燃的火把递给下一个同样热爱的人。**

如果你也是一位热爱二次元、喜欢萌系美化、并渴望在 Linux 上拥有一片属于自己纯净世界的探索者：
欢迎来到 Nyarch 的乐园！✨

---

<div align="center">

🌸 **相关开源仓库** 🌸  
[Dotfiles 桌面配置](https://github.com/shenchuchu91-hub/dotfiles) · [Moe Game Launcher 游戏启动器](https://github.com/shenchuchu91-hub/moe-game-launcher) · [一键拉取命令库](https://github.com/shenchuchu91-hub/linux)

<sub>Made with 💖 by <b>shenchuchu91-hub</b> · 致敬所有为 Linux 社区贡献热爱的开发者</sub>

</div>
