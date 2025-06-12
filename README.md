# 🐧 Linux Commands

## 📁 Basic File & Directory Commands

| Command | Description | Examples |
|--------|-------------|--------|
| `ls` | List files and directories ||
| `ls -l` | Detailed list (size, owner, dates, permissions) ||
| `ls -ld` | Show info about the directory, not its contents ||
| `cd folder1/folder2` | Change to directory |`cd Projects/laravel-app`|
| `cd ..` | Go up one level |
| `cd ../..` | Go up two levels |
| `pwd` | Print current path |
| `mkdir name` | Create directory |
| `rmdir name` | Remove empty directory |
| `rm file` | Remove file |
| `rm -r folder` | Remove folder and contents |
| `touch file.txt` | Create new empty file |
| `cp source target` | Copy file/folder |
| `mv source target` | Move or rename file/folder |
| `find /path -name "file"` | Find file by name |
| `locate name` | Fast search (pre-indexed) |

## 📄 Viewing & Editing Files

| Command | Description |oiu|
|--------|-------------|--|
| `cat file.txt` | Show file content ||
| `less file.txt` | View with scroll |
| `head -n 10 file.txt` | Show first 10 lines |
| `tail -n 10 file.txt` | Show last 10 lines |
| `tail -f logfile.txt` | Real-time file view |
| `nano file.txt` | Simple terminal editor |
| `vim file.txt` | Advanced terminal editor |
| `wc -l file.txt` | Count lines |
| `cut -d',' -f1 file.csv` | Cut field from CSV |
| `grep "text" file.txt` | Search text in file |
| `grep -r "text" folder/` | Recursive text search |

## 🔐 Permissions & Users

| Command | Description |
|--------|-------------|
| `chmod 755 file` | Set permissions |
| `chown user:group file` | Change ownership |
| `sudo command` | Run as superuser |
| `su` | Switch to root |
| `whoami` | Show current user |
| `id` | Show UID, GID, groups |
| `adduser name` | Add user |
| `passwd` | Change password |

## 🖥️ System Info

| Command | Description |
|--------|-------------|
| `uname -a` | System details |
| `top` | Live process monitor |
| `htop` | Enhanced process monitor |
| `free -h` | RAM usage |
| `df -h` | Disk space |
| `du -sh folder/` | Folder size |
| `uptime` | System uptime |
| `who` | Logged-in users |
| `ps aux` | List all processes |
| `kill PID` | Kill process |
| `kill -9 PID` | Force kill process |
| `lsof -i :80` | Check what uses port 80 |

## 📦 Package Management (Debian/Ubuntu)

| Command | Description |
|--------|-------------|
| `sudo apt update` | Update package list |
| `sudo apt upgrade` | Upgrade packages |
| `sudo apt install package` | Install package |
| `sudo apt remove package` | Remove package |
| `dpkg -l` | List installed packages |
| `dpkg -i package.deb` | Install from `.deb` file |

## 🌐 Network

| Command | Description |
|--------|-------------|
| `ping address` | Test connection |
| `ifconfig` or `ip a` | Show IP addresses |
| `ip route` | Show routes |
| `netstat -tuln` | Show open ports |
| `curl url` | Fetch web page |
| `wget url` | Download file |
| `ssh user@host` | SSH connection |
| `scp file user@host:/path` | Secure copy over SSH |

## 🗃️ Archiving & Compression

| Command | Description |
|--------|-------------|
| `tar -cvf archive.tar folder/` | Create `.tar` archive |
| `tar -xvf archive.tar` | Extract archive |
| `tar -czvf archive.tar.gz folder/` | Create compressed archive |
| `tar -xzvf archive.tar.gz` | Extract compressed archive |
| `zip -r file.zip folder/` | Create `.zip` archive |
| `unzip file.zip` | Extract `.zip` |

## 🧠 Miscellaneous

| Command | Description |
|--------|-------------|
| `alias ll='ls -alF'` | Create shortcut |
| `history` | Show command history |
| `!!` | Repeat last command |
| `!123` | Run command #123 from history |
| `man command` | Manual page |
| `crontab -e` | Edit cron jobs |
| `watch -n 1 command` | Run command repeatedly |

## 🔢 Permissions as Numbers

| Number | Symbol | Description                              |
|--------|--------|------------------------------------------|
| 0      | ---    | no permissions                           |
| 1      | --x    | execute only                             |
| 2      | -w-    | write only                               |
| 3      | -wx    | write + execute                          |
| 4      | r--    | read only                                |
| 5      | r-x    | read + execute                           |
| 6      | rw-    | read + write                             |
| 7      | rwx    | full permissions (read, write, execute)  |

---

## 👤👥🌍 
## The Three Digits Represent User Groups Others

| Digit Position | Applies To            |
|----------------|-----------------------|
| 1st digit      | Owner (user)          |
| 2nd digit      | Group                 |
| 3rd digit      | Others (everyone else) |

---

## 📘 Examples

### `chmod 755 file.sh`
To recursively apply permissions to all files and folders in a directory, run this command from the parent directory:
### `chmod -R 755 your_folder/`


- `7` (owner): read + write + execute → `rwx`
- `5` (group): read + execute → `r-x`
- `5` (others): read + execute → `r-x`

✅ Common for scripts or Laravel public folders.

---

### `chmod 644 index.php`

- `6` (owner): read + write → `rw-`
- `4` (group): read only → `r--`
- `4` (others): read only → `r--`

✅ Safe for web files (others can't modify).

---

### `chmod 600 .env`

- `6` (owner): read + write → `rw-`
- `0` (group): no permissions → `---`
- `0` (others): no permissions → `---`

✅ Good for sensitive configuration files.

---

### `chmod 777 file.txt` ❗

- `7` (owner): full permissions → `rwx`
- `7` (group): full permissions → `rwx`
- `7` (others): full permissions → `rwx`

⚠️ **Insecure** – avoid on production!

---

## 🧠 Tip

To recursively apply permissions to all files and folders in a directory:

```bash
chmod -R 755 your_folder/
