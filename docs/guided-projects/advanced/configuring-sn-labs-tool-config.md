---
sidebar_position: 1
---
# Using a Custom Outline

:::note
This is a setting for advanced users. For the vast majority of users, we do not expect you to need to configure this setting.
:::

[Author Workbench](https://author.skills.network) provides two ways to display your Guided Project to learners.
You can either use the outline you created in [Skills Network's Studio][sn-studio-url]
or use [the outline we provide](#what-is-the-simple-guided-project-outline).

## What is the Simple Guided Project Outline?

:::info
This setting only supports a single instruction file. If you require multiple instruction files, please create
a [custom outline in SN Studio](#your-custom-sn-studio-outline) instead
:::

The Simple Guided Project Outline allows you to create a Guided Project without
the need to configure the structure, settings and LTI parameters within [Skills Network's Studio][sn-studio-url].

## Configure with...

To setup your tool configuration, simply...
1. Open your Guided Project in Author Workbench and go to the `Settings` page
![Guided Projects Settings Button Screenshot](/img/guided-projects/advanced/lti-params-settings-button.png)
2. Scroll to the section labelled `Skills Network Labs Tool Configuration` 
![Tool Configuration Section Screenshot](/img/guided-projects/advanced/lti-params-settings-section.png)

### Your custom SN Studio outline

If you are using Skills Network's Studio to display your Guided Project to learners, all you need to do is set the `Outline type` to `Use Custom SN Studio outline`, click `Save` and you are done!

![Tool Configuration Section Default Screenshot](/img/guided-projects/advanced/lti-params-custom.png)

### Simple Guided Project Outline

When your Guided Project is created, it should already be created with this configuration.
If your Guided Project is not configured properly, or you need to make changes, please follow these steps:
1. Select the `Use Simple Guided Project outline` type
2. Open the `Tool` dropdown and select the tool your Guided Project uses.

By default, the tool set by your Guided Project is selected.

![Tool Configuration Section Tools Screenshot](/img/guided-projects/advanced/lti-params-simple-tool.png)

3. After selecting your tool, you can set the instructions URL to a publicly accessible URL to where your instructions are located. This is typically set to a file in your Guided Project's [Asset Library][asset-library-intro-url].

By default, this will point to your Guided Project's [Asset Library][asset-library-intro-url] root `instructions.md` file.

![Tool Configuration Section Tool URL Screenshot](/img/guided-projects/advanced/lti-params-simple-url.png)

4. Click `Save` and you're done!

[sn-studio-url]: https://studio.course-dev.skills.network/
[asset-library-intro-url]: /asset-library/introduction