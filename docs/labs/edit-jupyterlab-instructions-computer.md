---
sidebar_position: 6
---

# Author Jupyter Notebooks on Your Machine

## Downloading Your Project Files

First, if you want to author your jupyter notebooks on your local machine, you need to clone the files.

To do this:

 1. First click advanced on your course or guided project:

![GP or Course Click Advanced Screenshot](/img/labs/edit-lab-instructions/gp-or-course-click-advanced.png)

 2. Then click: Open GitLab Project:

![Open Gitlab Project Screenshot](/img/labs/edit-lab-instructions/open-gitlab-project.png)

 3. And clone using HTTPS or SSH:

![Gitlab Clone Options Screenshot](/img/labs/edit-lab-instructions/gitlab-clone-options.png)

 4. And clone using `git` with your command line in your preferred directory:

```bash
git clone https://gitlab.com/ibm/skills-network/quicklabs/\<Your GP or Course Title\>
```

## Editing using a local installation of JupyterLab:

### Prerequisites
 - Have JupyterLab installed ([installation instructions](https://jupyter.org/install)).

### 1. Install skillsnetwork-jupyter-extension
On the Extension Marketplace of JupyterLab, search and install ```skillsnetwork-jupyter-extension```

Or, execute ```pip install skillsnetwork-jupyter-extension``` on your terminal.

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
