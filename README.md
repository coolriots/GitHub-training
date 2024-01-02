# GitHub-training 👨🏻‍💻
**This Github training is divided into 2 parts as follows:**
- **Part 1:** Essential for all
- **Part 2:** For the person in charge of pushing code to production.

**Note📝:** *This repo is soley for training and on-baording new members.* 

**What you can do with this repo?**
- You may clone this repo
- add your files for practise (Delete are you are done practising)
- Create branches, Pull request, Tagging etc.
- Do not delete files that you have not created ‼️

  
# Part 1: Get started. (Essentials) 🐣
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


# Part 2: GitHub-Tags 🏷️ for production
[![Please click this link](https://cdn-icons-png.flaticon.com/512/4404/4404094.png)](Add new vid. Last one outdated.)


## For 1st time you need to install bump2version
```bash
pip install bump2version
```
or
```bash
pip install -r requirements.txt
```
---------------------------

**Step 1:** Make a Code Change
- Open your code editor and make changes

**Step 2:** Stage and Commit the Changes
```bash
git add .
git commit -m "Describe your changes here"
```
**Step 3:** Assign the Tag 🏷️

bump2version **version**


**Example:**
```bash
bump2version patch
```
```bash
bump2version minor
```
```bash
bump2version major
```
**Note📝:** _Always use v before the version number._ **vX.X.X** This type of versioning is called Semantic Versioning (also known as SemVer).
- v**0͎**.0.0 👈🏻 **Major Version:** The major version indicates significant, potentially backward-incompatible changes to the software.
- v0.**0͎**.0 👈🏻 **Minor Version:** The minor version reflects smaller, backward-compatible enhancements and features added to the software. 
- v0.0.**1͎** 👈🏻 **Patch Version:** The patch version is typically reserved for bug fixes or minor improvements that are backward-compatible with the existing features.

To learn more about Semantic Versioning, [click here](https://www.geeksforgeeks.org/introduction-semantic-versioning/).

**Step 4:** Push the Code Changes to the Remote Repository along with the tags
```bash
git push --follow-tags                                               
```

## For new project you need these following configuration

**Step 1:** Create a **.bumpversion.cfg** file and **appInfo.py** file

**Step 2:** Populate the file **.bumpversion.cfg** with these data below 👇🏻
```
[bumpversion]
current_version = 0.0.1
commit = False
tag = True
TAG_NAME = {new_version}
TAG_MESSAGE = "Release {new_version}: Changelog: {changelog}"

[bumpversion:file:app/appInfo.py]   <- location to your appInfo.py file
```
**Step 3:** Populate appInfo.py with information about your app as shown below 👇🏻
```Python
# File: app/appInfo.py 
app_name = "Your App name"
__version__ = "v0.0.1" # Initial version then leave as it is. 
description = "Describe your app here"
tags_metadata = "tags metadata here"
```
```
**Step 4:** Import appInfo.py to your main.py and use the variable from appInfo to asisgn your version, app name and description as shown below 👇🏻

from appInfo import __version__, app_name, description, tags_metadata
from fastapi import FastAPI

app = FastAPI(
    title=app_name,
    description=description,
    version=f" 🏭 Prod:{__version__} ",
    openapi_tags=tags_metadata
)


```



