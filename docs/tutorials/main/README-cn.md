# 安装 mise：你的开发工具管理总管家

## 📋 本节目标

- 理解 mise 是什么、为什么需要它
- 在 GitHub Codespace 中完成 mise 的安装
- 验证安装成功

## 🎯 为什么要学这个？

想象一下，你刚入职一家科技公司，准备开始写代码。结果发现：

- Python 项目需要 Python 3.11
- Node.js 项目需要 Node 20
- 另一个老项目需要 Python 3.9
- 还得装 Claude CLI 来用 AI 辅助开发……

怎么办？一个个去官网下载安装？版本冲突了怎么切换？每个工具的管理方式还都不一样？

这就像家里的遥控器越来越多——电视一个、空调一个、音响一个、投影仪一个……最后你需要一个"万能遥控器"来统一管理它们。

**mise 就是开发工具界的"万能遥控器"。**

有了 mise，你只需要学会一套命令，就能安装、切换、管理几乎所有开发工具：Python、Node.js、Go、Rust、Claude CLI……一个工具搞定全部。

## 📖 mise 是什么？

mise（发音类似 "meez"，来自法语烹饪术语 "mise en place"，意为"准备就绪"）是一个**开发环境管理工具**。

简单来说，它是"管理其他开发工具的工具"。传统上，不同的编程语言和工具有各自的版本管理器：

- Python 有 pyenv、uv
- Node.js 有 nvm、fnm
- Ruby 有 rbenv
- 各种 CLI 工具有 npm、pipx……

而 mise 把这些全部统一了。你不再需要学习五六个不同的工具，只需要掌握 mise 这一个。

> **为什么起这个名字？** "Mise en place" 是专业厨房里的基本原则：在开始烹饪之前，把所有食材、工具都准备好、摆放整齐。mise 这个工具的理念也是一样——让你的开发环境在开始工作前就"准备就绪"。

## 📝 前置知识提示

本教程假设你：

- 会使用 GitHub Codespace（能打开、使用、删除）
- 会在 Terminal 里输入命令并按回车执行
- 理解"复制粘贴"操作

不需要了解 Linux、bash 或任何编程知识。

## 💻 实战：在 Codespace 中安装 mise

整个安装过程只需要三步，我们一步步来。

### 第一步：确认当前没有 mise

首先，打开你的 GitHub Codespace 的 Terminal（终端）。

在 Terminal 里输入：

```
mise
```

因为这是一台"新电脑"（新的 Codespace），肯定没有安装过 mise，所以你会看到这样的错误信息：

```
bash: mise: command not found
```

这是正常的！说明我们确实需要安装它。

### 第二步：运行安装命令

