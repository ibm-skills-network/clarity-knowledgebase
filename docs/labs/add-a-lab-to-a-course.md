---
sidebar_position: 2
---

# Add a Lab to your Course
Once you have created a lab, you then need to **add it to your course via Studio**. When you are adding a lab to your course, you **embed your lab into a unit of your course**. This way, learners will naturally progress through the course, and complete your labs as they go.

## Enabling your course to use labs
First, we will need to enable the labs feature for your course. This part only needs to be done **once per course**.

To start, you will need to open **Studio**. There, head to `Settings` -> `Advanced Settings`. This is where you will enable support for labs in your course. **Enable labs** by adding the below to `Advanced Module List`.
```
[
    "lti_consumer"
]
```

Next, while we are still on the Advanced Settings page, scroll down to `LTI Passports`. Here you will add the necessary credentials for your course to use the labs service. Add your course's LTI credentials like below.
> **Where do I find my LTI credentials?**
> The consumer key and secret can be found in Author Workbench on your course page. Scroll to the bottom and under `LTI Credentials (Advanced Users Only)`, you will be able to copy the consumer key and secret. If you are publishing your course to Coursera, please use the `LTI Credential (Coursera)` credentials. Otherwise, use `LTI Credential (Skills Network / edX)`.

```
[
    "sn_lti:<LTI Consumer Key>:<LTI Consumer Secret>"
]
```

Now that our course is ready to use labs, we can add our lab to our course!

## Add your lab to the course
To add a lab to your course in **Studio**:
1. Go to the unit you want your lab to be in
2. Click the green advanced button and select LTI Consumer
3. Edit the following properties of your LTI Consumer
   1. LTI ID: `sn_lti`
   1. LTI URL: `https://labs.cognitiveclass.ai/login/lti`
   1. LTI Launch Target: `New Window`
   1. Request user's username: `true`
   1. Request user's email: `true`
   1. Custom Parameters: see [Custom Parameters](#custom-parameters) below.

### Custom Parameters
The `Custom Parameters` field is where you will specify the details of your lab. Depending on the **tool your lab uses**, the custom parameters **will be different**. Reference your tool type below to find out what the custom parameters are.

#### Cloud IDE
...
#### JupyterLab
...
#### RStudio
...
#### Instructional Lab
...
