# IntelliJ IDEA Community Edition

After downloading books to your local hard drive, edit book files using [IntelliJ IDEA](https://www.jetbrains.com/idea/download/). Download and install Community Edition - it's free and more than enough for book editing. 

Open a book directory in IntelliJ IDEA (or all the book directories) using `File -> Open` menu. 

Before diving into editing, configure IntelliJ IDEA as described in this article:   

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
* (Optional) Set `Appearance & Behavior -> Appearance -> Theme = Darcula`.
