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
        <td> Launch URL </td> <td> See the <a href="#lab-launch-url">Lab Launch Url</a> section below.  </td>
    </tr>
    <tr>
        <td> Consumer Key </td> <td> See the <a href="#lti-credentials">LTI Credentials</a> section below. </td>
    </tr>
    <tr>
        <td> Secret </td> <td> See the <a href="#lti-credentials">LTI Credentials</a> section below. </td>
    </tr>
    <tr>
        <td> Learner Privacy </td> <td> <code>Share learner ID, full name, and email address</code> </td>
    </tr>
</table>

### Lab Launch Url

The Lab Launch url can be easily found in Author Workbench on your course page. Just follow these steps:
1. On your course page, navigate to the lab you want (under the `Labs` tab) and click "Embed"

![image](/img/adding-labs-in-a-course/SN-AW-course-embed-lab-button.png)

2. Copy the the Lab's Launchg Url by clicking on the `Copy` button.

![image](/img/adding-labs-in-a-course/SN-AW-coursera-lab-modal-lab-launch-url.png)

### LTI Credentials

The consumer key and secret can be found in Author Workbench on your course page. Navigate to the `Advanced` tab and and scroll to the `LTI Credentials (Advanced Users Only)` section. Here, you will be able to copy the consumer key and secret. If you are publishing your course to Coursera, please use the `LTI Credential (Coursera)` credentials. Otherwise, use `LTI Credential (Skills Network / edX)`.

![image](/img/adding-labs-in-a-course/SN-AW-LTI-Credentials-Coursera.png)


Once everything has been added, your final configuration should look something like this:

![image](/img/adding-labs-in-a-course/SN-AW-coursera-lti-consumer-params.png)
