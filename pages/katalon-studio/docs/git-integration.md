---
title: "Git Integration"
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/git-integration.html
redirect_from:
    - "/display/KD/Git+Integration/"
    - "/display/KD/Git%20Integration/"
    - "/x/foEw/"
    - "/katalon-studio/docs/git-integration/"
    - "/katalon-studio/tutorials/git_integration_introduction.html"
description:
---

> The Git integration feature is based on **EGit**. You can refer to [http://wiki.eclipse.org/EGit/User_Guide](http://wiki.eclipse.org/EGit/User_Guide) for a detailed user guide regarding EGit.

What is Git?
------------

Git is a powerful and popular system for version control. It is one of the essential tools for collaboration in software development teams. If your Katalon Studio automation project involves several or more members, you should use Git or another source control system for managing change and configuration on your project. Below are several specific benefits of using Git for your Katalon Studio projects.  

* Git allows undoing mistakes
  * The undo ability gives project teams the courage to try out ideas and concepts without worrying about the risk of breaking stuff, and thus, fosters a culture of innovation.
* Git makes the team progress clearer
  * A commit in Git refers to a change in automation scripts that a team member makes, indicating the progress of tasks.
  * Git supports comparing versions of code to show differences between commits. It is useful to review a commit before it officially becomes final.
* Git supports working offline
  * Being to work offline makes your team more fail-safe. Each member can perform everything on his/her computer, independent from possible infrastructure downtime.
* Never losing data ever again
  * As daily work can be committed to the remote Git server, every team member working on a project has a full-fledged copy on his/her machine, including the project's complete change history.
* If any backup breaks down: restore it using any team member's local repository or Git repository.

With Git, a repository can be shared to multiple members in a team to help to improve the team's collaboration and productivity.

Katalon Studio integration with Git introduction
------------------------------------------------

Git Integration is a powerful feature of Katalon Studio for collaboration between team members in test automation projects using Git. This tutorial presents a typical workflow for Git integration with Katalon Studio:

![workflow working with Git in Katalon](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/tutorials/git_integration_introduction/Katalon-and-Git.png)

Configuration
-------------

1. **Enable Git Integration:** To access all Git features, you need to enable Git Integration first. The option is available in the following settings: **Katalon Studio >  Preferences > Katalon > Git**. Once enabled, you can start using Git at Katalon Studio's main toolbar.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/tutorials/git_integration_introduction/Enable-Git-integration-in-Katalon-Studio-2.png)

2. Now the Git integration feature should be **enabled**. We are ready to use Git from Katalon Studio.
    
<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/git-icon.png" width="545" height="202">

3. Advanced configurations are available at **Katalon Studio> Preferences > Team > Git** in case you want specific settings.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-6-29-163A563A16.png)

Clone a Katalon Studio project from a Git repository
----------------------------------------------------

After enabling Git Integration, you can clone an existing **Git repository** into a newly-created directory on the local machine.

1. From the main toolbar, select the **Git icon > Clone Project**.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-143A13A12.png)

2. The **Source Git Repository** dialog is displayed.

    ### Connecting to Git with HTTPS

    Enter all required information and click **Next** to let Katalon Studio get details about your repository.

     <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/https.png" width="522" height="412">

    Where:

    * Repository URL: the [remote URL](https://help.github.com/en/articles/which-remote-url-should-i-use) to your Git repository in HTTPS protocol.
    * Username: the username to access the Git repository.
    * Password: the password to access the Git repository.

    If you cannot access the repository after clicking **Next**, the connection may have issues with SSL verification. You can use below command to bypass SSL verification (NOT recommended):

    ```groovy
    git config --global http.sslVerify false
    ```

    ### Connecting to Git with SSH Keys

    >Starting from **version 7.0.0**, Katalon Studio supports connecting to Git with SSH Keys.

    1. Generating a public/private rsa key pair with this command:\
    `ssh-keygen -m PEM -t rsa -b 2048 -C "your_email@example.com"`
        > Note: Katalon Studio only supports `OpenSSL`, NOT `OpenSSH` formats.
    2. Enter file in which to save the key.
    3. Enter the SSH key [passphrase](https://help.github.com/en/articles/working-with-ssh-key-passphrases) and confirm it.
    4. Add your SSH key to the ssh-agent.
    5. Add a new SSH key to your Git account.

    In the **Source Git Repository** dialog, enter a repository URL with SSH Protocol and click **Next**.  

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/ssh.png" width="610" height="413">

    Enter the passphrase for the key generated above.
    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/filled-passphrase.png" width="523" height="415">

3. At **Branch Selection** screen, you can choose which branches to be checked out as local branches. Click **Next** to continue.

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/branch.png" width="523" height="411">

4. At **Local Destination** dialog, specify the local location for cloning as well as the initial branch.

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/local.png" width="520" height="412">

    Where:

* Directory: the local storage location you want to store your Git's repository.
* Initial branch: all selected branches from the previous step are displayed here. Select the branch to be used initially from this list.

5. Click **Finish** when you are done. Katalon Studio automatically opens your cloned project.

6. To verify settings, go to **Katalon Studio> Preferences > Team > Git > Configurations >  Repository Settings**. Ensure that the repository is selected correctly with the URL specified.

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/verify.png" width="" height="">

Publish a local non-Git project as a Git repository
-------------------------------------------------

**Share Project** is a step to enable Git configuration for your new Katalon Studio project.

1.  From the main toolbar, select the **Git icon > Share Project**.

    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-143A273A20.png)

2.  Folder **.git** and file **.gitignore** are created within the Katalon project.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2016-9-1-153A553A54.png)

    > **`.gitignore`** tells Git which files (or patterns) it should ignore. By default, **.gitignore** contains these files and patterns:
    >
    > /bin
    > /Libs
    > .settings
    > .classpath
    > /.svn

