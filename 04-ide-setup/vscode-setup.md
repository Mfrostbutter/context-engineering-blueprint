# VS Code Setup for Claude Code

VS Code (Visual Studio Code) is a free, open-source code editor from Microsoft. It's the most popular editor for AI-assisted work and has excellent Claude Code integration.

---

## Step 1: Install VS Code

1. Go to https://code.visualstudio.com
2. Download for your operating system
3. Run the installer
4. Open VS Code

---

## Step 2: Install the Claude Code extension

1. In VS Code, press `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (Mac) to open Extensions
2. Search for "Claude Code"
3. Install the extension published by Anthropic
4. Reload VS Code when prompted

The extension adds a Claude Code panel to your sidebar and lets you run Claude Code sessions directly in VS Code without switching to a separate terminal.

---

## Step 3: Recommended additional extensions

These aren't required, but they make the experience better:

**GitLens**
Shows git history and blame information inline in the editor. Useful when working with Claude Code — you can see what changed and who changed it without leaving the file.

**Markdown Preview Enhanced**
Better markdown rendering. Since CLAUDE.md files and knowledge base entries are markdown, this helps you read them clearly.

**GitHub Copilot** (optional)
If you have a Copilot subscription, install this for inline autocomplete. Works alongside Claude Code — different tools for different tasks.

---

## Step 4: Open a project folder

1. In VS Code: `File` → `Open Folder...`
2. Select your project directory (or create a new empty folder)
3. VS Code will show the folder contents in the left sidebar

---

## Step 5: Open the integrated terminal

Press `Ctrl+\`` (backtick, the key above Tab) to open VS Code's built-in terminal.

Run `claude` in the terminal to start a Claude Code session. You'll see the Claude Code prompt in the terminal while VS Code shows your files in the editor above.

This is the typical workflow:
- Write instructions to Claude in the terminal
- Watch it edit files in the editor above
- Review changes in the file explorer and editor

---

## Step 6: Open the Claude Code panel (extension)

Click the Claude icon in the VS Code sidebar (left-hand icon bar) or run `Ctrl+Shift+C` to open the Claude Code panel. This is an alternative to running `claude` in the terminal — same functionality, embedded in the editor window.

---

## Useful VS Code settings for AI work

Open settings with `Ctrl+,` (or `Cmd+,` on Mac). Search for each setting:

**Auto Save:** Set to `afterDelay` — this makes sure Claude Code's file edits are saved automatically.

**Word Wrap:** Set to `on` — CLAUDE.md files and markdown documents are easier to read with wrapping.

**Format on Save:** Set to `true` if you're working with code that has a formatter.

---

## The workflow in practice

1. Open VS Code
2. Open your project folder (`File` → `Open Folder`)
3. Open the integrated terminal (`Ctrl+\``)
4. Run `claude`
5. Give it a task: "Read CLAUDE.md and tell me what this project is about"
6. Watch it work — it reads files, you see changes in the editor
7. Review and commit with `git commit`

That's it. The rest is just practice.
