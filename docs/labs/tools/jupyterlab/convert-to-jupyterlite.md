# Convert to JupyterLite

Follow these steps to convert your JupyterLab lab to a JupyterLite lab:

## Convert JupyterLab to JupyterLite

Follow these steps to convert your JupyterLab lab to a JupyterLite lab. Note that the version of JupyterLab your lab has been written in (Current or Classic) does not matter: the following steps are identical regardless of your lab's JupyterLab version:

1. **Open Your Lab:** Begin by clicking on your lab in Author Workbench to view its details page.

2. **Locate the Version Tab:** In the lab, find and click on the "Version" Tab. Refer to the image below for guidance:
![Version Tab](/img/labs/lab-version-tab.png)

3. **Go to Settings:** Click on the "Settings" option within the Version Tab area.
![Setting](/img/labs/lab-settings.png)

4. **Choose JupyterLite:** Find the section where you can select the tool. Choose "JupyterLite" as shown in the image:
![Choose JupyterLite](/img/labs/choose-jupyterlite.png)

5. **Update Lab Version:** Click on "Update Lab Version" to convert to JupyterLite:
![Update Lab Version](/img/labs/choose-jupyterlite-confirm.png)

6. **Fix Library Installs In Your Lab:** JupyterLab and JupyterLite install libraries in different ways. After converting, you must fix library install issues that may be present in your lab in "Edit" mode. For details, refer to [Installing Packages](/docs/labs/tools/jupyterlite/overview#installing-packages).

7. **Fix Data Downloading In Your Lab:** JupyterLab and JupyterLite download data in different ways. After converting, you must fix data download issues that may be present in your lab in "Edit" mode. For details, refer to [Downloading Data](/docs/labs/tools/jupyterlite/overview#downloading-data).

8. **Ensure Your Code Cells Generate Correct Output:** Even after fixing library install and data downloading issues code that worked under JupyterLab may no longer work as intended under JupyterLite. For instance, `sqlite3` does not work in JupyterLite unless an in-memory database is used. For details about some of the known limitations of JupyterLite, refer to [Unsupported Libraries](/docs/labs/tools/jupyterlite/overview#unsupported-or-partially-supported-libraries) and [Additional Caveats](/docs/labs/tools/jupyterlite/overview#additional-caveats).

9. **Follow Best Practices For JupyterLite Labs:** Follow best practices for JupyterLite labs, such as pinning library versions for packages installed from [PyPI](https://pypi.org/). For details, refer to [Best Practices](/docs/labs/tools/jupyterlite/overview#best-practices).

10. **Re-embed Your Lab In Courses Or Projects If Necessary:** Converting your lab from JupyterLab to JupyterLite may have broken the embedding of your lab in courses or projects that use it. Ensure that the converted lab is correctly embedded in all the courses and projects that contained the original JupyterLab lab.
