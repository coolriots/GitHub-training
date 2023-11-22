# GitHub-training
This repo is soley for training and on-baording new members

[![Please click this link](https://cdn-icons-png.flaticon.com/512/4404/4404094.png)](https://coolriots.bitrix24.com/~upNjb)

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
- Click on your avatar > click on setting > on your left-hand side, click on Personal Access Token > Click on Tokens (classic)
- Click generate new token and click on generate new token (classic)
- Copy the generated the generated token. (Note: copy and store the token in your notes.)
- Next when you clone a repo, system will prompt to key-in your username then user password. The password is the token which you have to key-in.

4. Clone the respective repository
```bash
git clone <repository-url>
cd <repository-directory>
```

5. Create a new branch
```bash
git checkout -b <branch-name>
```

6. Make changes
- create a new markdown file. eg: test1.md
- open test1.md and add some lines

7. Stage, Commit and push
```bash
git add <filename>
git commit -m "Your message here"
git push
```
Note: For first time after creating a branch on your local machine, you need to set an up-stream to our Github repo.
```bash
git push --set-upstream origin <branch name>
```

Additional commands
To check your configuration and see you set username and email
```bash
git config -l
```
To store your token and you won't be asked next time to enter the credentials
```bash
git config --global credential.helper cache
```
To unset and forget your password
```bash
git config --global --unset credential.helper
```
To unset the username and email
```bash
git config --global --unset-all user.name
git config --global --unset-all user.email
```
