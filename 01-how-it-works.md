# How It Works

Contents:

{{ toc }}

## Books

**Book** is the central concept in OsmDocs. Technically, a book is a directory of Markdown files and images.

At the very least, book directory contains `index.md` file which represents book **home** page.

Other Markdown files in book directory are child pages of the home page. These pages may have child pages of their own. All book pages are written using Markdown syntax, may include images, tags and more.

Create books in your OsmDocs account. Then edit book files (text and images) on OsmDocs server using SFTP and see the changes in a Web browser.

For the best editing experience, I recommend downloading the book directory to your local hard drive and:

* edit the book files locally;
* configure your editor to save changes to disk automatically;
* use tools to upload all changes to OsmDocs server automatically (aka "sync").

This way, you can just edit local files and just check the changes in the browser, not thinking about whether your changes are saved and uploaded.

## Version Control

Having book copy locally as suggested above has yet another important benefit: you can put book files under Git version control and share it with other team members so that everyone can edit the same book on their own computers simultaneously and see a clear change history of everyone's work. This user guide introduces how Git works and how to organize basic Git workflow.

You can also host one more book and configure it to display the latest merged version of everyone's work, so that whenever someone "pushes" merged changes, that book content is automatically updated.

## Tools

You will need three tools on your computer for effective book writing:

1. SFTP client to connect to the book files and edit them on OsmDocs server directly or to sync local book files with book files on OsmDocs server;
2. Markdown editor - well, for editing;
3. (optional) Git version control - for version history and team work.

Personally, I use [OsmSync]() for syncing files and [IntelliJ IDEA Community Edition]() for editing Markdown files and for Git integration. 

You may pick different set of tools. There are many alternatives out there, just search for "SFTP client", "Markdown editor", "Git UI".  

I have also checked some alternative solutions:

* [PhpStorm]() or almost any other IDE by [JetBrains]() - paid all-in-one solution with good file sync, good Git integration, but average Markdown editor.
* [Atom]() - free IDE with average file sync and good Markdown editor. 
* [FileZilla]() - free SFTP client, allows editing book files directly on OsmDocs server.
* [MarkdownPad]() - free good markdown editor; you can configure IDE to open Markdown files with MarkdownPad and improve overall experience.



## Using Your Own Domain

By default, every book's root URL is `https://osmdocs.com/{user}/{book}/`.

If you have purchased your own domain, you can show your book on it instead. So that book's root URL becomes `https://yourdomain.com/`.

This user guide is an example of using custom domain for book's root URL. As you can see, its URL is `https://docs.osmdocs.com`.

See also:

* [Using Your Own Domain](settings/using-your-own-domain.html)

## Self-Hosting

You can also download the software which displays a book as a website and install it on your server.

You can also customize it as needed.

See also:

* [Self-Hosting](self-hosting.html)
