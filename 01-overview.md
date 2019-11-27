# Overview

Contents:

{{ toc }}

## Books

**Book** is the central concept in OsmDocs. Technically, a book is a directory of Markdown files and images.

At the very least, book directory contains `index.md` file which represents book **home** page.

Other Markdown files in book directory are child pages of the home page. These pages may have child pages of their own. All book pages are written using Markdown syntax, may include images, tags and more.

Create books on our server using your OsmDocs account.

See also:

* [Signing Up](settings/signing-up.html)
* [Creating A Book](settings/creating-a-book.html)
* [Directory Structure](books/directory-structure.html)
* [Formatting](books/formatting.html)

## Editing

Create, edit or delete book files including images on our server using SFTP and see the changes in a Web browser.

You can edit Markdown files with any text editor, but we recommend using an editor specialized in Markdown.

For the best editing experience, we recommend downloading the book directory to your local hard drive and:

* edit the book files locally;
* configure your editor to save changes to disk automatically;
* use tools to upload all changes to our server automatically, that is creation of new files, file edits, even renaming and deleting files.

This way, you can just edit local files and just check the changes in the browser, not thinking about whether your changes are saved and uploaded.

See also:

* [SFTP Clients](sftp-clients.html)
* [Markdown Editors](markdown-editors.html)

## Using Git

Having book copy locally as suggested in [Editing](#editing) section have yet another advantage: you can put it under Git version control and share it with other team members so that everyone can edit the book on their own computers simultaneously and there is a clear change history of everyone's work.

There are many ways a team can organize its work on a book. This user guide describes most common ones.

You can also host one more book and configure it to display the latest merged version of everyone's work. So that whenever someone "pushes" merged changes, that book content is automatically updated.

See also:

* [Using Git](using-git.html)
* [Deploying Git Repositories](settings/deploying-git-repositories.html)

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