Codespace 是 Linux 环境。根据 [mise 官方文档](https://mise.jdx.dev/getting-started.html)，Linux 的安装命令是：

```
curl https://mise.run | sh
```

> **小知识：** `` curl `` 是一个下载工具，这行命令的意思是"从 mise.run 这个网址下载安装脚本，然后运行它"。

复制上面的命令，粘贴到 Terminal，按回车。你会看到类似这样的输出：

```shell
mise: installing mise...
######################################################################## 100.0%
mise: installed successfully to /home/codespace/.local/bin/mise
mise: run the following to activate mise in your shell:
echo "eval \"$(/home/codespace/.local/bin/mise activate bash)\"" >> ~/.bashrc

mise: run `mise doctor` to verify this is setup correctly
```

安装成功了！但还没完——注意看输出里有一行很重要的提示，以 `` echo `` 开头的那行。

### 第三步：让 mise 每次自动启动

这是最关键的一步，很多人会漏掉。

你看到的那行 `` echo "eval ..." `` 命令，是 mise 告诉你："如果你想每次打开 Terminal 都能直接用 mise，请把我的启动命令添加到你的启动脚本里。"

**先复制粘贴执行它！** 完整的命令长这样（你的可能略有不同，以你屏幕上显示的为准）：

```
echo "eval \"$(/home/codespace/.local/bin/mise activate bash)\"" >> ~/.bashrc
```

**这行命令在做什么？**

让我用一个比喻解释：

- `` ~/.bashrc `` 是一个"开机自动运行脚本"。每次你打开 Terminal（或输入 `` bash `` 重新进入 bash），系统都会自动执行这个脚本里的所有命令
- `` eval "$(...mise activate bash)" `` 是 mise 的"启动命令"，不运行这个，mise 就像睡着了一样无法使用
- `` echo "..." >> ~/.bashrc `` 的意思是"把引号里的内容添加到 ~/.bashrc 文件的最后一行"

所以这整行命令的效果是：**让 mise 的启动命令被写入启动脚本，以后每次打开 Terminal，mise 都会自动启动。**

你不想每次手动输入一长串启动命令吧？所以现在就把它添加进去！

### 第四步：重启 Terminal，验证安装

添加完启动命令后，需要重启 Terminal 让它生效。最简单的方法是输入：

```
bash
```

这会重新启动一个 bash 会话，自动执行 ~/.bashrc 里的内容。

然后再次输入：

```
mise
```

如果你看到类似这样的帮助信息，说明安装成功了：

```shell
The front-end to your dev env

Usage: mise [OPTIONS] [TASK] [COMMAND]

Commands:
  activate      Initializes mise in the current shell session
  tool-alias    Manage tool version aliases.
  backends      Manage backends [aliases: b]
  ...
```

🎉 **恭喜！你已经成功安装了 mise！**

这件事在同一台机器上一辈子只需要做一次。以后这台 Codespace 只要还在，mise 就随时可用。

## 📌 关于 bash 和 zsh 的小知识

GitHub Codespace 默认使用的是 [**bash**](https://www.gnu.org/software/bash/)（一种常见的命令行程序）。

如果你用的是 Mac 电脑的 Terminal，默认是 [**zsh**](https://www.zsh.org/)（另一种命令行程序）。两者非常相似，但配置文件不同：

- bash 的启动脚本是 `` ~/.bashrc ``
- zsh 的启动脚本是 `` ~/.zshrc ``

所以如果你将来在 Mac 上安装 mise，安装过程一样，只是最后要把启动命令添加到 `` ~/.zshrc `` 而不是 `` ~/.bashrc ``。**mise 会自动识别你的 shell 类型并给出正确的提示**，不用担心。

## 👨‍🏫 导师寄语：找到"元工具"的智慧

完成安装后，你可能会想："不就是装个工具吗？为什么第一个就要学这个？"

让我分享一个更深层的认识：**在任何领域，找到并掌握那个"管理其他工具的工具"，是事半功倍的关键。**

### 从"各自为政"到"统一管理"

传统上，每个开发工具都有自己的安装方式和版本管理器：

| 语言/工具<br> | 传统版本管理器<br> | 学习成本<br> |
| --- | --- | --- |
| Python<br> | pyenv, conda, uv<br> | 需要单独学习<br> |
| Node.js<br> | nvm, fnm, volta<br> | 需要单独学习<br> |
| Ruby<br> | rbenv, rvm<br> | 需要单独学习<br> |
| Rust<br> | rustup<br> | 需要单独学习<br> |
| Go<br> | gvm<br> | 需要单独学习<br> |
这些工具都很优秀，但它们的设计者来自不同背景，设计哲学和命令风格都不一样。如果你要同时用 Python、Node.js、Ruby，就得学三套不同的工具。

而 mise 的思路是：**用最现代、最科学的设计，一次性统一解决所有开发工具的管理问题。**

### 这种思维方式的迁移价值

这个道理不只适用于开发工具。在任何领域，当你面对大量同类事物时，都可以问自己：

> "有没有一个'元工具'或'元方法'，能让我用一套方法管理所有这些？"

比如：

- 任务管理：与其用不同的 app 管理工作任务、个人事项、学习计划，不如找一个能统一管理的系统
- 知识管理：与其笔记散落在各处，不如建立一个统一的知识库
- 自动化：与其手动重复操作，不如学会写脚本或使用自动化工具

### 为什么现在就学？

我们之后会学习 AI 相关的开发：需要 Python、Claude CLI、Node.js、uv（Python 包管理器）……

如果不用 mise，你可能要学习至少四五个不同的工具来管理这些。而现在先学会 mise，之后只需要：

```
mise use python@3.11
mise use node@20
mise use npm:@anthropic-ai/claude-code

```

就这样，一个命令一个工具，全部搞定。你可以直接专注于学习和做事，而不是在工具管理上浪费时间。

**这就是"磨刀不误砍柴工"——先花一点时间学最好的那把刀，之后所有的树都砍得更快。**

## ✅ 完成检查清单

- [ ] 在新的 Codespace 里输入 `` mise ``，确认显示 `` command not found ``
- [ ] 运行 `` curl https://mise.run | sh `` 完成安装
- [ ] 复制粘贴 `` echo "eval..." `` 那行命令，将 mise 添加到启动脚本
- [ ] 输入 `` bash `` 重启 Terminal
- [ ] 再次输入 `` mise ``，看到帮助信息而不是 `` command not found ``

## 💡 关键要点总结

1. **mise 是开发工具的"万能遥控器"** - 一个工具管理 Python、Node.js、CLI 工具等所有开发工具
2. **安装命令：** `` curl https://mise.run | sh ``
3. **别忘了关键一步：** 把 mise 的启动命令添加到 ~/.bashrc（安装脚本会提示你具体命令）
4. **重启 Terminal 才生效：** 输入 `` bash `` 或重新打开 Terminal
5. **一次安装，永久使用：** 同一台机器只需要安装一次