# Step 1: Install Cursor and Sign In

> Part of the [Cursor Quickstart Guide](./quickstart.md)

Download Cursor, open the app, and sign in to your account. Then pick a project folder and start with a small task.
Sunday_Sept6

- **Download Link**: [https://cursor.com/downloads](https://cursor.com/downloads)

## System Requirements by Platform

### macOS
- **Operating System**: macOS 12 (Monterey) and later
- **Installer**: Native installer (`.dmg`)
- **Hardware Architecture**: Apple Silicon (M-series) and Intel support

### Windows
- **Operating System**: Windows 10 and later (64-bit)
- **Installer**: Native installer (`.exe`)

### Linux

#### Debian / Ubuntu (Recommended)
Add Cursor's official GPG key and APT repository:

```bash
# Add Cursor's GPG key
curl -fsSL https://downloads.cursor.com/keys/anysphere.asc | gpg --dearmor | sudo tee /etc/apt/keyrings/cursor.gpg > /dev/null

# Add the Cursor repository
echo "deb [arch=amd64,arm64 signed-by=/etc/apt/keyrings/cursor.gpg] https://downloads.cursor.com/aptrepo stable main" | sudo tee /etc/apt/sources.list.d/cursor.list > /dev/null

# Update package lists and install
sudo apt update
sudo apt install cursor
```

#### RHEL / Fedora
Add the YUM/DNF repository configuration:

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

# Install Cursor
sudo dnf install cursor
```

#### AppImage (Portable)
Download the `.AppImage` file from [cursor.com/downloads](https://cursor.com/downloads), then make it executable and run:

```bash
chmod +x Cursor-*.AppImage
./Cursor-*.AppImage
```

> **Tip**: The `apt` and `yum` packages are preferred over AppImage because they provide desktop integration, automatic updates, and CLI commands.
