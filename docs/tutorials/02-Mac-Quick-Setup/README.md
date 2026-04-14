# Mac Local Dev Environment Quick Setup

> Set up your Mac for local development in minutes — VS Code, Ghostty, and GitHub Desktop.

## 📋 What You'll Learn

- Install three core tools on your Mac: VS Code, Ghostty, and GitHub Desktop
- Understand the User Folder concept and set up a clean project folder structure
- Transition from GitHub Codespaces to local development

## 🎯 Why Does This Matter?

Congrats on installing mise! You now have a universal remote for managing dev tools.

Remember how we've been using GitHub Codespaces? Codespaces are great — they're like a disposable cloud workspace where you can experiment freely. If something breaks, just delete it and start over. For a beginner, that's an incredibly safe sandbox.

But now that you know mise, setting up tools on your own Mac is just as simple and safe. mise keeps everything organized and isolated — it won't mess up your system. So it's time to bring your main workspace home to your own machine.

**The benefits of local development are clear:**

- Speed — no waiting for a Codespace to spin up, just open your laptop and go
- Your files live on your machine, always accessible
- Works offline — no internet? No problem, you can still code
- No worrying about Codespace free-tier limits

Of course, Codespaces are still useful. When you want to try something new without touching your local setup, spinning up a quick Codespace is still a great option.

**Our strategy: use local for daily work, use Codespaces for exploration.**

So what do you need for local development? Just three things: a code editor, a terminal, and a Git manager. Let's install them one by one.

## 🛠️ Tool 1: VS Code (Code Editor)

VS Code (Visual Studio Code) is the most popular code editor out there. If you've been through our GitHub tutorials, you've already seen it — the editor inside GitHub Codespaces is actually a web version of VS Code.

Now we're going to install the real deal on your Mac.

**How to install:**

1. Open your browser and go to https://code.visualstudio.com
2. Click the big Download button to get the Mac version
3. Open the downloaded ``.dmg`` file and drag VS Code into your Applications folder
4. Open VS Code from your Applications folder

That's it. Done.

You'll notice the local VS Code looks almost identical to the one in Codespaces. Going forward, you'll use it to open project folders and edit code — same experience, but running right on your machine.

## 🛠️ Tool 2: Ghostty (Terminal)

A terminal is that window where you type commands. Mac comes with a built-in app called "Terminal" that works fine, but looks pretty basic.

If you want something that looks nicer and feels better, I recommend **Ghostty**. It's fast, beautiful, and completely free.

> If you're happy with the built-in Terminal, feel free to skip this step entirely. It works just fine.

**How to install:**

1. Open your browser and go to https://ghostty.org
2. Download the Mac version
3. Open the downloaded ``.dmg`` file and drag Ghostty into your Applications folder
4. Open Ghostty from your Applications folder

You'll see a clean, good-looking terminal window. Try typing ``mise`` — if you've already installed mise on your Mac, you should see the help output.

Going forward, whether you're using mise to install tools or running Python, Claude Code, or any other command, this is where you'll do it.

## 🛠️ Tool 3: GitHub Desktop (Git Manager)

If you've been through our GitHub tutorials, you already know GitHub Desktop. It's a graphical Git manager that lets you handle version control with clicks instead of memorizing Git commands.

**How to install:**

1. Open your browser and go to https://desktop.github.com/download/
2. Download the Mac version
3. Install and open it
4. Sign in with your GitHub account

Once installed, you can use it to clone (download) projects from GitHub to your Mac, and sync your local changes back to GitHub.

## 📁 About the User Folder: Where Do Your Files Live?

Before we start using these tools together, let's talk about a basic concept — the **User Folder**.

Open Finder on your Mac. In the sidebar, you'll see familiar folders: Documents, Downloads, Desktop, and so on. All of these live inside your **User Folder**.

Why is it called "User Folder"? Because computers are designed to support multiple people using the same machine. Each person is a "user," and each user gets their own folder to store their stuff. On your personal Mac, you're probably the only user, so there's just one.

Your User Folder path on Mac looks like this:

```
/Users/your-username/
```

For example, if your username is ``alice``, it's ``/Users/alice/``. Your Documents folder is actually ``/Users/alice/Documents``, your Downloads is ``/Users/alice/Downloads``, and so on.

## 📂 Recommended Project Folder Structure

Now that you understand the User Folder concept, I recommend creating a folder called ``GitHub`` inside your Documents folder (or directly inside your User Folder). This is where you'll keep all the projects you clone from GitHub.

```
/Users/your-username/
├── Documents/
│   └── GitHub/             ← dedicated folder for Git projects
│       ├── project-a/      ← one Git project
│       ├── project-b/      ← another Git project
│       └── learn-xxx/      ← yet another Git project
├── Downloads/
├── Desktop/
└── ...
```

**Each subfolder is a Git repository (repo).** This keeps things clean — all your projects in one place, easy to find.

When GitHub Desktop asks where to clone a project, just point it to this ``GitHub`` folder.

## 🔮 What's Next: Installing Tools with mise

Now your Mac has the essential trio: VS Code for editing code, Ghostty (or Terminal) for running commands, and GitHub Desktop for managing projects.

In upcoming lessons, we'll be working with Python and Claude Code (an AI coding assistant). Both can be installed with mise! Remember how easy it is:

```
mise use python@3.12
mise use npm:@anthropic-ai/claude-code
```

Up and running on your machine in seconds. That's the magic of mise — tools that sound intimidating become a one-liner install.

## 👨‍🏫 Mentor's Note: From Borrowing a Kitchen to Owning Your Workbench

Using Codespaces was like cooking in someone else's kitchen — everything was set up for you, but it wasn't really yours. When you were done, you had to clean up and leave.

Now you've set up a dev environment on your own Mac. This is your workbench. VS Code is your cutting board, the terminal is your stove, GitHub Desktop is your pantry, and mise is the assistant who keeps all your kitchen tools organized.

This setup will carry you forward. Whether you're learning Python, building with AI, or working on projects, you just open your laptop and start.

**You might worry: will installing all this stuff mess up my computer?** Don't. With mise, your tools are neatly managed and isolated. That's literally what mise is for — keeping your dev environment "in its place" (*mise en place*), not a tangled mess.

You've gone from "borrowing someone else's kitchen" to "having your own workbench." That's a real milestone — and things only get more interesting from here.

## ✅ Completion Checklist

- [ ] Installed VS Code and opened it successfully
- [ ] Installed Ghostty (or confirmed you'll use the built-in Terminal)
- [ ] Installed GitHub Desktop and signed in with your GitHub account
- [ ] Created a ``GitHub`` folder inside Documents
- [ ] Typed ``mise`` in the terminal and confirmed it works

## 💡 Key Takeaways

1. **Local for daily work, Codespaces for exploration** — they complement each other
2. **The trio: VS Code + Ghostty + GitHub Desktop** — code editing, command line, project management, all covered
3. **Keep projects organized in Documents/GitHub/** — each subfolder is a Git repo
4. **mise manages dev tools** — Python, Claude Code, and more, installed with one command, no system mess
5. **User Folder is your home on the computer** — all your personal files live under ``/Users/your-username/``
