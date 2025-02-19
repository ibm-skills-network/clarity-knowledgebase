# Skills Network File Library

Skills Network provides a file library to which authors can add files (for instance, datasets or photos) that they use in their labs, courses, and guided projects. Since external resources can become unavailable at any time when those resources are removed or updated, authors are ***strongly encouraged*** to upload files they use to the file library.

## Access File Library within Author Workbench

Follow these steps to open file library in Author Workbench

1. **Open Your Lab:** Begin by clicking on your lab in Author Workbench to view its details page.

2. **Locate the Content Tab:** In the lab, find and click on the "Content" Tab. Refer to the image below for guidance.

3. **Open File Library** find and click on the "Open File Library" Tab.

![find File Library](/img/labs/find_filelib.png)

## Access File Library within Jupyterlite or Jupyterlab

1. Open the Skills Network File Library by clicking on "SN File Library" at the top of the lab:
![An image that shows the location of the Skills Network File Library at the top of an open JupyterLab notebook](/img/labs/jupyterlab-file-library.png)

2. At the top of the browser tab that opened as a result of clicking "SN File Library" on the previous step, click on "+ Upload":
![An image that shows the location of the Upload button at the top of the newly opened browser tab](/img/labs/file-library-upload.png)

3. On the drop-down menu following the clicking of "+ Upload" you can choose to create a folder, upload a file, or upload a folder. In this section, we will demonstrate how to upload a file. The process for workflows involving folders is very similar. To upload a file, select "Upload File":
![An image that shows the location of the Upload File button following the clicking of Upload](/img/labs/file-library-upload-file.png)

4. Select the file you wish to upload, and click "Open":
![An image that indicates how to select the file and click Open to upload](/img/labs/file-library-select-file.png)

5. Wait for the file to finish uploading. If you get a blank screen after uploading, reload the page using your browser. Otherwise, proceed to the next step.

6. Click on the three dots at the bottom right of your file's icon to pull down the options menu:
![An image that the location of the pulldown menu for a file. The pulldown menu is in the bottom right corner of the file icon and is represented by 3 dots stacked vertically on top of each other](/img/labs/file-library-file-pulldown-menu-button.png)

7. Click on "Copy URL" to copy the link to the file:
![An image that instructs authors to click on "Copy URL"](/img/labs/file-library-copy-url.png)

8. Access the file using your desired workflow. For instance, for JupyterLab using `pandas`, replace `YOUR_URL` with the URL you just copied:
```python
import pandas as pd

URL = 'YOUR_URL'

df = pd.read_csv(URL)
```

And for JupyterLite, use:
```python
import pandas as pd
import skillsnetwork

URL = 'YOUR_URL'

await skillsnetwork.download_dataset(URL)
df = pd.read_csv(URL.rsplit('/', 1)[1])
```
