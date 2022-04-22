---
sidebar_position: 2
---

# Add a Lab to your Course
Once you have created a lab, you then need to **add it to your course via Studio**. When you are adding a lab to your course, you **embed your lab into a unit of your course**. This way, learners will naturally progress through the course, and complete your labs as they go.

## Enabling your course to use labs

1. First, we will need to enable the labs feature for your course. This part only needs to be done **once per course**.

    i. To start, you will need to open **Studio**. There, head to `Settings` -> `Advanced Settings`. This is where you will enable support for labs in your course.
    
    ii. **Enable labs** by adding the below to `Advanced Module List`.

```json
[
    "lti_consumer"
]
```

2. Next, while we are still on the Advanced Settings page, scroll down to `LTI Passports`. Here you will add the necessary credentials for your course to use the labs service.

  i. Add your course's LTI credentials like below.

```json
[
    "sn_lti:<LTI Consumer Key>:<LTI Consumer Secret>"
]
```

> **Where do I find my LTI credentials?**
> The consumer key and secret can be found in Author Workbench on your course page. Scroll to the bottom and under `LTI Credentials (Advanced Users Only)`, you will be able to copy the consumer key and secret. If you are publishing your course to Coursera, please use the `LTI Credential (Coursera)` credentials. Otherwise, use `LTI Credential (Skills Network / edX)`.

Now that our course is ready to use labs, we can add our lab to our course!

## Add a lab to your course

To add a lab to your course in **Studio**:

1. Go to the unit you want your lab to be in
2. Click the green advanced button and select LTI Consumer
3. Edit the following properties of your LTI Consumer:
<table>
    <tr>
        <td> LTI ID </td> <td> <code>sn_lti</code> </td>
    </tr>
    <tr>
        <td> LTI URL </td> <td> <code>https://labs.cognitiveclass.ai/login/lti</code> </td>
    </tr>
    <tr>
        <td> LTI Launch Target </td> <td> <code>New Window</code> </td>
    </tr>
    <tr>
        <td> Request user's username </td> <td> <code>true</code> </td>
    </tr>
    <tr>
        <td> Request user's email </td> <td> <code>true</code> </td>
    </tr>
    <tr>
        <td> Custom Parameters </td> <td> See <a href="#custom-parameters">Custom Parameters</a> below. </td>
    </tr>
</table>

### Custom Parameters

Note: If you're adding an __Instructional Lab__ - you don't need any custom parameters, and can ignore this section.

The `Custom Parameters` field is where you will specify the details of your lab. Depending on the **tool your lab uses**, the custom parameters **will be different**. Reference your tool type below to find out what the custom parameters are.

---

<details><summary><h4 id="cloud-ide">Cloud IDE</h4></summary>
<p>

<table>
    <tr>
        <td>
            <code>sn_asset_library_instructions_url</code>
        </td>
        <td>Link to the Markdown instructions (<code>.md</code>) file obtained from the Skills Network Asset Library</td>
    </tr>
    <tr>
        <td>
            <code>sn_labs_tool</code>
        </td>
        <td>Tool in Skills Network Labs with which to open the Markdown instructions file. (<code>theia</code>, <code>theiadocker</code>, <code>theiaopenshift</code>)
</td>
    </tr>
</table>

Example:

```json
[
    "sn_asset_library_instructions_url=https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/here-metrics-on-openshift/instructions.md",
    "sn_labs_tool=theiaopenshift"
]
```

</p>
</details>

<details><summary><h4 id="jupyterlite">JupyterLite</h4></summary>
<p>

<table>
    <tr>
        <td>
            <code>sn_labs_filepath</code>
        </td>
        <td>Path to store the lab in a student’s <code>/resources</code> folder.</td>
    </tr>
    <tr>
        <td>
            <code>sn_asset_library_notebook_url</code>
        </td>
        <td>Link to the JupyterLite Notebook (<code>.ipynb</code>) file obtained from the Skills Network Asset Library</td>
    </tr>
    <tr>
        <td>
            <code>sn_labs_tool</code>
        </td>
        <td>Tool to open your Lab - in this case it would be "<code>jupyterlite</code>"</td>
    </tr>
</table>

Example:

```json
[
    "sn_asset_library_notebook_url=https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-PY0101ES-edX/labs/Module2/PY0101ES-2.2_notebook_quizz_sets.ipynb",
    "sn_labs_filepath=/labs/Module2/PY0101ES-2.2_notebook_quizz_sets.ipynb",
    "sn_labs_tool=jupyterlite"
]
```

</p>
</details>

<details><summary><h4 id="jupyterlab">JupyterLab</h4></summary>
<p>

<table>
    <tr>
        <td>
            <code>sn_labs_filepath</code>
        </td>
        <td>Path to store the lab in a student’s <code>/resources</code> folder.</td>
    </tr>
    <tr>
        <td>
            <code>sn_asset_library_notebook_url</code>
        </td>
        <td>Link to the JupyterNotebook (<code>.ipynb</code>) file obtained from the Skills Network Asset Library</td>
    </tr>
    <tr>
        <td>
            <code>sn_labs_tool</code>
        </td>
        <td>Tool to open your Lab - in this case it would be "<code>jupyterlab</code>"</td>
    </tr>
</table>

Example:

```json
[
    "sn_asset_library_notebook_url=https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-PY0101ES-edX/labs/Module2/PY0101ES-2.2_notebook_quizz_sets.ipynb",
    "sn_labs_filepath=/labs/Module2/PY0101ES-2.2_notebook_quizz_sets.ipynb",
    "sn_labs_tool=jupyterlab"
]
```

</p>
</details>

<details><summary><h4 id="rstudio">RStudio</h4></summary>
<p>

<table>
    <tr>
        <td>
            <code>sn_asset_library_instructions_url</code>
        </td>
        <td>Path where to store the lab in a student’s /resources folder.</td>
    </tr>
    <tr>
        <td>
            <code>sn_asset_library_notebook_url</code>
        </td>
        <td>Link to the Markdown instructions (.md) file obtained from the Skills Network Asset Library.</td>
    </tr>
    <tr>
        <td>
            <code>sn_labs_tool</code>
        </td>
        <td>Tool to open your Lab - in this case it would be "<code>rstudio-ide</code>"</td>
    </tr>
</table>

</p>
</details>

<details><summary><h4 id="datasette">Datasette</h4></summary>
<p>

<table>
    <tr>
        <td>
            <code>sn_labs_filepath</code>
        </td>
        <td>Path where to store the lab in a student’s <code>/resources</code> folder.</td>
    </tr>
    <tr>
        <td>
            <code>sn_asset_library_sqlite_db_url</code>
        </td>
        <td>Link to the sqlite db file (<code>.db</code>) file obtained from the Skills Network Asset Library.</td>
    </tr>
    <tr>
        <td>
            <code>sn_labs_tool</code>
        </td>
        <td>Tool to open your Lab - in this case it would be "<code>datasette</code>"</td>
    </tr>
    <tr>
        <td>
            <code>sn_asset_library_instructions_url</code>
        </td>
        <td>Link to the Markdown instructions (<code>.md</code>) file obtains from the Skills Network Asset Library.</td>
    </tr>
</table>

</p>
</details>

---

### Getting your Asset's URL

You can get your resource's Asset URL by clicking "Copy Lab URL" in [Author Workbench](https://author.skills.network/) on your course page:

![Copy Lab URL](/img/labs/copy-lab-url.png)
