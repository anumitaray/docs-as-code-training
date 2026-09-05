# Cursor Quickstart

> **Source**: [https://cursor.com/docs/get-started/quickstart](https://cursor.com/docs/get-started/quickstart)  
> This guide gets you from install to your first useful change in Cursor. You'll sign in, ask Cursor to explain your codebase, make a small edit, and review the result.

---

## 1. Install Cursor and Sign In

Download Cursor, open the application, and sign in to your account. Then pick a project folder and start with a small task.

- **Download Link**: [cursor.com/downloads](https://cursor.com/downloads)

### Platform Requirements & Installation

#### macOS
- **System Requirements**: macOS 12 (Monterey) and later
- **Installer**: Native installer (`.dmg`)
- **Architecture**: Apple Silicon (M1/M2/M3/M4) and Intel x86_64 support

#### Windows
- **System Requirements**: Windows 10 and later (64-bit)
- **Installer**: Native installer (`.exe`)

#### Linux

##### Debian / Ubuntu (Recommended)
Add the official Cursor repository and GPG key for automated updates and CLI tool integration:

```bash
# Add Cursor's GPG key
curl -fsSL https://downloads.cursor.com/keys/anysphere.asc | gpg --dearmor | sudo tee /etc/apt/keyrings/cursor.gpg > /dev/null

# Add the Cursor repository
echo "deb [arch=amd64,arm64 signed-by=/etc/apt/keyrings/cursor.gpg] https://downloads.cursor.com/aptrepo stable main" | sudo tee /etc/apt/sources.list.d/cursor.list > /dev/null

# Update package lists and install Cursor
sudo apt update
sudo apt install cursor
```

##### RHEL / Fedora
Configure the yum repository:

```bash
# Add Cursor's repository
sudo tee /etc/yum.repos.d/cursor.repo << 'EOF'
[cursor]
name=Cursor
baseurl=https://downloads.cursor.com/yumrepo
enabled=1
gpgcheck=1
gpgkey=https://downloads.cursor.com/keys/anysphere.asc
EOF

# Install Cursor via dnf
sudo dnf install cursor
```

##### AppImage (Portable)
Download the `.AppImage` file from [cursor.com/downloads](https://cursor.com/downloads), then run:

```bash
chmod +x Cursor-*.AppImage
./Cursor-*.AppImage
```

> **Note**: The `apt` and `yum` native package manager packages are preferred over AppImage because they provide system desktop launcher icons, automatic background updates, and terminal CLI symlinks (`cursor .`).

---

## 2. Ask Cursor to Explain Your Codebase

After you open your project folder, launch the Agent pane:
- **macOS**: `Cmd + I`
- **Windows / Linux**: `Ctrl + I`

Ask Cursor to explain how the codebase is structured and point out the key areas to explore:

### Recommended Exploration Prompt

```text
Explain this codebase. Point me to the main entry points, key modules, and anything I should read before making changes.
```

### What Happens
Cursor will automatically:
1. Search through your repository using semantic indexing.
2. Read the relevant entry point files, config files, and core modules.
3. Summarize how the components connect together.

This is one of the fastest ways to get oriented in any unfamiliar codebase.

> *Want a deeper walkthrough? See [Understand your codebase](https://cursor.com/learn/understanding-your-codebase).*

---

## 3. Make One Small Change

Once you understand the project layout, ask Cursor to propose a few safe, incremental improvements. Choose one and instruct it to make the change.

### Recommended Starter Prompt

```text
Suggest three small, safe improvements in this codebase. Explain the tradeoffs and wait for me to choose one.
```

### Tips for Early Success
- Good first tasks are low-risk changes, such as improving copywriting, adding missing TypeScript types, fixing small CSS/UI alignment issues, or adding inline documentation.
- If you already know what you want to change, ask for it directly and describe the exact outcome and constraints you want.

---

## 4. Review the Diff and Verify the Result

While Cursor makes changes, you can watch it work in real time. The interactive diff view displays all changes proposed by the agent.

### Verification Workflow
1. **Inspect the inline diff**: Review line-by-line additions (green) and deletions (red).
2. **Run project checks**: Ask Cursor to execute the checks your project already relies on:
   - Automated test suites (`npm test`, `pytest`, `cargo test`, etc.)
   - Static type checking (`tsc --noEmit`, `mypy`)
   - Linters (`eslint`, `ruff`, `golangci-lint`)
   - Local build / dev server compilation (`npm run build`)

> *Want a stronger review workflow? See [Reviewing and testing code](https://cursor.com/docs/agent/review).*

---

## 5. Use Plan Mode for Bigger Changes

Now that you know the basics, use **Plan Mode** for larger, architectural tasks. Plan Mode is ideal when a task spans multiple files, requires codebase research, or requires your explicit approval before any code is modified.

### Activating Plan Mode
In the Agent prompt input bar, press:
- `Shift + Tab` to toggle **Plan Mode**.

### How Plan Mode Works
Instead of immediately writing code, Cursor will:
1. **Research your codebase** to find all relevant files and dependencies.
2. **Ask clarifying questions** about your specific technical requirements and constraints.
3. **Generate a detailed implementation plan** step-by-step.
4. **Wait for your approval** before touching code or generating modifications.

> *For a deeper walkthrough, see [Build new features](https://cursor.com/learn/creating-features).*

---

## Next Steps & Key Resources

Explore these resources to master Cursor's AI coding capabilities:

| Resource | Description | Documentation Link |
| :--- | :--- | :--- |
| **Agent Overview** | Learn about Agent's autonomous tools, multi-file edits, and terminal execution | [cursor.com/docs/agent/overview](https://cursor.com/docs/agent/overview) |
| **Rules (`.cursorrules`)** | Create persistent project-level instructions, conventions, and design standards | [cursor.com/docs/rules](https://cursor.com/docs/rules) |
| **Understand Your Code** | Techniques for getting oriented quickly in large or unfamiliar repos | [cursor.com/learn/understanding-your-codebase](https://cursor.com/learn/understanding-your-codebase) |
| **Build New Features** | Comprehensive end-to-end workflow for planning, executing, and shipping large features | [cursor.com/learn/creating-features](https://cursor.com/learn/creating-features) |

---

### Quick Reference: Essential Shortcuts

- `Cmd + I` / `Ctrl + I`: Open Agent Window
- `Shift + Tab` (in Agent): Toggle Plan Mode
- `Cmd + K` / `Ctrl + K`: Inline Code Edit in Editor
- `Cmd + L` / `Ctrl + L`: Open Chat Sidebar
- `@`: Reference files, folders, docs (`@Docs`), git commits, or web (`@Web`)
