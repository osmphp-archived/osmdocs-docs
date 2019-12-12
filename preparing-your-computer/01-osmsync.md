# OsmSync

{{ toc }}

## Connecting To OsmDocs

1. Install [OsmSync](https://github.com/osmianski/osmsync) as described in its `Installation` section into some directory (I'll call it `{project_path}`).
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
3. Run the following commands in shell to download all of your books to `osmdocs.com` subdirectory:

        cd {project_path}
        gulp pull

## Auto-Syncing Changes

Run the following commands in shell tpo track changes in `osmdocs.com` subdirectory and upload them back to OsmDocs server automatically:

    cd {project_path}
    gulp watch

Alternatively, run this command in background as described in `Installing As A Windows Service` and `Running In Background In Linux` sections of [OsmSync](https://github.com/osmianski/osmsync) readme.

## Editing Files

Just edit files in `{project_path}/osmdocs.com` directory, create new ones, delete obsolete files - all the changes will be automatically uploaded to OsmDocs server.

After making changes, open the book in the browser by clicking on a book link in `My Books` page of your OsmDocs account and see how the changes look like.
