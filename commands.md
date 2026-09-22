# 🐧 Linux & Git — Useful Commands

A quick reference for the Linux commands I'm learning.

---

# 🐧 Linux Commands

## 🖥️ Basic Commands

### `clear`

Clears the terminal screen.

```bash
clear
```

---

### `whoami`

Shows the name of the current user.

```bash
whoami
```

> **Note:**
>
> * `root` → has full permissions on the system.
> * `ec2-user` → an administrative user on many Amazon EC2 instances, but it is **not** the root user.

---

### `pwd`

Shows the current working directory.

```bash
pwd
```

**pwd = Print Working Directory**

---

# 📂 Working with Directories

### `cd`

Changes the current directory.

```bash
cd /home
```

**cd = Change Directory**

---

### `cd /`

Moves to the root directory.

```bash
cd /
```

Think of it like going to:

```text
C:\
```

on Windows.

On Linux, `/` is the top-level directory of the entire filesystem.

---

### `cd`

With no argument, it takes you to your home directory.

```bash
cd
```

For example:

```text
/home/ec2-user
```

You can also use:

```bash
cd ~
```

`~` represents the current user's home directory.

---

### `ls`

Lists files and directories.

```bash
ls
```

---

### `ls -la`

Lists **all** files and directories in long format, including hidden files.

```bash
ls -la
```

Breakdown:

```text
-l  → long format
-a  → all files, including hidden files
```

---

# 📁 Creating Directories and Files

### `mkdir`

Creates a directory.

```bash
mkdir new_folder
```

**mkdir = Make Directory**

---

### `mkdir -p`

Creates a directory structure, including parent directories when necessary.

```bash
mkdir -p folder_name/{subfolder1,subfolder2,subfolder3}
```

This creates:

```text
folder_name/
├── subfolder1/
├── subfolder2/
└── subfolder3/
```

---

### `touch`

Creates an empty file.

```bash
touch file_name.ext
```

Example:

```bash
touch index.html
```

---

### `rm -r`

Removes a directory and its contents recursively.

```bash
rm -r folder_name
```

**rm = Remove**
**-r = Recursive**

⚠️ Be careful with `rm` because deleted files may not be recoverable.

---

# 🔎 Viewing Files and Directories

### `cat`

Displays the contents of a file.

```bash
cat file_name
```

Example:

```bash
cat index.html
```

---

### `ls -lh`

Lists files using a human-readable format and shows their sizes.

```bash
ls -lh subfolder1
```

**-h = Human-readable**

For example:

```text
2.1K
15M
1.2G
```

---

### `cd folder_name && ls -R`

Moves into a directory and recursively lists its contents.

```bash
cd folder_name && ls -R
```

**&&** means:

> Run the second command only if the first command succeeds.

`-R` means:

> List directories recursively.

---

# 🌐 Creating a Simple HTML File

### `echo`

Prints text to the terminal or writes it to a file.

```bash
echo "Welcome to my web" > subfolder1/index.html
```

This creates `index.html` and writes:

```html
Welcome to my web
```

into it.

### `>` vs `>>`

```bash
> 
```

Creates or **overwrites** the file.

```bash
>>
```

Appends to the existing file.

Example:

```bash
echo "Hello" > file.txt
echo "World" >> file.txt
```

Result:

```text
Hello
World
```

---

# 🕐 Command History

### `history`

Shows previously executed commands in the current shell history.

```bash
history
```

Example:

```text
25  pwd
26  ls
27  cd /home
28  ls -la
```

You can execute a previous command by its number:

```bash
!27
```

This executes command number `27`.

---

# 🖥️ Server Information

### `hostname`

Shows the hostname of the machine/server.

```bash
hostname
```

The hostname identifies the machine on the network.

---

### `uname -a`

Displays information about the operating system and kernel.

```bash
uname -a
```

**-a = All available information**

---

### `uptime`

Shows how long the system has been running.

```bash
uptime
```

It can also show information such as:

* System uptime
* Number of logged-in users
* System load

---

### `df -h`

Shows available and used disk space.

```bash
df -h
```

**df = Disk Free**

**-h = Human-readable**

Example:

```text
Filesystem      Size  Used  Avail  Use%
/dev/xvda1       20G   8G    12G   40%
```

---

### `free -h`

Shows RAM and memory usage.

```bash
free -h
```

**free = Memory usage**

**-h = Human-readable**

---

### `nproc`

