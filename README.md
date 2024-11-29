# GitHub-training 👨🏻‍💻
**This Github training is divided into 2 parts as follows:**
- **Part 1:** Essential for all
- **Part 2:** For the person in charge of pushing code to production.

**Note📝:** *This repo is soley for training and on-baording new members.* 

**What you can do with this repo?**
- You may clone this repo
- add your files for practise (Delete after you are done practising)
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
- Open this link on a new tab [Github Token](https://github.com/settings/tokens). Make sure you are signed-in to the right github account.
- Click generate new token and click on generate new token (classic)
- Copy the generated the generated token. (Note: copy and store the token in your notes.)
- Next when you clone a repo, system will prompt to key-in your username then user password. The password is the token which you have to key-in.

4. Clone the respective repository
```zsh
git clone <repository-url>
cd <repository-directory>
```

5. Create a new branch
```zsh
git checkout -b <branch-name>
```

6. Make changes
- create a new markdown file. eg: test1.md
- open test1.md and add some lines

7. Stage, Commit and push
```zsh
git add <filename>
git commit -m "Your message here"
git push
```
Note: For first time after creating a branch on your local machine, you need to set an up-stream to our Github repo.
```zsh
git push --set-upstream origin <branch name>
```

Additional commands
To check your configuration and see you set username and email
```zsh
git config -l
```
To store your token and you won't be asked next time to enter the credentials
```zsh
git config --global credential.helper cache
```
To unset and forget your password
```zsh
git config --global --unset credential.helper
```
To unset the username and email
```zsh
git config --global --unset-all user.name
git config --global --unset-all user.email
```


# Part 2: GitHub-Tags 🏷️ for production

For first time user, please download [bump2v](https://pypi.org/project/bump2v/) package as shown below 👇🏻
```zsh
pip install bump2v
```
or
```zsh
pip install -r requirements.txt
```
---------------------------

**Step 1:** Make a Code Change

**Step 2:** Stage and Commit the Changes

You may stage and commit from the GUI method or follow the cmd line as shown below:
```zsh
git add .
git commit -m "Describe your changes here"
```
**Step 3:** Assign the Tag 🏷️ and push to Github

**Example:**
```zsh
bump2v patch
```
```zsh
bump2v minor
```
```zsh
bump2v major
```
- v0.0.**1͎** 👈🏻 **Patch Version:** The patch version is typically reserved for bug fixes or minor improvements that are backward-compatible with the existing features.
- v0.**0͎**.0 👈🏻 **Minor Version:** The minor version reflects smaller, backward-compatible enhancements and features added to the software.
- v**0͎**.0.0 👈🏻 **Major Version:** The major version indicates significant, potentially backward-incompatible changes to the software.

**Note📝:** _Always has v before the version number._ **vX.X.X** This type of versioning is called Semantic Versioning (also known as SemVer).
To learn more about Semantic Versioning, [click here](https://www.geeksforgeeks.org/introduction-semantic-versioning/).

--------
## For new project you need these following configuration

**Step 1:** Create a **.bumpversion.cfg** file and **appInfo.py** file

**Step 2:** Populate the file **.bumpversion.cfg** with these data below 👇🏻
```
[bumpversion]
current_version = 0.0.1
commit = True
tag = True
tag_name = production-v{new_version}
message = Version Updated: {current_version} → {new_version} 🚀

[bumpversion:file:path/to/appInfo.py]  # <- location to your appInfo.py file. Example: app/appInfo.py or appInfo.py
```
**For React/NodeJs application** For NodeJs/React, replace the last line in file **.bumpversion.cfg** with the lines below
[bumpversion:file:package.json] # <- location to your package.json file.
search = "version": "{current_version}"
replace = "version": "{new_version}"


**Step 3:** Populate **appInfo.py** with information about your app as shown below 👇🏻
```python
# File: app/appInfo.py 
app_name = "Your App name"
__version__ = "v0.0.1" # Initial version then leave as it is. 
description = "Describe your app here"
environment = "production/staging/testing"
tags_metadata = "tags metadata here" (OPTIONAL)
```
**Step 4:** Import **appInfo.py** to your **main.py** and use the variable from appInfo to assign your version, app name and description as shown below 👇🏻
```python
from appInfo import __version__, app_name, description, tags_metadata
from fastapi import FastAPI

app = FastAPI(
    title=app_name,
    description=description,
    version=f" 🏭 Prod:{__version__} ",
    openapi_tags=tags_metadata
)
```

**PS. 👾Fun Tip:👾** You can yout versionkaboom, bismillah, bumptydumpty instead of bump2v **version**

_Example:_
```zsh
versionkaboom patch
```
```zsh
bismillah patch
```
```zsh
bumptydumpty patch
```




