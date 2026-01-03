# ezmailconfig

`ezmailconfig` is a lightweight, interactive CLI utility to quickly configure email sending on Linux systems. It simplifies the setup of `msmtp` for popular providers like Gmail, Outlook, and Proton Mail, as well as custom SMTP servers.

## Features

- **Auto-dependency detection:** Automatically installs `msmtp` and `whiptail` using your system's package manager (supports apt, dnf, pacman, etc.).
- **Interactive TUI:** User-friendly menus for selecting providers and entering credentials.
- **Provider Presets:** Optimized configurations for Gmail (App Passwords), Outlook, and Proton Mail Bridge.
- **CLI Mode:** Configure everything via command-line arguments for scripts and automation.
- **Testing:** Built-in tool to send a test email and verify your configuration immediately.
- **Safe Backups:** Automatically backs up existing `.msmtprc` files before making changes.

## Installation

You can download the script directly and make it executable:

```bash
curl -O https://raw.githubusercontent.com/stldave314/ezmailconfig/master/ezmailconfig
chmod +x ezmailconfig
```

## Usage

### Interactive Mode (Recommended)

Simply run the script without arguments to start the wizard:

```bash
./ezmailconfig
```

### CLI Mode (Automation)

Configure a custom SMTP server without user interaction:

```bash
./ezmailconfig --user "your-email@example.com" --pass "your-password" --host "smtp.example.com" --port 587
```

### Testing

Send a test email to verify your current setup:

```bash
./ezmailconfig --test "recipient@example.com"
```

## Configuration File

The script generates and manages the `~/.msmtprc` file. Ensure this file is kept secure as it contains your email credentials. `ezmailconfig` automatically sets the permissions to `600` (read/write for owner only).

## Requirements

- Linux operating system
- `sudo` privileges (for installing dependencies)
- A supported package manager (apt, dnf, pacman, etc.)

## License

MIT
