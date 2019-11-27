# Using SFTP

Conceptually, there are three kind of tools for working with book files via SFTP:

1. Use SFTP client such as [FileZilla](using-sftp/filezilla.html), WinScp, Cyberduck or other for browsing, creating, editing and deleting files on the server.

    It is the most straightforward way of working with SFTP server.

    Use SFTP client if you don't write a lot and don't want to bother with installing and configuring [OsmSync](using-sftp/osmsync.html).

    Configure SFTP client to open `.md` files in your favorite external Markdown editor.

2. If you already use IDE (integrated development environment) such as [PhpStorm](using-sftp/phpstorm.html) (same applies to almost any other IDE from [JetBrains](https://www.jetbrains.com/products.html)), [Atom](using-sftp/atom.html), VS Code or other, configure your IDE to work with our SFTP server.

    This way, you can use single tool both for coding and for writing.

    Also use your IDE to download all book files locally and to upload changes made to the local files automatically. IDE's have support file syncing to a various degree, but some are very decent at that, for instance [PhpStorm](using-sftp/phpstorm.html).

    Explore ecosystem around your IDE for the best possible internal Markdown editor. [Atom](markdown-editors/atom.html) especially shines at that. Alternatively, configure your IDE to open `.md` files in your favorite external Markdown editor.

3. If you are not afraid of the command line, use [OsmSync](using-sftp/osmsync.html).

    With OsmSync, first download files of all of your books from our server using `gulp pull` command and then watch them for changes and upload changes to our server on the fly with `gulp watch` command. You can even setup it as a service and forget - it will still track all the changes and upload them to our server in background.

    This way, you will always have full copy of all of your books locally. Use your favorite Markdown or IDE for editing those files.

Internally, we use [OsmSync](using-sftp/osmsync.html) for syncing files via SFTP and [Atom](markdown-editors/atom.html) for local file editing. However, you may have different setup according to your needs and preferences.

After picking one of the listed tools, follow the link to open tool-specific usage instructions.
