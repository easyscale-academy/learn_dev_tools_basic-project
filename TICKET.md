# Exercise: Installing mise, Your Developer Toolchain Manager

## Objective

Read the *[Installing mise: Your All-in-One Dev Tool Manager](https://easyscalecloud.atlassian.net/wiki/external/MGQxMzlhMGM1ZDZlNDQwYTkyMmZjNGI3YTVhZWFkN2I)* tutorial, then install and configure mise from scratch inside a brand-new GitHub Codespace. Once everything is working, delete the Codespace to free up resources.

**Estimated time: 15–20 minutes**

## How-to Guide

1. **Read the tutorial first** — work through the full *Installing mise: Your All-in-One Dev Tool Manager* tutorial before touching a terminal
2. Create a new GitHub Repository (name it anything you like, e.g. `mise-practice`)
3. Launch a new Codespace inside that repository
4. Follow the tutorial to install and configure mise
5. Verify that the `mise` command works correctly
6. Delete the Codespace when you're done (no need to keep it around)

> **Tip:** A freshly created Codespace is essentially a brand-new machine with no development tools pre-installed — which makes it the perfect sandbox for practicing a clean mise install from zero.

## Checklist

- [ ] **Create a practice repository** — create a new repository on GitHub (Public or Private, any name)
- [ ] **Start a new Codespace** — on the repository page, click the green **Code** button, open the **Codespaces** tab, and click **Create codespace on main**
- [ ] **Confirm the starting state** — run `mise` in the terminal; you should see `bash: mise: command not found`
- [ ] **Run the installer** — execute `curl https://mise.run | sh` and wait for it to finish
- [ ] **Add the shell hook** — copy the `echo "eval..."` command from the installer output and run it
- [ ] **Reload the shell** — type `bash` to start a fresh terminal session
- [ ] **Verify the installation** — run `mise` again; you should now see the help output (`Usage: mise [OPTIONS]...`) instead of `command not found`
- [ ] **Clean up** — go back to GitHub, open the repository's **Settings**, find the **Codespaces** section, and delete the Codespace you created; delete the repository too if you no longer need it