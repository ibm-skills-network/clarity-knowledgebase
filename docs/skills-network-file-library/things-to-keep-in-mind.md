---
sidebar_position: 5
---

# Things to Keep in Mind

- Renaming, deleting, or moving a file into a different folder changes or clears the public URL of that file. Make sure to update all instructions that use the public URL of the file after it has been renamed, deleted, or moved into a different folder.
- We don't recommend uploading or storing images anywhere outside the `/images` directory or its subdirectories when using the Skills Network File Library.
- For authors who use GitLab and rely on GitLab ci to upload files into Cloud Object Storage(COS), it's important to know that:
    - Skills Network File Library shares the same project path as the GitLab ci when it comes to uploading files to COS.
    - When a file is uploaded or modified in any way via Skills Network File Library, it's uploaded and kept track of on the default branch of the underlying GitLab project as well as the COS under the path associated with the project. This means that any manual intervention to the Skills Network File Library files caused by direct commits to the underlying GitLab project may break things in the Skills Network File Library.
    - Any project files uploaded manually via GitLab will not be automatically picked up by the Skills Network File Library.

