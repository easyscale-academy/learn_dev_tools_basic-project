# Mac 本地开发环境快速搭建

## 📋 本节目标

- 在 Mac 上安装三个核心工具：VS Code、Ghostty、GitHub Desktop
- 理解 User Folder 的概念，建立合理的项目文件夹结构
- 从 GitHub Codespace 过渡到本地开发

## 🎯 为什么要学这个？

恭喜你完成了 mise 的安装！你现在已经拥有了一个"万能遥控器"来管理开发工具。

还记得之前我们一直在用 GitHub Codespace 吗？Codespace 很棒——它就像一个云端的"一次性工作间"，你可以放心大胆地折腾，搞砸了大不了删掉重来。对于刚开始学习的你来说，这是一个非常安全的练习场。

但现在，你已经学会了 mise。有了 mise，你在本地电脑上安装和管理开发工具变得又简单又安全——因为 mise 会帮你把所有工具都管理得井井有条，不会把你的系统搞乱。所以现在是时候把"主战场"搬回你自己的 Mac 了。

**本地开发的好处很明显：**

- 速度快——不用等 Codespace 启动，打开电脑就能干活
- 文件就在你电脑上，随时可以找到
- 不受网络影响，断网了照样写代码
- 不用担心 Codespace 的免费时长用完

当然，Codespace 你以后还是可以继续用的。当你想尝试一些新东西、又不想影响本地环境的时候，开一个 Codespace 练练手，仍然是个很好的选择。

**所以我们的策略是：日常开发用本地，探索新东西用 Codespace。**

那本地开发需要哪些工具呢？其实就三样东西：一个代码编辑器、一个终端、一个 Git 管理工具。我们一个个来装。

## 🛠️ 工具一：VS Code（代码编辑器）

VS Code（全称 Visual Studio Code）是目前最流行的代码编辑器。如果你之前学过我们的 GitHub 教程，你应该已经见过它了——没错，GitHub Codespace 里面用的就是网页版的 VS Code。

现在我们要在你的 Mac 上装一个本地版。

**安装方法：**

1. 打开浏览器，访问 https://code.visualstudio.com
2. 点击那个大大的 Download 按钮，下载 Mac 版
3. 下载完成后，打开 ``.dmg`` 文件，把 VS Code 拖到 Applications 文件夹里
4. 去 Applications 文件夹里双击打开 VS Code

就这样，装好了。

你会发现本地的 VS Code 界面和 Codespace 里的几乎一模一样。以后你用它来打开项目文件夹、编辑代码，和在 Codespace 里的体验是一样的。

## 🛠️ 工具二：Ghostty（终端）

终端（Terminal）就是你输入命令的那个黑色窗口。Mac 自带了一个叫 "Terminal" 的应用，能用，但界面比较朴素。

如果你想要一个颜值更高、体验更好的终端，我推荐 **Ghostty**。它速度快、界面好看，而且完全免费。

> 当然，如果你觉得系统自带的 Terminal 够用了，完全可以跳过这一步，直接用自带的。

**安装方法：**

1. 打开浏览器，访问 https://ghostty.org
2. 下载 Mac 版本
3. 下载完成后，打开 ``.dmg`` 文件，把 Ghostty 拖到 Applications 文件夹里
4. 去 Applications 文件夹里双击打开 Ghostty

打开后你会看到一个简洁好看的终端窗口。试着输入 ``mise`` 看看——如果你之前在 Mac 上已经装好了 mise，这里应该能看到 mise 的帮助信息。

以后不管是用 mise 安装工具，还是运行 Python、Claude Code 这些命令，都可以在这个终端里操作。

## 🛠️ 工具三：GitHub Desktop（Git 管理工具）

如果你学过我们之前的 GitHub 教程，你应该对 GitHub Desktop 不陌生了。它是一个图形界面的 Git 管理工具，让你不用记 Git 命令，点点鼠标就能管理代码的版本。

**安装方法：**

1. 打开浏览器，访问 https://desktop.github.com/download/
2. 下载 Mac 版本
3. 下载完成后，安装并打开
4. 用你的 GitHub 账号登录

装好以后，你就可以用它来 clone（下载）GitHub 上的项目到本地，也可以把本地的修改同步回 GitHub。

## 📁 关于 User Folder：你的文件都放在哪？

在我们开始用这些工具之前，先聊一个基础概念——**User Folder（用户文件夹）**。

