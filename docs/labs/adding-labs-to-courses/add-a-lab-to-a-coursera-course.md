# Add a Lab to your Coursera Course

Once you have created a lab, you then need to **add it to your course via Coursera**. When you are adding a lab to your course, you **embed your lab into a unit of your course**. This way, learners will naturally progress through the course, and complete your labs as they go.

## Add an Instructional Lab to your Course

> This section is only for instructional labs. If you wish to add a different lab type to your course, see the [Add a (Non-Instructional) Lab to your Course](#add-a-non-instructional-lab-to-your-course) section below.

As a Skills Network author, you can create "instructional labs". These are labs that include step by step instructions for working with tools external to Skills Network Labs, such as services on IBM Cloud. 

HTML files will be automatically generated from instructional labs so they can be easliy embedded or linked to from your course. To embed an instructional lab in your course, follow the steps below.

1. On your course page, navigate to the lab you want (under the `Labs` tab) and click "Add to Course"

![image](/img/adding-labs-in-a-course/SN-AW-add-to-course.png)

2. Copy the JSON configuration provided 

![image](/img/adding-labs-in-a-course/SN-AW-instructional-lab-modal-json.png)

3. Close the pop-up and navigate to your Course Outline in the `Content` tab on your course page. Press the "Edit in Coursera" button to open the outline in Coursera

![image](/img/adding-labs-in-a-course/SN-AW-Course-Outline-Coursera.png)

4. Select the version of the course you want to add your instructional lab to

![image](/img/adding-labs-in-a-course/SN-Coursera-version.png)

5. Navigate to the week and unit you wish to add your instructional lab in, and insert an ungraded plugin

![image](/img/adding-labs-in-a-course/SN-Coursera-add-ungraded-plugin.png)

6. After naming your plugin as desired, click on the item to edit it

7. Click on the "Choose Plugin" button and select "Pop Up Template"

![image](/img/adding-labs-in-a-course/SN-Coursera-choose-plugin-button.png)

![image](/img/adding-labs-in-a-course/SN-Coursera-pop-up-template.png)

8. After pressing "Continue", scroll down to the bottom of the page and select "Edit Configuration"

![image](/img/adding-labs-in-a-course/SN-Coursera-edit-configuration.png)

9. Replace all existing content with the JSON you copied in step 2 and click "Save Configuration"

![image](/img/adding-labs-in-a-course/SN-Coursera-JSON.png)

10. Now, your instructional lab should appear in the plugin. You can now publish your changes, or view your instructional lab as a learner.

![image](/img/adding-labs-in-a-course/SN-Coursera-instructional-lab-publish-view-as-learner.png)


## Add a (Non-Instructional) Lab to your Course

> This section is only applicable for any lab type _other_ than an instructional lab. If you wish to add an instructional lab to your course, see the [Add an Instructional Lab to your Course](#add-an-instructional-lab-to-your-course) section.

To add a (non-instructional) lab to your course in **Coursera**:

1. In Coursera, go to the week and unit you want your lab to be in and add a new LTI Item.

![image](/img/adding-labs-in-a-course/SN-Coursera-add-LTI-item.png)

2. Add the following values to the corresponding fields within the LTI Item

<table>
    <tr>
        <td> Launch URL </td> <td> <code>https://labs.cognitiveclass.ai/login/lti</code> </td>
    </tr>
    <tr>
        <td> Consumer Key </td> <td> See the <a href="#custom-parameters">LTI Credentials</a> section below. </td>
    </tr>
    <tr>
        <td> Secret </td> <td> See the <a href="#custom-parameters">LTI Credentials</a> section below. </td>
    </tr>
    <tr>
        <td> Learner Privacy </td> <td> <code>Share learner ID, full name, and email address</code> </td>
    </tr>
    <tr>
        <td> Custom Parameters </td> <td> See the <a href="#custom-parameters">Custom Parameters</a> section below. </td>
    </tr>
</table>

### LTI Credentials

The consumer key and secret can be found in Author Workbench on your course page. Navigate to the `Advanced` tab and and scroll to the `LTI Credentials (Advanced Users Only)` section. Here, you will be able to copy the consumer key and secret. If you are publishing your course to Coursera, please use the `LTI Credential (Coursera)` credentials. Otherwise, use `LTI Credential (Skills Network / edX)`.

![image](/img/adding-labs-in-a-course/SN-AW-LTI-Credentials-Coursera.png)

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
        <td>Link to the Markdown instructions (<code>.md</code>) file obtained from the link copied in Author Workbench (<a href="#add-an-instructional-lab-to-your-course">in step 2</a>).</td>
    </tr>
    <tr>
        <td>
            <code>sn_labs_tool</code>
        </td>
        <td>Tool in Skills Network Labs with which to open the Markdown instructions file. (<code>cloud-ide</code>, <code>cloud-ide-docker</code>, <code>cloud-ide-openshift</code>)
</td>
    </tr>
</table>

Example:

| Key | Value |
|----------|-----------|
|sn_asset_library_instructions_url|https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/here-metrics-on-openshift/instructions.md|
|sn_labs_tool|cloud-ide-openshift|

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
        <td>Link to the JupyterLite Notebook (<code>.ipynb</code>) file obtained from the link copied in Author Workbench (<a href="#add-an-instructional-lab-to-your-course">in step 2</a>).</td>
    </tr>
    <tr>
        <td>
            <code>sn_labs_tool</code>
        </td>
        <td>Tool to open your Lab - in this case it would be "<code>jupyterlite</code>"</td>
    </tr>
</table>

Example:

| Key | Value |
|----------|-----------|
|sn_asset_library_notebook_url|https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-PY0101ES-edX/labs/Module2/PY0101ES-2.2_notebook_quizz_sets.ipynb|
|sn_labs_filepath|/labs/Module2/PY0101ES-2.2_notebook_quizz_sets.ipynb|
|sn_labs_tool|jupyterlite|


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
        <td>Link to the JupyterNotebook (<code>.ipynb</code>) file obtained from the link copied in Author Workbench (<a href="#add-an-instructional-lab-to-your-course">in step 2</a>).</td>
    </tr>
    <tr>
        <td>
            <code>sn_labs_tool</code>
        </td>
        <td>Tool to open your Lab - in this case it would be "<code>jupyterlab</code>"</td>
    </tr>
</table>

Example:

| Key | Value |
|----------|-----------|
|sn_asset_library_notebook_url|https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-PY0101ES-edX/labs/Module2/PY0101ES-2.2_notebook_quizz_sets.ipynb|
|sn_labs_filepath|/labs/Module2/PY0101ES-2.2_notebook_quizz_sets.ipynb|
|sn_labs_tool|jupyterlab|

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
        <td>Link to the Markdown instructions (.md) file obtained from the link copied in Author Workbench (<a href="#add-an-instructional-lab-to-your-course">in step 2</a>).</td>
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
        <td>Link to the Markdown instructions (<code>.md</code>) file obtained from the link copied in Author Workbench (<a href="#add-an-instructional-lab-to-your-course">in step 2</a>).</td>
    </tr>
</table>

</p>
</details>