# Step 1: Protect your code

It's been a busy month at Mergington High! Your simple website for managing extra-curricular activities has really taken off. What started as a basic sign-up form for a few activities has grown into the go-to place for half the school activities. 📚✨

Principal Martinez was so impressed with your work that they announced at the last staff meeting that ALL clubs should start using the website. While this is exciting, you're a bit nervous - the last thing you want is an accidental change breaking the system right before the big Fall Activities Fair! 😰

When more teachers start helping with the Mergington High activities website, it's important to add some safeguards. Thankfully, GitHub provides several ways to protect your repository:

1. **Repository Rulesets** - These provide safeguards to limit:

   - Pushing code directly to important branches
   - Deleting or renaming branches
   - Force pushing (which can overwrite history)
   - (and much more)

1. **`.gitignore`** - This special file tells Git which files it should NOT track, like:

   - Temporary files that your code creates while running
   - Secret configuration files with sensitive information
   - System files that other developers don't need

> [!TIP]
> Think of these settings like the editorial process of a school yearbook. Various student committees will take photos and write articles, then the yearbook president will make adjustments to make sure everything flows together properly. Finally, a teacher/advisor will sign off that all content is appropriate.


## ⌨️ Activity: Add a branch ruleset

To get started, let's add some protections so that no one accidentally breaks the club registration system.

1. If necessary, open another tab and navigate to this repository. We will start on the **Settings** tab.

1. In the left navigation, expand the **Rules** area and select **Rulesets**.

1. Click the **New ruleset** dropdown and select **New branch ruleset**.

   <img width="250" alt="image" src="https://github.com/user-attachments/assets/1e9fd519-1421-4d6b-b654-a3fe53a8fb75" />

1. Set the **Ruleset Name** as `Protect main` and change the **Enforcement status** to `Active`.

   <img width="250" alt="image" src="https://github.com/user-attachments/assets/ce30fd34-39b5-4e22-b348-4af61fd05cd1" />

1. Find the **Targets** section and use the **Add target** dropdown to add 2 entries:

   1. Add the **Include default branch** option to ensure protections aren't bypassed by switching the default branch.

      <img width="250" alt="image" src="https://github.com/user-attachments/assets/217263cc-d5c2-4ac0-b03c-a72494e5c812" />

   1. Use the **include by pattern** option and enter the pattern `main`.

      <img width="250" alt="image" src="https://github.com/user-attachments/assets/968c9ed8-b051-44eb-af42-d99670ad31fd" />

      <img width="250" alt="image" src="https://github.com/user-attachments/assets/ddc52767-d93e-4c9e-a77a-90c3b5c08fb5" />

1. Find the **Rules** section and ensure the following items are checked.

   - [x] Restrict deletions
   - [x] Require a pull request before merging
     - Required approvals: `0`
     - [x] Require review from Code Owners
   - [x] Block force pushes

1. Scroll to the bottom and click the **Create** button to save the ruleset.

## ⌨️ Activity: Create a `.gitignore` file

We know many teachers use different tools, so let's make sure they don't accidentally commit unnecessary files.

1. At the top navigation, return to the **Code** tab and verify you are on the `main` branch.

1. Above the list of files, click the **Add file** dropdown and select **Create new file**.

   <img width="300" alt="New file button" src="https://github.com/user-attachments/assets/8f3f8da8-1471-485a-9df5-8c03ecba2d8e"/>

1. Enter the file name `.gitignore`. We will ignore the template selector for now and make our own. Copy the below example content into it.

   <img width="350" alt="preview of new file" src="https://github.com/user-attachments/assets/580d1a63-a264-4d44-8901-50ad708b8822"/>

   ```gitignore
   # Python backend for club management
   __pycache__/
   *.py[cod]      # Python compiled files
   *$py.class
   *.so
   .Python
   env/
   .env           # Where database passwords are stored
   venv/          # Virtual environment for testing
   .venv

   # Teacher IDE settings
   .vscode/       # Ms. Rodriguez uses VS Code
   .idea/         # Mr. Chen uses PyCharm

   # Local development & testing
   instance/
   .pytest_cache/
   .coverage      # Test coverage reports
   htmlcov/

   # Staff computer files
   .DS_Store      # For teachers with Macs
   Thumbs.db      # For teachers with Windows
   ```

1. In the top right, select the **Commit changes...** button. Notice that it won't let us commit to the `main` branch! Our ruleset is working! Nice!

   <img width="400" alt="image" src="https://github.com/user-attachments/assets/4e85948d-75c8-4c13-8ddd-4707bf9b0805" />

1. Enter `prepare-to-collaborate` for the branch name then click the **Propose changes** button. You will be forwarded to a new page to start a new pull request. 

1. Set the title to `Prepare to collaborate` and click the **Create pull request** button. **Do NOT merge yet**, since we will be adding more collaboration related changes. **IMPORTANT: Make sure the base for the pull request is the main branch of yuor fork of the assignment.**

1. With the file committed, wait a moment for Mona to check your work, provide feedback, and share the next lesson.

> [!TIP]
> GitHub and the community have built a repository with [sample `.gitignore` files](https://github.com/github/gitignore) for many situations. Make sure to check it out!

<details>
<summary>🤷 Having trouble?</summary><br/>

Make sure you pushed the `.gitignore` file to `prepare-to-collaborate` branch. Exact naming for both matters!

</details>
