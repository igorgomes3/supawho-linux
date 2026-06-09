<div align="center">

<table>
<tr>
<td align="center" width="300">
<img src="image.png" alt="supawho" width="280" />
</td>
<td align="center" width="400">
<img src="demo.png" alt="demo" width="380" />
</td>
</tr>
</table>

Switch between multiple **Supabase** accounts in seconds.<br>
Tokens are stored securely in **Linux GNOME Keyring**.

<br>

[![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=for-the-badge&logo=supabase&logoColor=fff)](#)
[![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

</div>

<br>

## 🍺 Installation

First, ensure you have the `secret-tool` package installed:
```bash
sudo apt install libsecret-tools -y
```

Then download the `supawho` binary and make it executable:
```bash
sudo wget -qO /usr/local/bin/supawho https://raw.githubusercontent.com/igorgomes3/supawho-linux/main/supawho
sudo chmod +x /usr/local/bin/supawho
```
<br>

## 🔑 Getting your Supabase Access Token

1. Open [**supabase.com/dashboard**](https://supabase.com/dashboard) and click your **profile icon** (top right)
2. Select **Account preferences**
3. Go to **Access Tokens** in the left sidebar
4. Click **Generate new token**, give it a name and copy the token

> 💡 The token starts with `sbp_` and is shown **only once** — make sure to copy it!

Then save it:

```bash
supawho add myproject sbp_xxxxxxxxxxxxx
```

<br>

## 🚀 Usage

| Command | Description |
|---------|-------------|
| `supawho` | Interactive account picker |
| `supawho add <name> <token>` | Save a new account |
| `supawho use <name>` | Switch to an account |
| `supawho list` | Show all saved accounts |
| `supawho remove <name>` | Delete an account |

### Interactive mode

Just run `supawho` with no arguments:

```
   ___  _   _ ___  ___  _    _ _  _  ___
  / __|| | | | _ \/ _ \| |  | | || |/ _ \
  \__ \| |_| |  _/ (_) | |/\| | __ | (_)
  |___/ \___/|_|  \__\_\__/\__|_||_|\___/

     🔍 Who are you today?

Select an account:

  1) myproject
  2) another-project

Enter number (1-2):
```

<br>

## 🔒 Why is it secure?

Your tokens **never touch the filesystem**. They are stored exclusively in the **Linux GNOME Keyring**, the same encrypted vault that your system uses for passwords and certificates.

| | supawho | Plain text files |
|---|:---:|:---:|
| Encrypted at rest | ✅ | ❌ |
| Protected by system login | ✅ | ❌ |
| Visible to other processes | ❌ | ✅ |
| Survives accidental `git add .` | ✅ | ❌ |

<br>

## 📋 Requirements

- **Linux** (Ubuntu, Pop!_OS, Debian, etc.) — requires `libsecret-tools` installed to access the GNOME Keyring via `secret-tool`
- [**Supabase CLI**](https://supabase.com/docs/guides/cli) or **npx supabase**

<br>

## 📄 License

[MIT](LICENSE) — Adapted for Linux by [Igor Gomes](https://github.com/igorgomes3). Original macOS version made with 💚 by [Elia Tolin](https://github.com/EliaTolin)
