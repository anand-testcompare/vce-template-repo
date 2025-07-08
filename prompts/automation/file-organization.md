# Gemini CLI Prompt for Directory Organization and File Renaming

## Overview

This prompt instructs Gemini to perform a comprehensive and safe cleanup of a directory. The process is divided into several phases:
0.  **Backup:** Create a compressed archive of the entire directory before making any changes.
1.  **Organization:** Sort all files and folders into logically named, prefixed parent folders.
2.  **Content-Based Renaming:** Analyze the content of screenshots and rename them with a `yyyy-mm-dd` date prefix and a descriptive name.
3.  **Final Cleanup:** Tidy up any empty or redundant folders created during the process.
4.  **Create Mapping File:** Generate a Markdown file that logs all file path changes, making it easy to update external references (e.g., in Obsidian).

---

## The Prompt

**Instructions:** Copy and paste the text below into the Gemini CLI.

```
Hello! I need your help organizing my current directory. Please follow these steps carefully:

**Phase 0: Create a Backup**

1.  Before you begin, create a compressed `tar.gz` archive of the current directory's contents. Name it `backup-YYYYMMDD-HHMMSS.tar.gz` using the current timestamp.
2.  **Crucially**, make sure to exclude the backup file itself from the archive.

**Phase 1: Organize the Directory**

1.  **Analyze:** Review all files, images, documents, and subdirectories in my current directory to understand their purpose.
2.  **Create Folders:** Create a small number of logically organized parent folders. Prefix each folder name with a number for ordering (e.g., `01. Development`, `02. Media`, `03. Documents`).
3.  **Move Files:** Move all items from the root of the directory into the appropriate new folders.
    *   Leave system files (like `.DS_Store` or `.localized`) in place.
    *   Be prepared to handle files with very long or complex names that might cause errors. If a standard `mv` command fails, try renaming the file to something simple first (e.g., `temp-file.ext`), then move it, and then rename it back if necessary, or use a more robust command like `find` with `-exec`.

**Phase 2: Rename Screenshots**

1.  **Locate Screenshots:** Find the folder you created that contains my screenshots (e.g., `02. Screenshots`).
2.  **Analyze and Rename:** For each image file in that folder, perform the following:
    *   **View the image content** to understand what it depicts.
    *   **Determine a new, descriptive filename** in kebab-case (e.g., `vehicle-registration-receipt` or `project-file-structure`).
    *   **Extract the original creation date** from the old filename (e.g., from "Screenshot 2024-06-26 at 10.12.04 PM.png").
    *   **Rename the file** using the format: `yyyy-mm-dd-your-descriptive-name.png`.

**Phase 3: Final Cleanup**

1.  After all moves and renames are complete, please do a final check to ensure no empty or redundant subdirectories were left behind. If so, please clean them up.

**Phase 4: Create a Mapping File**

1.  This is the most critical step. As you perform the moves and renames in the phases above, you must keep a precise record of every change.
2.  Once all operations are complete, create a new Markdown file named `file_changes_log.md`.
3.  In this file, create a table with two columns: "Old Path" and "New Path".
4.  Populate the table with every single file that was moved or renamed. The paths should be absolute.

    **Example:**

    | Old Path                                                              | New Path                                                                    |
    | --------------------------------------------------------------------- | --------------------------------------------------------------------------- |
    | /Users/anandpant/Desktop/Screenshot 2024-06-26 at 10.12.04 PM.png      | /Users/anandpant/Desktop/02. Screenshots/2024-06-26-vehicle-registration-renewal.png |
    | /Users/anandpant/Desktop/my-project/                                  | /Users/anandpant/Desktop/01. Development/my-project/                        |

Please begin.
```