# AI Use Log
* **Tool Used:** AI Assistant
* **Step Used:** Step 2 (Generating cleaning and verification code after committing `attempt-before-AI`)
* **Prompt Summary:** Described the columns (`date`, `item`, `city`, `price`) and the 3 diagnosed issues in words without pasting raw dataset rows, and requested pandas cleaning code and a before-and-after verification table.
* **Verification & Edits:** Ran the generated code on a copy (`df_clean = df.copy()`) in `2_work.ipynb`, verified every line could be explained, and checked row counts, missing values, and `describe()` outputs before accepting the code.