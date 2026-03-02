# Installing mise: One Tool to Manage All Your Dev Tools

## 📋 What You'll Learn

- What mise is and why it's worth using
- How to install mise in a GitHub Codespace
- How to verify the installation works

## 🎯 Why Does This Matter?

Picture this: it's your first day at a new tech job, and you're ready to start coding. Then reality hits:

- One project needs Python 3.11
- Another runs on Node 20
- There's a legacy app stuck on Python 3.9
- Oh, and you need the Claude CLI for AI-assisted development…

Now what? Download each one manually from different websites? Deal with version conflicts? Learn a completely different management tool for each runtime?

It's like having a growing pile of remote controls at home — one for the TV, one for the AC, one for the speaker, one for the projector… What you really want is a universal remote.

**That's mise — the universal remote for your dev tools.**

With mise, you learn one set of commands to install, switch, and manage nearly everything: Python, Node.js, Go, Rust, Claude CLI… all through a single tool.

## 📖 What Is mise?

mise (pronounced "meez," from the French cooking term *mise en place*, meaning "everything in its place") is a **dev environment management tool**.

Put simply, it's a tool that manages your other tools. Traditionally, every language and runtime has its own version manager:

- Python has pyenv, uv
- Node.js has nvm, fnm
- Ruby has rbenv
- Various CLI tools use npm, pipx…

mise unifies all of them. Instead of learning half a dozen different tools, you just learn mise.

> **Why the name?** *Mise en place* is a core principle in professional kitchens: before you start cooking, get every ingredient and tool prepped and in position. The idea behind mise is the same — get your dev environment ready to go before you start working.

## 📝 Prerequisites

This tutorial assumes you can:

- Use GitHub Codespaces (open, use, and delete them)
- Type commands in a terminal and press Enter
- Copy and paste

No Linux, bash, or programming knowledge required.

## 💻 Hands-On: Installing mise in a Codespace

The whole process takes three steps. Let's walk through them.

### Step 1: Confirm mise isn't installed yet

Open the Terminal in your GitHub Codespace.

Type:

```
mise

```

Since this is a fresh Codespace (basically a brand-new machine), mise won't be installed. You'll see:

```
bash: mise: command not found

```

That's expected! It just confirms we need to install it.

### Step 2: Run the installer

