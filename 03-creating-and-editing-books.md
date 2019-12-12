# Creating And Editing Books

**Book** is the central concept in OsmDocs. Technically, a book is a directory of Markdown files and images.

At the very least, book directory contains `index.md` file which represents book **home** page.

Other Markdown files in book directory are child pages of the home page. These pages may have child pages of their own. All book pages are written using Markdown syntax, may include images, tags and more.

**OsmDocs** is a service for uploading your book files and showing them as a website.

Create a book in your OsmDocs account, download the book directory from OsmDocs server to your local hard drive and:

* edit the book files locally;
* configure your editor to save changes to disk automatically;
* use tools to upload all changes to OsmDocs server automatically (aka "sync").

This way, you'll edit local files and just check the changes in a Web browser, not thinking about whether your changes are saved and uploaded.

Alternatively, you can just edit book files (text and images) on OsmDocs server directly using SFTP client and see the changes in a Web browser.

This section dives into the details of creating a book and understanding book structure and syntax:

{{ child_pages }}

See also:

* [Preparing your computer](../preparing-your-computer.html)
* [Editing book files with IntelliJ IDEA](../preparing-your-computer/intellij-idea.html)
* [Editing book files with Atom](../preparing-your-computer/atom.html)
* [Syncing book files from your local hard drive to the OsmDocs server and back with OsmSync](../preparing-your-computer/osmsync.html)
