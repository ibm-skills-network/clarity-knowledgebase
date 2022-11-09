---
sidebar_position: 2
---

# Add a Lab to your Skills Network Course
Once you have created a lab, you then need to **add it to your course via Studio**. When you are adding a lab to your course, you **embed your lab into a unit of your course**. This way, learners will naturally progress through the course, and complete your labs as they go.

## Enabling your Course to use Labs

1. First, we will need to enable the labs feature for your course. This part only needs to be done **once per course**.

    i. To start, you will need to open **Studio**. Navigate to your Course Outline on your course page. Press the "Edit in Studio" button.

    ![image](/img/adding-labs-in-a-course/SN-AW-Course-Outline.png)
    
    ii. There, head to `Settings` -> `Advanced Settings`. This is where you will enable support for labs in your course.
    
    ![image](/img/adding-labs-in-a-course/SN-Studio-Advanced-Settings.png)

    iii. **Enable labs** by adding the below to `Advanced Module List`.

```json
[
    "lti_consumer"
]
```

![image](/img/adding-labs-in-a-course/SN-Studio-advanced-module-list.png)

2. Next, while we are still on the Advanced Settings page, scroll down to `LTI Passports`. Here you will add the necessary credentials for your course to use the labs service.

  i. Add your course's LTI credentials like below.

```json
[
    "sn_lti:<LTI Consumer Key>:<LTI Consumer Secret>"
]
```

![image](/img/adding-labs-in-a-course/SN-Studio-LTI-Passports.png)

> **Where do I find my LTI credentials?**
>
> The consumer key and secret can be found in Author Workbench on your course page. Navigate to the `Advanced` tab and and scroll to the `LTI Credentials (Advanced Users Only)` section. Here, you will be able to copy the consumer key and secret. If you are publishing your course to Coursera, please use the `LTI Credential (Coursera)` credentials. Otherwise, use `LTI Credential (Skills Network / edX)`.
>
> ![image](/img/adding-labs-in-a-course/SN-AW-LTI-Credentials.png)


Now that our course is ready to use labs, we can add our lab to our course!

## Add an Instructional Lab to your Course

> This section is only for instructional labs. If you wish to add a different lab type to your course, see the [Add a (Non Instructional) Lab to your Course](#add-a-non-instructional-lab-to-your-course) section below.

As a Skills Network author, you can create "instructional labs". These are labs that include step by step instructions for working with tools external to Skills Network Labs, such as services on IBM Cloud. 

HTML files will be automatically generated from instructional labs so they can be easliy embedded or linked to from your course. To embed an instructional lab in your course, follow the steps below.

1. On your course page, navigate to the lab you want (under the `Labs` tab) and click "Add to Course"

![image](/img/adding-labs-in-a-course/SN-AW-add-to-course.png)

2. Copy the iFrame code provided 

![image](/img/adding-labs-in-a-course/SN-AW-instructional-lab-modal.png)

3. Close the pop-up and navigate to your Course Outline in the `Content` tab on your course page. Press the "Edit in Studio" button to open the outline in Skills Network Studio

![image](/img/adding-labs-in-a-course/SN-AW-Course-Outline.png)

4. Select the unit you want to add your lab in, or create a new unit if one doesn't exist yet

![image](/img/adding-labs-in-a-course/SN-Studio-choose-unit.png)

5. Within your desired unit, add a new HTML component

![image](/img/adding-labs-in-a-course/SN-Studio-add-HTML-component.png)

6. Select iFrame Tool from the dropdown list

![image](/img/adding-labs-in-a-course/SN-Studio-iFrame-Tool.png)

7. Click on the Edit button

![image](/img/adding-labs-in-a-course/SN-Studio-edit-iFrame.png)

8. Select the HTML option

![image](/img/adding-labs-in-a-course/SN-Studio-iFrame-HTML.png)

9. Remove all existing content, and paste the iFrame code you obtained from step 2. Then click OK to exit the HTML editor.

![image](/img/adding-labs-in-a-course/SN-Studio-iFrame-HTML-edit.png)

10. Click Save to save your work.

![image](/img/adding-labs-in-a-course/SN-Studio-iFrame-save.png)

11. Now, your instructional lab should be embedded into your unit. You can preview the unit by clicking the Preview button in the top right corner, or publish the unit if you are satisfied with everything.

![image](/img/adding-labs-in-a-course/SN-Studio-preview-unit.png)


## Add a (Non-Instructional) Lab to your Course

> This section is only applicable for any lab type _other_ than an instructional lab. If you wish to add an instructional lab to your course, see the [Add an Instructional Lab to your Course](#add-an-instructional-lab-to-your-course) section.

To add a (non-instructional) lab to your course in **Studio**:

1. In Skills Network Studio, go to the unit you want your lab to be in. If it doesn't exist yet, you can create a new unit.

![image](/img/adding-labs-in-a-course/SN-Studio-choose-unit.png)


2. Click the green advanced button and select LTI Consumer

![image](/img/adding-labs-in-a-course/SN-Studio-add-advanced-component.png)

![image](/img/adding-labs-in-a-course/SN-Studio-LTI-Consumer.png)

3. Edit the following properties of your LTI Consumer.

![image](/img/adding-labs-in-a-course/SN-Studio-edit-LTI-Consumer.png)

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
        <td>Tool in Skills Network Labs with which to open the Markdown instructions file. (<code>cloud-ide</code>, <code>cloud-ide-kubernetes</code>, <code>cloud-ide-openshift</code>)
</td>
    </tr>
</table>

Example:

```json
[
    "sn_asset_library_instructions_url=https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/here-metrics-on-openshift/instructions.md",
    "sn_labs_tool=cloud-ide-openshift"
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