打开 Mac 的 Finder（访达），你会在左边栏看到一些常见的文件夹：Documents（文稿）、Downloads（下载）、Desktop（桌面）等等。这些文件夹都在一个地方，叫做你的 **User Folder**（用户文件夹）。

为什么叫"用户文件夹"呢？因为电脑在设计上假设可能有多个人使用同一台电脑，每个人都是一个"用户"（User），每个用户有自己独立的文件夹来存放各自的东西。只不过你的个人电脑一般只有你一个人用，所以你可能只看到一个用户。

你的 User Folder 在 Mac 上的路径是：

```
/Users/你的用户名/
```

比如你的用户名是 ``alice``，那就是 ``/Users/alice/``。你的 Documents、Downloads 这些，其实就是 ``/Users/alice/Documents``、``/Users/alice/Downloads``。

## 📂 建议的项目文件夹结构

知道了 User Folder 的概念后，我建议你在 Documents 下面（或者直接在 User Folder 下面）创建一个叫 ``GitHub`` 的文件夹，专门用来存放你从 GitHub 上 clone 下来的项目。

```
/Users/你的用户名/
├── Documents/
│   └── GitHub/           ← 专门放 Git 项目的文件夹
│       ├── project-a/    ← 一个 Git 项目
│       ├── project-b/    ← 另一个 Git 项目
│       └── learn-xxx/    ← 又一个 Git 项目
├── Downloads/
├── Desktop/
└── ...
```

**每个子文件夹就是一个 Git 仓库（repo）。** 这样组织起来很清爽——你所有的项目都在一个地方，一目了然。

用 GitHub Desktop clone 项目的时候，它会问你要把项目放在哪里，你就选这个 ``GitHub`` 文件夹就好了。

## 🔮 接下来用 mise 装什么？

现在你的 Mac 上已经有了三件套：VS Code 写代码、Ghostty（或 Terminal）跑命令、GitHub Desktop 管理项目。

接下来我们的课程会用到 Python 和 Claude Code（AI 编程助手）。这些都可以用 mise 来安装！还记得 mise 的安装命令吗？就是这么简单：

```
mise use python@3.12
mise use npm:@anthropic-ai/claude-code
```

分分钟就在你的电脑上跑起来。这就是 mise 的魅力——那些看起来高大上的"黑科技"工具，有了 mise 以后，一行命令就搞定。

## 👨‍🏫 导师寄语：从"借别人的厨房"到"自己的工作台"

之前用 Codespace，就像在别人的厨房里做饭——食材和工具都是现成的，但毕竟不是自己的地方，用完还得收拾走人。

现在你在自己的 Mac 上搭好了开发环境，这就是你自己的工作台了。VS Code 是你的切菜板，终端是你的灶台，GitHub Desktop 是你的储物柜，而 mise 是帮你管理所有厨具的助手。

这套组合你会一直用下去。不管以后学 Python、学 AI、做项目，打开电脑就能开始干活。

**刚开始可能会觉得：在本地装这些东西会不会搞乱我的电脑？** 放心，有了 mise，你的工具都被管理得整整齐齐。mise 就是专门干这个的——让你的开发环境"准备就绪"（mise en place），而不是一团乱麻。

你已经从一个"借厨房的新手"变成了"有自己工作台的开发者"。这是一个重要的里程碑，接下来的旅程会越来越有趣！

## ✅ 完成检查清单

- [ ] 安装 VS Code 并成功打开
- [ ] 安装 Ghostty（或确认使用系统自带 Terminal）
- [ ] 安装 GitHub Desktop 并登录 GitHub 账号
- [ ] 在 Documents 下创建 ``GitHub`` 文件夹
- [ ] 在终端里输入 ``mise``，确认 mise 可以正常工作

## 💡 关键要点总结

1. **日常开发用本地，探索新东西用 Codespace** - 两者互补，各有所长
2. **三件套：VS Code + Ghostty + GitHub Desktop** - 代码编辑、命令行、项目管理，一套搞定
3. **在 Documents/GitHub/ 下统一管理项目** - 每个子文件夹就是一个 Git 仓库
4. **mise 管理开发工具** - Python、Claude Code 等，一行命令安装，不会搞乱系统
5. **User Folder 是你在电脑上的"家"** - 所有个人文件都在 ``/Users/你的用户名/`` 下面
