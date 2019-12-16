# IntelliJ IDEA Community Edition

After downloading books to your local hard drive, edit book files using [IntelliJ IDEA](https://www.jetbrains.com/idea/download/). Download and install Community Edition - it's free and more than enough for book editing. 

Open the directory containing all the books in IntelliJ IDEA using `File -> Open` menu. 

Contents:

{{ toc }}

## Settings

In `File -> Settings (Alt+F7)`:

* Set `Keymap = Visual Studio` to make sure that keyboard shortcuts in your copy of IntelliJ IDEA are the same as in this user guide.
* Clear `System Settings -> Use "safe write"` checkbox to force saving file every time you switch from IntelliJ IDEA to another application.
* In `Version Control` section: 
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


 