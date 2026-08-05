# 🔐 SSH Authentication (GitHub)

SSH lets you connect to GitHub securely without entering your username and password every time you push or pull.

---

## Check Existing SSH Keys

```bash
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