Shows the number of available processing units (CPU cores).

```bash
nproc
```

Example:

```text
2
```

---

# 📦 Package Management

### `yum`

`yum` is a package manager used by some Linux distributions, including older Amazon Linux versions.

Example:

```bash
sudo yum install htop
```

Breakdown:

```text
sudo  → execute with elevated privileges
yum   → package manager
install → install a package
htop  → package being installed
```

---

### `sudo`

Runs a command with elevated privileges.

```bash
sudo command
```

For example:

```bash
sudo yum install htop
```

> `sudo` does not mean "root user." It allows an authorized user to execute a specific command with elevated privileges.

---

### `htop`

`htop` provides an interactive dashboard for monitoring the system.

```bash
htop
```

It can show:

* CPU usage
* RAM usage
* Processes
* System load
* Running programs

---

# 📖 Command Documentation

### `man`

Opens the manual page for a command.

```bash
man command_name
```

Example:

```bash
man ls
```

**man = Manual**

You can use it to learn about:

* What a command does
* Available options
* Arguments
* Examples

---

# 🧩 Useful Linux Symbols

| Symbol | Meaning                               |
| ------ | ------------------------------------- |
| `/`    | Root directory                        |
| `~`    | Current user's home directory         |
| `.`    | Current directory                     |
| `..`   | Parent directory                      |
| `>`    | Create/overwrite file                 |
| `>>`   | Append to file                        |
| `&&`   | Run next command if previous succeeds |
| `*`    | Wildcard                              |
| `-`    | Command option                        |

---

# 🌿 Git & GitHub

## 📥 Clone a Repository

### `git clone`

Downloads a repository from GitHub or another Git server.

```bash
git clone repo_url
```

Example:

```bash
git clone https://github.com/user/project.git
```

---

# ⚙️ Configure Git

### Set your username

```bash
git config --global user.name "Ana Maria"
```

### Set your email

```bash
git config --global user.email "anamaria@email.com"
```

Check your configuration:

```bash
git config --global --list
```

---

# 📋 Check Repository Status

### `git status`

Shows the current state of the Git repository.

```bash
git status
```

It can show:

* Modified files
* New files
* Deleted files
* Files ready to commit
* Current branch

---

# ➕ Stage Changes

### `git add .`

Stages all changes in the current directory.

```bash
git add .
```

The files are now ready to be committed.

---

# 💾 Commit Changes

### `git commit`

Creates a commit with a message describing the changes.

```bash
git commit -m "Message content"
```

Example:

```bash
git commit -m "Add Linux command notes"
```

---

# ☁️ Push Changes to GitHub

### `git push`

Uploads local commits to the remote repository.

```bash
git push origin main
```

Breakdown:

```text
git push → upload commits
origin   → remote repository name
main     → branch name
```

---

# 🔄 Basic Git Workflow

The basic workflow is:

```text
        Make changes
             ↓
        git status
             ↓
        git add .
             ↓
     git commit -m "..."
             ↓
       git push origin main
             ↓
          GitHub
```

### Quick version

```bash
git status
git add .
git commit -m "Describe changes"
git push origin main
```

---

# 🧠 Quick Cheat Sheet

| Command      | What it does                          |
| ------------ | ------------------------------------- |
| `clear`      | Clears terminal                       |
| `whoami`     | Shows current user                    |
| `pwd`        | Shows current directory               |
| `cd`         | Changes directory                     |
| `ls`         | Lists files/directories               |
| `ls -la`     | Lists all files in long format        |
| `mkdir`      | Creates a directory                   |
| `touch`      | Creates a file                        |
| `rm -r`      | Removes a directory recursively       |
| `cat`        | Displays file contents                |
| `history`    | Shows command history                 |
| `hostname`   | Shows machine hostname                |
| `uname -a`   | Shows system information              |
| `uptime`     | Shows system uptime                   |
| `df -h`      | Shows disk usage                      |
| `free -h`    | Shows RAM usage                       |
| `nproc`      | Shows CPU count                       |
| `sudo`       | Runs command with elevated privileges |
| `yum`        | Package manager                       |
| `htop`       | System monitoring tool                |
| `man`        | Opens command manual                  |
| `git clone`  | Clones a repository                   |
| `git status` | Shows Git status                      |
| `git add .`  | Stages changes                        |
| `git commit` | Creates a commit                      |
| `git push`   | Pushes commits to remote              |
