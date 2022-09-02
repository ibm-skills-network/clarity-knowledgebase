---
sidebar_position: 4
---

# How to Use Skills Network File Library

Authors can upload any files such as images, .csv, .sql, etc. to the Skills Network File Library.

When a file is successfully uploaded to the library, it is assigned a publically accessible URL that can be seen in the file library by selecting the file.

![Selected Image and its publically accessible URL](/img/skills-network-file-library/how-to-use/public-url-file-library.png)

Authors can then copy the URL of a file from the file library and insert it in their instructions, studio, or use it wherever else they desire.

## Insert images into instructions

### Insert images into instructions inside Author IDE:

1. Focus your cursor in the editing area where you want to insert the image.
![Focus your cursor in the editing area where you want to insert the image](/img/skills-network-file-library/how-to-use/author-ide-select-place-to-insert-image.png)

2. Open the file library.
![Open file library in Author IDE](/img/skills-network-file-library/how-to-use/author-ide-file-library.png)

3. Select `Images` in the `Mode` section.

4. Select an image you want to insert into your instructions.

5. Optionally specify `Title` and `Link`.

6. Click `Insert Image`.
![Insert image into the editor](/img/skills-network-file-library/how-to-use/author-ide-insert-image.png)

7. Done.
![Image inserted](/img/skills-network-file-library/how-to-use/author-ide-inserted-image.png)

### Insert images into instructions inside JupyterLab or JupyterLite:

1. Open the file library.
![Open file library in JupyterLab/JupyterLite authoring environment](/img/skills-network-file-library/how-to-use/jlab-jlite-file-library.png)

2. Select an image you want to insert into your instructions.

3. Copy the URL of the image from the `Public URL` section.
![Copy image URL](/img/skills-network-file-library/how-to-use/jlab-jlite-insert-image.png)

4. Insert the image into a markdown cell in your notebook with the url from the previous step using the following format: `![<alternative_text>](<image_url>)`.
![Insert image into the editor](/img/skills-network-file-library/how-to-use/jlab-jlite-insert-image-into-md-cell.png)

5. Done.
![Inserted Image](/img/skills-network-file-library/how-to-use/jlab-jlite-inserted-image.png)