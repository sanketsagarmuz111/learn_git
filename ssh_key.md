# 🔐 SSH Authentication (GitHub)

SSH lets you connect to GitHub securely without entering your username and password every time you push or pull.

---

## Check Existing SSH Keys

``` bash
ls -al ~/.ssh
```

📌 Lists all SSH keys on your system.

Example

```
~/.ssh/
├── id_ed25519
├── id_ed25519.pub
└── known_hosts
```

---

## Generate a New SSH Key

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

If your system doesn't support `ed25519`, use:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

📌 Creates a new SSH key pair.

```
Private Key (Keep Secret)
        │
        ▼
id_ed25519

Public Key (Share)
        │
        ▼
id_ed25519.pub
```

---

## Start the SSH Agent

```bash
eval "$(ssh-agent -s)"
```

📌 Starts the SSH authentication agent.

---

## Add SSH Key to the Agent

```bash
ssh-add ~/.ssh/id_ed25519
```

📌 Adds your private key to the SSH agent.

---

## Copy the Public Key

### macOS

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

### Linux

```bash
cat ~/.ssh/id_ed25519.pub
```

### Windows (Git Bash)

```bash
cat ~/.ssh/id_ed25519.pub
```

📌 Copy the displayed key and add it to your GitHub account.

---

## Add SSH Key to GitHub

1. Open **GitHub**
2. Go to **Settings**
3. Click **SSH and GPG Keys**
4. Click **New SSH Key**
5. Paste your public key
6. Click **Add SSH Key**


```
Computer
     │
     ▼
Public SSH Key
     │
     ▼
GitHub Account
```

---

## Test the SSH Connection

```bash
ssh -T git@github.com
```

Expected output:

```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

📌 Confirms your SSH key is correctly configured.

---

## Clone Using SSH

```bash
git clone git@github.com:username/repository.git
```

Instead of

```bash
git clone https://github.com/username/repository.git
```

📌 SSH is recommended because you won't need to enter your credentials every time.

---

## Change Existing Remote from HTTPS to SSH

Check the current remote:

```bash
git remote -v
```

Change it to SSH :

```bash
git remote set-url origin git@github.com:username/repository.git
```

Verify :

```bash
git remote -v
```

Example output :

```
origin  git@github.com:username/repository.git (fetch)
origin  git@github.com:username/repository.git (push)
```

---

## Verify SSH Fingerprint (Optional)

```bash
ssh -T git@github.com
```

The first time you connect, you'll see:

```
Are you sure you want to continue connecting (yes/no)?
```

Type:

```text
yes
```

GitHub's fingerprint will be saved for future connections.

---

## SSH Workflow

```
Generate SSH Key
        │
        ▼
Add Public Key to GitHub
        │
        ▼
Test Connection
        │
        ▼
Clone Repository (SSH)
        │
        ▼
git pull / git push
```

---

### 💡 Why Use SSH?

| HTTPS | SSH |
|--------|-----|
| Requires credentials or PAT | No repeated login |
| Good for occasional use | Best for daily development |
| Simpler setup | Slightly longer setup but more convenient |

> **Recommendation:** If you're a regular GitHub user, configure SSH once and use it for all repositories.
