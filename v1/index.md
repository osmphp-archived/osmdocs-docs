# OsmDocs User Guide #

In OsmDocs, the central concept is a **book**.

Technically, a book is a directory of [Markdown files](using-markdown-syntax.html) and images. At the very least, book directory contains `index.md` file which represents book topmost page.

Other Markdown files in book directory are considered to be child pages of the topmost page. These pages may have child pages of their own. All book pages are written using Markdown syntax, may include images, tags and more, see [Organizing Pages And Images](organizing-pages-and-images.html) for details.

Before writing books, you'll have to install necessary software on your computer,
configure SFTP connection and automatic upload of all the changes. All of that is covered in [Getting Started](getting-started.html).

> **Note**. In this guide, we use [Atom](https://atom.io/) for editing and uploading files as we really like how it works with OsmDocs. However, you can use any editor and any SFTP client of your choice. For instance, [PhpStorm](https://www.jetbrains.com/phpstorm/) has great SFTP support with automated uploading of all changes, too. We may cover such tools in detail later.

The rest of documentation covers advanced topics such as working on the same book in team and using your own website domain instead of [osmdocs.com](https://osmdocs.com/).

Contents:

{{ child_pages }}