Codespaces run Linux. Per the [official mise docs](https://mise.jdx.dev/getting-started.html), the Linux install command is:

```
curl https://mise.run | sh

```

> **Quick note:** `` curl `` is a download tool. This command grabs an install script from mise.run and runs it.

Paste that into your Terminal and hit Enter. You'll see output like this:

```
mise: installing mise...
######################################################################## 100.0%
mise: installed successfully to /home/codespace/.local/bin/mise
mise: run the following to activate mise in your shell:
echo "eval \"$(/home/codespace/.local/bin/mise activate bash)\"" >> ~/.bashrc

mise: run `mise doctor` to verify this is setup correctly

```

Installed! But we're not done yet — see that line starting with `` echo ``? That's important.

### Step 3: Make mise start automatically

This is the step most people skip, and then wonder why mise doesn't work.

That `` echo "eval ..." `` command is mise telling you: "If you want me available every time you open a terminal, add my activation command to your shell startup script."

**Copy and run it now!** The full command looks like this (yours may differ slightly — use whatever your terminal printed):

```
echo "eval \"$(/home/codespace/.local/bin/mise activate bash)\"" >> ~/.bashrc

```

**What's actually happening here?**

Here's a quick analogy:

- `` ~/.bashrc `` is like a startup script that runs automatically every time you open a terminal (or type `` bash `` to start a new session)
- `` eval "$(...mise activate bash)" `` is mise's activation command — without it, mise is installed but dormant
- `` echo "..." >> ~/.bashrc `` appends that activation line to the end of your `` .bashrc `` file

The net effect: **mise's activation command gets saved to your startup script, so it launches automatically every time you open a terminal.**

Nobody wants to type a long activation command by hand every time, so let's set it and forget it.

### Step 4: Restart the terminal and verify

After adding the activation command, you need to restart the terminal for it to take effect. The easiest way:

```
bash

```

This starts a fresh bash session, which automatically runs everything in `` ~/.bashrc ``.

Now type:

```
mise

```

If you see help output like this, you're all set:

```
The front-end to your dev env

Usage: mise [OPTIONS] [TASK] [COMMAND]

Commands:
  activate      Initializes mise in the current shell session
  tool-alias    Manage tool version aliases.
  backends      Manage backends [aliases: b]
  ...

```

🎉 **You've successfully installed mise!**

This is a one-time setup per machine. As long as this Codespace exists, mise is ready to go.

## 📌 A Quick Note on bash vs. zsh

GitHub Codespaces default to [**bash**](https://www.gnu.org/software/bash/) as the shell.

If you're on a Mac, your terminal defaults to [**zsh**](https://www.zsh.org/). They're very similar, but they use different config files:

- bash reads from `` ~/.bashrc ``
- zsh reads from `` ~/.zshrc ``

So if you install mise on a Mac later, the process is the same — just add the activation command to `` ~/.zshrc `` instead of `` ~/.bashrc ``. **mise detects your shell automatically and gives you the right command**, so no need to worry.

## 👨‍🏫 The Bigger Lesson: Meta-Tools

After finishing the install, you might think: "All I did was install a tool. Why was this the very first thing to learn?"

Here's the deeper insight: **in any field, finding the tool that manages all your other tools is a massive force multiplier.**

### From fragmentation to unification

Traditionally, each dev tool comes with its own version manager:

| Language/Tool<br> | Traditional Version Manager<br> | Learning Cost<br> |
| --- | --- | --- |
| Python<br> | pyenv, conda, uv<br> | Separate learning curve<br> |
| Node.js<br> | nvm, fnm, volta<br> | Separate learning curve<br> |
| Ruby<br> | rbenv, rvm<br> | Separate learning curve<br> |
| Rust<br> | rustup<br> | Separate learning curve<br> |
| Go<br> | gvm<br> | Separate learning curve<br> |
These are all solid tools, but they come from different authors with different design philosophies and different command patterns. Working with Python, Node.js, and Ruby means learning three separate tools.

mise takes a different approach: **one modern, consistent interface to manage all of them.**

### This thinking applies everywhere

This principle goes way beyond dev tools. Whenever you're juggling a bunch of similar things, ask yourself:

> "Is there a meta-tool or meta-method that lets me handle all of these with one approach?"

Some examples:

- Task management: instead of scattering tasks across different apps for work, personal stuff, and learning, find one system that covers everything
- Knowledge management: instead of notes in five different places, build a unified knowledge base
- Automation: instead of repeating the same steps manually, learn scripting or use automation tools

### Why learn this first?

Later in this course, we'll be working with AI development tools: Python, Claude CLI, Node.js, uv (a Python package manager)…

Without mise, you'd need to learn four or five different tools to manage all of those. With mise, it's just:

```
mise use python@3.11
mise use node@20
mise use npm:@anthropic-ai/claude-code

```

One command per tool, done. You can focus on actually building things instead of fighting with tool management.

**Sharpen the axe before you chop the tree — spend a little time learning the best tool now, and everything after goes faster.**

## ✅ Completion Checklist

- [ ] Typed `` mise `` in a fresh Codespace and confirmed `` command not found ``
- [ ] Ran `` curl https://mise.run | sh `` to install
- [ ] Copied and ran the `` echo "eval..." `` command to add mise to the startup script
- [ ] Typed `` bash `` to restart the terminal
- [ ] Typed `` mise `` again and saw help output instead of `` command not found ``

## 💡 Key Takeaways

1. **mise is the universal remote for dev tools** — one tool to manage Python, Node.js, CLI tools, and more
2. **Install command:** `` curl https://mise.run | sh ``
3. **Don't skip the critical step:** add mise's activation command to `` ~/.bashrc `` (the installer tells you exactly what to run)
4. **Restart the terminal to apply changes:** type `` bash `` or reopen the terminal
5. **One-time setup:** you only need to do this once per machine