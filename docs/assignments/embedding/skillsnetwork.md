# Skills Network

This guide shows the Skills Network-specific steps for embedding Mark assignments. First, get your LTI Launch URL using the **Embedding Mark - General Instructions**.

---

## Configure LTI in Skills Network

1. Open **Content** in your course and click **Edit in SN Studio**.  
   ![Content menu](../image-6.png)

2. In Studio, create **New Subsection ▸ New Unit**.  
   ![New Subsection button](../image-14.png)
   ![New Unit](../image-15.png)

3. Click **Advanced** (flask icon) → **LTI Consumer**.  
   ![Advanced components](../image-16.png)  
   ![Select LTI consumer](../image-17.png)

4. Press **Edit** and fill in the fields:

   | Field                       | Value                                     |
   | --------------------------- | ----------------------------------------- |
   | **LTI ID**                  | `sn_lti`                                  |
   | **LTI URL**                 | *\[Launch URL from general instructions]* |
   | **Launch Target**           | `New Window`                              |
   | **Request user's username** | `true`                                    |
   | **Request user's email**    | `true`                                    |
   | **Send extra parameters**   | `true`                                    |
   | **Scored** \*               | `true`                                    |

   > **Note:** Ensure **Scored** is set to `true` for **graded assignments**, so that grades can be assigned to the learner upon completion.

5. **Save** ➜ **Preview** the unit. Use "View this course as…" to test both **Author** and **Learner** views.
