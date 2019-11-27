# OsmSync

{{ toc }}

## Connecting To OsmDocs

1. Install [OsmSync](https://github.com/osmianski/osmsync) as described in its `Installation` section into some directory (we'll call it `{project_path}`).
2. Add `config.json` file to `{project_path}` directory with the following contents:

        {
            "osmdocs.com": {
                "localPath": "osmdocs.com",
                "remotePath": "/",
                "remote": {
                      "host": "139.162.184.116",
                      "username": "{username}@osmdocs.com",
                      "password": "{password}"
                }
            }
        }
3. Run the following commands in shell:

        cd {project_path}
        gulp pull

## Auto-Syncing Changes

Run the following commands in shell:

    cd {project_path}
    gulp watch

Alternatively, run this command in background as described in `Installing As A Windows Service` and `Running In Background In Linux` sections of [OsmSync](https://github.com/osmianski/osmsync) readme.

## Working With Files

Just edit files in `{project_path}/osmdocs.com` directory, create new ones, delete obsolete files - all the changes will be automatically uploaded to our server.

Use any [Markdown editor](../markdown-editors.html) of your choice. Internally we open `{project_path}/osmdocs.com` as Atom project and use [Atom Markdown plugins](../markdown-editors/atom.html) for editing.

After making changes, open the book in the browser by clicking on a book link in `My Books` page of your OsmDocs account and see how the changes look like.
