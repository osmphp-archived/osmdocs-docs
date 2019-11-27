# Getting Started

This guide briefs preparation steps needed for effective book editing in Atom project. If you are know what Atom and SFTP is, read the [short version](#short-version), otherwise, pick the [long version](#long-version).

> **Note**. You'll have to do these steps only once, before editing the first book. Your second and further books will appear in your Atom project after reconnecting to the server.

Contents:

{{ toc }}

## Short Version

1. [Sign up](#creating-osmdocs-account) to OsmDocs and [create a book](#creating-a-book). Open the book in a browser.

2. Install [Atom](https://atom.io/), [enable auto-saving files](#auto-saving-files-in-atom) and [additional Atom packages](#installing-atom-packages):
    * `language-markdown`
    * `markdown-writer`
    * `remote-ftp`
    * `tool-bar`
    * `tool-bar-markdown-writer`

3. [Create Atom project](#creating-atom-project) and add 2 files:

    * `.ftpconfig`, copy value of `host` and `user` from OsmDocs book settings:

            {
                "protocol": "sftp",
                "host": "{host}",
                "port": 22,
                "user": "{user}",
                "promptForPass": true,
                "remote": "/",
                "watch":["**/*.*"],
                "watchTimeout":500
            }

    * `.ftpignore`:

            /.ftpignore
            /.ftpconfig
            /.ssh/
            /temp/
            .git/

4. Connect to SFTP. When prompted for a password, use your OsmDocs password.

5. Test connection. Modify header in `index.md` of your book, save the changes and check if you see your changes in the browser.

## Long Version

### Creating A Book

> **Note**. You may have already noticed SFTP settings on a book settings page. You will use these settings in a few minutes to connect to the book files later in this guide.

### Installing Atom Packages

1. Installing Atom itself is straghtforward: download the installer from <https://atom.io/>, run the installer and follow the instructions.

2. After installation, open Atom and open its settings via menu `File -> Settings` or by using `Ctrl + Comma` shortcut and click on `Install` tab:

    ![Installing Atom packages](getting-started/installing-atom-packages.png)

3. Enter `remote-ftp` package name into `Search packages` text box and press `Enter`. In search result list, locate `remote-ftp` package created by `icetee` and click its `Install` button.

    This package will allow you to edit book files via SFTP. It will upload your changes whenever you edit book files in Atom and save the files (`Ctrl + S` keyboard shortcut). This package will also track any changes in book directory and upload them as necessary, so you can edit and save files using any external Markdown editor of your choice.

4. Repeat the same search/install procedure for these packages:

    * `language-markdown` by `burodepeper`
    * `markdown-writer` by `zhuochun`
    * `tool-bar` by `suda`
    * `tool-bar-markdown-writer` by `zhuochun`

    These four packages will provide you with rich markdown editing capabilities including live preview and convenient toolbar and keyboard shortcuts for applying visual styles to your text.

### Auto-Saving Files In Atom

After editing a file in Atom you normally have to press `Ctrl + S` to save changes to disk and to upload them to the server. It may lead to certain confusion, so let's enable auto-saving files whenever you switch from Atom to the browser:

1. Open Atom settings via menu `File -> Settings` or by using `Ctrl + Comma` shortcut, click on `Packages` tab and enter `autosave` into `Filter packages` text box:

    ![Finding Autosave Atom package](getting-started/finding-autosave-atom-package.png)

2. Click `Settings` button of the `autosave` package, and then check `Enabled` checkbox in the `Settings` section:

![Enabling Autosave setting](getting-started/enabling-autosave-setting.png)


### Creating Atom Project

Atom project is a directory on your local hard drive containing configuration files specifying SFTP connection settings and local copy of all the files of all your books.

Atom project is needed for the book editing, so let's create it:

1. Click on Atom's `File -> Open Folder` menu item or press `Ctrl + Shift + O`, pick or create (by right-clicking inside exiting directory and picking `New -> Folder` menu item from context menu) a directory on your local hard drive and click `Select Folder` button to open selected directory as Atom project:

    ![Empty Atom project](getting-started/empty-atom-project.png)

    It's empty, but not for a long time :)

2. Right-click on root directory name in project sidebar and pick `New file` menu item from context menu. When prompted for a filename, enter `.ftpconfig`. In file editor, paste the following settings:

        {
            "protocol": "sftp",
            "host": "{host}",
            "port": 22,
            "user": "{user}",
            "promptForPass": true,
            "remote": "/",
            "watch":["**/*.*"],
            "watchTimeout":500
        }

    Replace `{host}` and `{user}` placeholders with actual SFTP host and SFTP user name which you can find in `My Books -> [gear icon] -> Edit book contents using SFTP` section.

3. Right-click on root directory name in project sidebar one more time and pick `New file` menu item from context menu. When prompted for a filename, enter `.ftpignore`. In file editor, paste the following settings:

        /.ftpignore
        /.ftpconfig
        /.ssh/
        /temp/
        .git/

4. Connect to SFTP via Atom's `Packages -> Remote FTP -> Connect` menu item. When prompted for password, enter your OsmDocs account password. The `Remote`  tab appears in left sidebar displaying your book directory (in the example below, `my-first-book`) and `.ssh` directory:

    ![Atom connected to SFTP](getting-started/atom-connected-to-sftp.png)

    > **Note**. Sometimes Atom complains that it can't find `.ftpconfig` file. In this case `Remote` tab appears anyway, displaying buttons instead of remote files. In this case press `Connect` button in the `Remote` tab and, when prompted, enter your OsmDocs account password.

5. Expand the book directory and double-click `index.md` in `Remote` sidebar to oen it in editor. Enter some meaningful book title between `#` characters.

6. Open the book in the browser by clicking on a book link in `My Books` page. You should see the meaningful title you just entered.

7. Switch to Atom again, do some more editing of `index.md`. Switch back to the browser, refresh the page and see your edits online!

### Saving The Password

If you find entering the password tiring, consider replacing

    "promptForPass": true,

line in `.ftpconfig` file with

    "pass": "your_osmdocs_password",

This way Atom will always use this password instead of asking for it. However, keep in mind that storing passwords in plain text like this is not secure. You have been warned!

### SFTP Commands

* Disconnect: `Alt + Ctrl + D`
* Connect: `Connect` button in `Remote` sidebar
* Make local files same as on server: `Sync local <- remote` in context menu of `Remote` sidebar
* Make files on server same as local: `Sync local -> remote` in context menu of `Project` sidebar

For more information, see <https://atom.io/packages/remote-ftp>.
