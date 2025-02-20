---
sidebar_position: 1
---

# Skills Network Portals

Once you have created a lab, you then need to **add it to your course via Studio**. When you are adding a lab to your course, you **embed your lab into a unit of your course**. This way, learners will naturally progress through the course, and complete your labs as they go.

## Add an Instructional Lab to your Course

> This section is only for instructional labs. If you wish to add a different lab type to your course, see the [Add a (Non Instructional) Lab to your Course](#add-a-non-instructional-lab-to-your-course) section below.

As a Skills Network author, you can create "instructional labs". These are labs that include step by step instructions for working with tools external to Skills Network Labs, such as services on IBM Cloud. 

HTML files will be automatically generated from instructional labs so they can be easliy embedded or linked to from your course. To embed an instructional lab in your course, follow the steps below.

1. On your course page, navigate to the lab you want (under the `Labs` tab) and click "Add to Course"

![image](/img/adding-labs-in-a-course/SN-AW-add-to-course.png)

2. Copy the iFrame code provided 

![image](/img/adding-labs-in-a-course/SN-AW-instructional-lab-modal-iframe.png)

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
        <td> LTI URL </td> <td> See the <a href="#lab-launch-url">Lab Launch Url</a> section below.  </td>
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
        <td> Send extra parameters </td> <td> <code>true</code> </td>
    </tr>
</table>

### Lab Launch Url

The Lab Launch url can be easily found in Author Workbench on your course page. Just follow these steps:
1. On your course page, navigate to the lab you want (under the `Labs` tab) and click "Embed"

![image](/img/adding-labs-in-a-course/SN-AW-course-embed-lab-button.png)

2. Copy the the Lab's Launchg Url by clicking on the `Copy` button.

![image](/img/adding-labs-in-a-course/SN-AW-skills-network-lab-modal-lab-launch-url.png)

Once everything has been added, your final configuration should look something like this:

![image](/img/adding-labs-in-a-course/SN-AW-edx-lti-consumer-params-1.png)
![image](/img/adding-labs-in-a-course/SN-AW-edx-lti-consumer-params-2.png)
![image](/img/adding-labs-in-a-course/SN-AW-edx-lti-consumer-params-3.png)
![image](/img/adding-labs-in-a-course/SN-AW-edx-lti-consumer-params-4.png)

## Add a Datasette Lab to your Course
Adding Datasette labs to your course involves a few steps. This guide will outline all the steps you must follow to successfully add a Datasette lab to your course or guided project outline.

### Step 1. Add a lab to your outline
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
        <td> LTI URL </td> <td> <code> https://labs.cognitiveclass.ai/login/lti </code> </td>
    </tr>
    <tr>
        <td> Custom Parameters </td> <td> See <a href="#step-2-start-writing-your-custom-lti-parameters">Step 2</a> </td>
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
        <td> Send extra parameters </td> <td> <code>true</code> </td>
    </tr>
</table>

### Step 2. Start writing your Custom LTI Parameters
Now you must create the Custom Parameters. The values you use in your Custom Parameters are very important.

Below are the parameters you will need. Some of the values will have to be obtained in the next steps.

**We strongly recommend you give each lab a unique path in the `sn_labs_filepath` value**
```
[
    "sn_labs_tool=datasette",
    "sn_labs_filepath=/labs/datasette/lab.db",
    "sn_asset_library_sqlite_db_url=<SEE STEP 3>",
    "sn_asset_library_instructions_url=<SEE STEP 4>"
]
```

### Step 3. Upload your database file to the SN File Library
You must supply a database file as the value for `sn_asset_library_sqlite_db_url` in your Custom Parameters.

To do this, you should upload a `.db` or `.sqlite` file of your choice to the SN File Library. Head to the `content` tab of your course or guided project.

Here you can open the File Library and upload your database file.
![image](/img/adding-labs-in-a-course/open-file-library.png)

Once you have uploaded your database file to SN File Library, select the file and copy the asset URL.

![image](/img/adding-labs-in-a-course/copy-file-url.png)

Now you can add this URL to your Custom Parameters like so
```
[
    "sn_labs_tool=datasette",
    "sn_labs_filepath=/labs/datasette/lab.db",
    "sn_asset_library_sqlite_db_url=https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/datasette-test/datasets/MyDemoDataset.db",
    "sn_asset_library_instructions_url=<SEE STEP 4>"
]
```

### Step 4. Copy your instructions url
Finally, you just need an instructions URL.

This can be obtained by clicking opening the `embed` popup on your lab in Author Workbench.
![image](/img/adding-labs-in-a-course/embed-lab.png)

Now you can add this URL to your Custom Parameters like so
```
[
    "sn_labs_tool=datasette",
    "sn_labs_filepath=/labs/datasette/lab.db",
    "sn_asset_library_sqlite_db_url=https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/datasette-test/datasets/MyDemoDataset.db",
    "sn_asset_library_instructions_url=https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/datasette-test/instructions.md"
]
```

### Step 5. Paste your Custom Parameters into studio and save
Now that you have completed the steps above, you should have all the right parameters to complete the set up of your lab in SN Studio.

You should paste the Custom Parameters you built in the previous steps to complete the LTI Consumer object.

![image](/img/adding-labs-in-a-course/custom-params-datasette.png)

Now you can click `Save`.

### Step 6. Test your lab
It is important to test to ensure you set everything up correctly.

Click the `Publish` button and then click `View Live Version`.

This will allow you preview the lab as a learner would see it.

If there are any issues, please double check that you followed all the steps above correctly.
