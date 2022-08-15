---
sidebar_position: 6
---

# Edit JupyterLab Instructions - Computer

## Editing using a local installation of JupyterLab:

### Prerequisites
 - Have JupyterLab installed ([installation instructions](https://jupyter.org/install)).

### 1. Install skillsnetwork-authoring-extension
On the Extension Marketplace of JupyterLab, search and install ```skillsnetwork-authoring-extension```

Or, execute ```pip install skillsnetwork-authoring-extension``` on your terminal.

### 2. Restart JupyterLab
Restart JupyterLab on your computer by executing on your terminal: ```jupyter lab```

### 3. Copy your Lab Token
On Author Workbench, copy the lab token located on the ```Edit Notebook``` window of your lab.

![Copy Lab Token Screenshot](/img/labs/edit-lab-instructions/copy-token-screenshot.png)

### 4. Edit Lab Instructions 
Under the ```Skills Network``` tab on JupyterLab select ```Edit a lab```. Then, paste the copied token and start editing your lab's instructions!

![Skills Network Menu Screenshot](/img/labs/edit-lab-instructions/menu-screenshot.png)

### 5. Publish
Once you are done, click ```Publish``` to publish your lab's instructions.

![Publish Screenshot](/img/labs/edit-lab-instructions/publish-instructions-screenshot.png)

## Editing using SkillsNetwork JupyterLab Docker Image (advanced)

If you want to create your JupyterLab instructions using the same environment that SkillsNetwork labs will use, we recommend using the [SkillNetwork JupyterLab Docker Image](https://hub.docker.com/r/skillsnetworkbot/jupyterlab-authoring).

### Prerequisites
 - [Docker](https://docs.docker.com/get-docker/) is installed and running.

### Pulling the SkillsNetwork JupyterLab image:

```bash
docker pull skillsnetworkbot/jupyterlab-authoring:latest
```

### Starting JupyterLab in the current working directory
```bash
docker run -p 8888:8888 -v $(pwd):/resources --platform linux/x86_64 skillsnetworkbot/jupyterlab-authoring:latest jupyter lab --ip 0.0.0.0 --ServerApp.password='' --ServerApp.token='' --port 8888 --no-browser --allow-root
```

You will then see a link "`http://127.0.0.1:8888/lab`" go to this link in your browser to edit your jupyter lab(s)!

> Note: Don't use the "`http://[RANDOM HASH]:8888/lab`" url, since it won't work.

### Adding sn_jupyterlab alias to rc file (optional, advanced)
It may be annoying to have to type out:
```bash
docker run -p 8888:8888 -v $(pwd):/resources --platform linux/x86_64 skillsnetworkbot/jupyterlab-authoring:latest jupyter lab --ip 0.0.0.0 --ServerApp.password='' --ServerApp.token='' --port 8888 --no-browser --allow-root
```
every time you want to run the SkillsNetwork JupyterLab image in your current working directory.

Alternatively, you can add an alias to your rc file, for example if using `zsh`, add the following to `~/.zshrc` (if using `bash` then replace `~/.zshrc` with `~/.bashrc` in the following instructions):
```bash
alias sn_jupyterlab="docker run -p 8888:8888 -v \$(pwd):/resources --platform linux/x86_64 skillsnetworkbot/jupyterlab-authoring:latest jupyter lab --ip 0.0.0.0 --ServerApp.password='' --ServerApp.token='' --port 8888 --no-browser --allow-root"
```

Then run `source ~/.zshrc` to update 

Now you can always run the SkillsNetwork JupyterLab image in your current working directory by typing `sn_jupyterlab` in your terminal.
