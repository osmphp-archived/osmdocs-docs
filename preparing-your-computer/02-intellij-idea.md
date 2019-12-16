# IntelliJ IDEA Community Edition

After downloading books to your local hard drive, edit book files using [IntelliJ IDEA](https://www.jetbrains.com/idea/download/). Download and install Community Edition - it's free and more than enough for book editing. 

Open the directory containing all the books in IntelliJ IDEA using `File -> Open` menu. 

Contents:

{{ toc }}

## Settings

In `File -> Settings (Alt+F7)`:

* Set `Keymap = Visual Studio` to make sure that keyboard shortcuts in your copy of IntelliJ IDEA are the same as in this user guide.
* Optionally, if you'll use Git: in `Keymap` section, find `Main menu -> VCS -> Git -> Fetch` and double click on it:
    * Pick `Add Keyboard Shortcut`
    * Press `Ctrl+Shift+M`.
    * Check `Second keystroke` and press down arrow.
    * Press `OK`, `Apply` and `OK`. 
* Clear `System Settings -> Use "safe write"` checkbox to force saving file every time you switch from IntelliJ IDEA to another application.
* Optionally, if you'll use Git: in `Version Control` section: 
    * Check `Commit dialog -> Commit from local changes without showing the Commit dialog` checkbox - for faster Git commit operations.
    * In `Confirmation` subsection:
        * Set `When files are created = Add silently` and check `Including external files` checkbox
        * Set `When files are deleted = Remove silently`
    * Clear `Git -> Show Push dialog for Commit and Push` checkbox - for faster Git push operations.
* Optionally, customize `Appearance & Behavior -> Appearance`: 
    Set `Appearance & Behavior -> Appearance -> Theme = Darcula`.

## Using Git

Before using Git, install and configure it as described in [installing Git](../version-control/git-concepts.html#installing-git).

### Creating Git repository For A Book
 
1. Open `VCS -> Import into Version Control -> Create Git Repository`.
2. Pick book directory and press OK.

### Committing To A Git Repository

1. Edit files or create new ones. Allow IDE to put new files under Git if it asks you to.

2. See new, modified and deleted files since last commit using `View -> Tool Windows -> Version Control (Alt+9)`. Press `Alt+9` again to hide the tool window.

3. If you see red (not under Git) files in the version control Tool Window, click on such files and press `Ctrl+Alt+A` to put them under Git.

4. Press `Ctrl+K` to create a commit, enter commit message describing the changes you made and press the `Commit` button (`Alt+I`).

### Viewing Commit History

Open `View -> Tool Windows -> Version Control (Alt+9)` and click on `Log` tab.

### Working With Git Branches

1. See all the book directories being under separate Git repositories and on which branch they are (typically you will see `master`) by clicking on `Git: master` in the right-bottom corner of the IDE or by using `Ctrl+Shift+BackTick` keyboard shortcut. It opens `Git Branches` tool window. 

2. Create new branch and switch to it in `Git Branches` tool window by clicking on a book directory name and picking `New branch`  (available after making the initial commit).

3. Merge a branch into the current branch in `Git Branches` tool window by clicking on a book directory name, picking the branch to merge from and clicking on `Merge into current` command.

4. Delete a branch in `Git Branches` tool window by clicking on a book directory name, picking the branch to be deleted and clicking on `Delete` command.

### Working With Remote Repositories

1. Create a remote repository, configure your GitHub account and push to the remote repository for the first time in command line, as described in [Remote Repositories](../version-control/remote-repositories.html).
2. Clone existing repository into your OsmDocs account:

    1. Create new empty book `{book_name}` on OsmDocs.
    2. Stop [OsmSync](osmsync.html) from syncing changes.
    3. Clone existing repository using `VCS -> get From Version Control`, entering SSH version of the remote repository URL, picking directory `{project_path}/{book_name}` pressing `OK`. 
    4. Run `gulp push` command of OsmSync to push all the books to OsmDocs server including the one you have just cloned.
    5. Start OsmSync again to watch and upload your changes. 
 
3. After making some commits, push to the remote repository using `VCS -> Git -> Push (Ctrl+Shift+K)` dialog.

4. Merge the latest changes from the remote repository using `VSC -> Git -> Fetch` command followed by merging `origin/master` branch using `Git Branches` tool window as described in [Working With Git Branches](#working-with-git-branches).

5. You can also push when committing. Commit as described in [Committing To A Git Repository](#committing-to-a-git-repository), but instead of clicking `Commit (Alt+I)` button, press on down arrow near t and pick `Commit And Push (Ctrl+Alt+K)`.

### Creating Pull Requests

1. Create new feature branch in `Git Branches` tool window as described in [Working With Git Branches](#working-with-git-branches).

2. Make some changes and commit them on the feature branch.     

3. Create a pull request using `VCS -> Git -> Create Pull Request` and picking the remote repository. Enter pull request title so that maintainer can understand what your changes are about and press `OK`.

### Merging Pull Requests

1. Open list of pending pull requests using `VCS -> Git -> View Pull Requests` and picking the remote repository.

2. If the change is OK to merge, click on `Open on GitHub` link and merge the pull request as described in [Maintainers And Pull Requests](../version-control/team-workflow.html#maintainers-and-pull-requests).  