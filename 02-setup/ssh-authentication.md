# SSH Authentication

## What is it?
SSH (Secure Shell) authentication uses a pair of cryptographic keys (a public key and a private key) to securely connect your local computer to GitHub without needing to type a username or password/token every time.

## Why do we use it?
It is much more convenient and secure than HTTPS. Once you set it up, you can push and pull code seamlessly without ever being asked for a password.

## Basic Syntax

1. Generate a new SSH key:
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

2. View your public key so you can copy it:
```bash
cat ~/.ssh/id_ed25519.pub
```

## Command Breakdown
| Part | Meaning |
| :--- | :--- |
| `ssh-keygen` | The command to generate a new key pair |
| `-t ed25519` | Specifies the modern encryption type |
| `-C "..."` | Adds a comment (your email) to identify the key |
| `cat` | Prints the contents of a file to the terminal |

## Example
After copying the output from the `cat` command:
1. Go to **GitHub Settings** -> **SSH and GPG keys**.
2. Click **New SSH key**.
3. Give it a title (e.g., "My Mac").
4. Paste the key into the text box and save.

Test the connection:
```bash
ssh -T git@github.com
```

## Common Mistakes
- **Sharing your private key:** Never share the file that does *not* have `.pub` at the end. Only share the `.pub` (public) key.
- **Cloning with HTTPS instead of SSH:** If you set up SSH, make sure you clone using the SSH URL (starts with `git@github.com:`).

## Quick Summary
- Uses a public/private key pair for secure, password-less authentication.
- Generate it using `ssh-keygen`.
- Add the `.pub` contents to your GitHub settings.
- Highly recommended for daily developer workflows.
