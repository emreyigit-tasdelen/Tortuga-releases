# Tortuga

**English** · [Türkçe](README.tr.md)

**One terminal for connecting to network devices, reading their output and auditing configs.**
SSH, Telnet and serial console in the same window. Command output turns into tables, and risky settings are flagged automatically.

[**⬇ Download the latest version**](../../releases/latest)  ·  [Release history](../../releases)  ·  [Installation](#installation)  ·  [Security](#how-are-updates-secured)

> The app's interface is currently in Turkish, as in the screenshots below. English is planned for version 1.0.4.

![Two SSH sessions side by side and the saved session tree](https://raw.githubusercontent.com/emreyigit-tasdelen/Tortuga-releases/gorseller/02-terminal.png)

## What does it do?

### Analyzes output and audits configs

Inspects session output, pasted text or a file with one click. It recognizes the device type, turns `show` output into filterable tables, and points to the exact line of problems such as open Telnet, default SNMP communities, reversible passwords and faulty ports. You can also compare two configs.

Table and audit support: Cisco IOS / IOS-XE, Aruba AOS-CX, Aruba AOS 8, Juniper Junos. Ruijie RGOS has audit rules and a command dictionary.

![Audit findings and tables built from show output](https://raw.githubusercontent.com/emreyigit-tasdelen/Tortuga-releases/gorseller/04-analiz.png)

### Completes commands for you

The command bar adapts its language to the device you're connected to, with completion, annotated suggestions and abbreviation expansion. You can send the same command to several sessions and save frequent steps as macros.

![Annotated completion suggestions in the command bar](https://raw.githubusercontent.com/emreyigit-tasdelen/Tortuga-releases/gorseller/03-komut-cubugu.png)

### All your connections in one place

SSH (password, private key, legacy algorithms for older devices), Telnet, serial (baud rate is detected automatically on USB console cables), Rlogin, SUPDUP, Raw and Bare SSH. Organize sessions into folders; passwords stay in the operating system's keychain. You can import your PuTTY sessions.

![Protocol selection and saved sessions in folders](https://raw.githubusercontent.com/emreyigit-tasdelen/Tortuga-releases/gorseller/01-baglanti.png)

### And for everyday work

- Tabs and horizontal/vertical split view
- SFTP file panel
- Port forwarding (`-L`, `-R`, `-D`) and jump host
- Session logging and history
- Themes, shortcuts, low memory mode

<sub>The sessions in the screenshots are sample data, and the connected device is a test simulator.</sub>

## Installation

1. Download `Tortuga_<version>_x64-setup.exe` from the [latest release](../../releases/latest) page. An `.msi` is also available for mass deployment.
2. Run the file.
3. If you see the "Windows protected your PC" warning, choose **More info → Run anyway**. The warning appears because the installer isn't signed with a code signing certificate yet.

Later versions arrive as in-app notifications and are installed with your approval.

| System | Status |
|---|---|
| Windows 10/11 (64-bit) | Available |
| Linux, macOS | Not released yet |

## Verifying the file

Every release includes `SHA256SUMS.txt`. The hash of the file you downloaded must match the one listed there:

```
certutil -hashfile Tortuga_<version>_x64-setup.exe SHA256
```

## How are updates secured?

- Every update package is signed with a key kept offline on the developer's computer (`.sig` files). The key isn't on GitHub or any server.
- Before installing a downloaded package, Tortuga verifies its signature with the public key embedded in the app. A package isn't installed if the signature doesn't match, if it belongs to a different version, or if it's an older version.
- Updates are always installed with the user's approval.

---

This repository contains compiled releases only; the source code isn't here. Installed copies of Tortuga check for and download updates from here.

## License

Compiled releases of Tortuga are licensed under the [Apache License 2.0](LICENSE). © 2026 Emre Yiğit Taşdelen
