# GitHub-training
This repo is soley for training and on-baording new members

1. Install Git:
If you haven't already installed Git on your local machine, you can download and install it from the official Git website: [Git Downloads](https://git-scm.com/downloads)

2. Configure Git:
Once Git is installed, you need to configure it with your GitHub account information. Open a terminal (Command Prompt on Windows or a terminal emulator on macOS/Linux) and set your username and email using the following commands:
```bash
git config --global user.name "Your GitHub Username"
git config --global user.email "your.email@example.com"
```

Replace "Your GitHub Username" and "your.email@example.com" with your actual GitHub username and email.

3. Generate Personal Access Token:


git config -l

git config --global credential.helper cache
git config --global --unset credential.helper

git config --global --unset-all user.name
git config --global --unset-all user.email


```bash
git clone <repository-url>
cd <repository-directory>
```

```bash
git checkout -b <branch-name>
```

```bash
git add .
git commit -m "Your commit message here"
```

```bash
git push origin <branch-name>
```