Commit
------

The **Commit** option allows users to view all current changes and decide which changes to be stored in the local branch. Refer to [https://git-scm.com/docs/git-commit](https://git-scm.com/docs/git-commit) for detailed Git documentation regarding Commit command.

1. From the main toolbar, select the **Git icon > Commit**.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-143A383A43.png)

2. The **Git Staging** tab is displayed for configuration.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-143A413A43.png)
    Where:

    | Field | Description |
    | --- | --- |
    | Unstaged Changes | Changes which have been made. |
    | Staged Changes | Selected changes from **Unstaged Changes.** These changes are committed. |

3. From the **Unstaged Changes** list, select the changes to be committed, then right-click on them and select **Add To Index**. Selected changes are added to the **Staged Changes** list.

4. Enter your comments into the **Commit Message** then click on **Commit** to store your staged changes into the local branch.

Manage Branches
---------------

### New Branch

1. From the main toolbar, select the **Git icon > Manage Branches > New Branch**.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-143A573A48.png)

2. The **Create Branch** dialog is displayed.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-153A23A3.png)
    Where:

    <table><thead><tr><th>Field</th><th>Description</th></tr></thead><tbody><tr><td>Source</td><td><p>Select either remote or local branch, which is your source branch.</p><p><img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-163A83A31.png"></p></td></tr><tr><td>Branch name</td><td>The name to be used for the new branch.</td></tr><tr><td>Checkout new branch</td><td>Option to let Katalon Studio checkout that branch after created.</td></tr></tbody></table>

3.  Click **Finish** to create a new branch.

### Checkout Branch

The **Checkout Branch** option allows you to switch from one branch to another.

1.  From the main toolbar, select the **Git icon > Manage Branches > Checkout Branch**.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-153A73A15.png)

2.  The **Select Source** dialog is displayed. Select the local branch you want to check out to be the current branch. The branch with an √ icon is your current local branch.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-153A83A40.png)

3.  Click **OK** to finish checking out to the new local branch.

### Delete Branch 

1. From the main toolbar, select the **Git icon > Manage Branches > Delete Branch**.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-153A103A10.png)

2. In this dialog, both local and remote branches are displayed. Select a branch to be deleted then click **OK**.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-163A63A37.png)

Fetch
-----

Retrieve all information about changes that have occurred in remote branches. Refer to [https://git-scm.com/docs/git-fetch](https://git-scm.com/docs/git-fetch) for detailed Git documentation regarding Fetch command

1. From the main toolbar, select the **Git icon > Fetch**.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-163A273A32.png)

2. It automatically fetches remote branches, tags, and remote changes.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-163A573A18.png)

3. Select **History** from the main toolbar.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-173A23A17.png)

4. Details regarding all the branches and tags you've just fetched are displayed.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-173A63A5.png)

Pull
----

Incorporate changes from a remote repository into the current branch. Refer to [https://git-scm.com/docs/git-pull](https://git-scm.com/docs/git-pull) for detailed Git documentation regarding Pull command.

1. From the main toolbar, select the **Git icon > Pull**.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-153A533A48.png)

2. In the **Pull** dialog, select the remote branch to be pulled into your local branch. Click **Finish**.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-153A543A56.png)

3. The **Pull Result** dialog is displayed with all data about pulling requests on the selected branch.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-153A563A21.png)

Push
----

Update the remote branch using the local branch. Refer to [https://git-scm.com/docs/git-push](https://git-scm.com/docs/git-push) for detailed Git documentation regarding Push command.

Before doing any push, you have to commit your changes first.

1. From the main toolbar, select the **Git icon > Push**.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-153A143A38.png)

2. The **Push to Branch** dialog is displayed. Choose from the **Remote branch** list which branch to be updated (All remote branches in your Git repository are listed here).

    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-153A193A28.png)
    Click **Next** after finished selecting your remote branch.

    > If you enter a different name besides the listed branches, a new remote branch with that name is created accordingly.

3. The **Push Confirmation** Dialog is displayed with details regarding your commit.
    ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/git-integration/image2017-2-22-153A273A45.png)
    Click on **Finish** to push your commits to the remote repository.
