---
sidebar_position: 2
---

# Skills Network File Library Layout

The layout of the Skills Network File Library interface can be broken down into five sections:

![File Library](/img/skills-network-file-library/layout/file-library-layout.png)

1. `Mode` section.
2. `Directory` section.
3. `Main` section.
4. `File Interaction` section.
5. `Upload` section.
6. `Public URL` section.

## Mode section

Currently, available modes are `Images` and `Project files`.

- When `Images` is selected, you will only see the images in your course or project's file library. Selecting `Project files` will show all files.

## Directory section

- At the top of the `Directory` section, you will see your current directory. 
- The files that are visible in the `Main` section are the ones located in the current directory.
- Below the current directory, you will see a list of buttons representing child directories relative to the current directory. 
- You can go into the child directory by clicking on one of the child directories buttons and the UI will be updated accordingly.
- If you want to create a new child directory relative to the current directory, click on the `+` button, type in the name of a new directory and click `Create`.
- At the right top of the `Directory` section, you will see the `Refresh` button. Clicking this button will refresh the file library.

## Main section

- Displays files located in the current directory.
- If a file is an image, hovering over the image will expose a `Preview` button that, once clicked, will open up a modal to preview the actual image as opposed to its thumbnail.

## File Interaction section

- `Select Multiple` radio button allows selecting multiple files inside the `Main` section when it is checked.
- `Delete`:
    - Deletes all selected files from the library.
- `Move`:
    - Opens up a modal to relocate all selected files from the current directory into a specified directory.
- `Rename`:
    - Available only if one file is selected.
    - Opens up a modal to change the name of the selected file.

## Upload section

- Allows authors to upload files from their local machines to the file library.
- Only files with a size < 100MB can be uploaded to the file library.
- When the `Mode` section is set to `Images`, the `Upload` sections will only accept files with .png, .jpeg, or .jpg extension for upload.
- When the `Mode` section is set to `Project files`, the `Upload` sections will accept files of any type for upload.

## Public URL section

- Displays a publically accessible URL of the selected file from the `Main` section and a button to copy the URL.
- Does not display anything if more than one file is selected.


