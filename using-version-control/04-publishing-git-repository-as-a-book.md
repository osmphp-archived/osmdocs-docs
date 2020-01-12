# Publishing Git Repository As A Book

After the book contents gets into shape, create one more book in your OsmDocs account and link it with the remote Gt repository on GitHub (or other Git hosting) and share this book with your readers. 

Such books are not edited directly via SFTP. Instead, their contents is changed whenever you push to the remote Git repository.

Configuration is a bit different for publicly available and private Git repositories.

Contents:

{{ toc }}

## Publishing Public Git Repository

1. On GitHub's repository page, press `Clone or download` button, press `Use HTTPS` link and copy the repository URL from the text box to clipboard.  

2. Create new book in your OsmDocs account, paste the repository URL into the `Repository URL` field and save the book. 

The book contents is immediately cloned from GitHub. Open the book link from `My Books` page and make sure that the book is available. 

## Publishing Private Git Repository

1. Create new book in your OsmDocs account. Click `Allow SSH Access` button and use `Copy` button to copy SSH public key to clipboard.

2. In GitHub repository `Settings -> Deploy keys` page, press `Add deploy key` button, paste SSH public key from clipboard to `Key` field and press `Add key` button.  

3. On GitHub's repository page, press `Clone or download` button, press `Use SSH` link and copy the repository URL from the text box to clipboard.  

4. In OsmDocs book settings, paste the repository URL into the `Repository URL` field and save the book. 

The book contents is immediately cloned from GitHub. Open the book link from `My Books` page and make sure that the book is available. 

## Manually Updating The Book

Use `Pull` button in OsmDocs book settings to retrieve the latest book version from remote Git repository.

## Automating Book Updates

1. In OsmDocs book settings, press `Configure Web Hook` button and use `Copy` button to copy Web hook URL to clipboard.

2. In GitHub repository `Settings -> Webhooks` page, press `Add webhook` button, paste the Web hook URL into the `Payload URL` field, keep `Content Type == application/x-www-form-urlencoded` and press `Add webhook` button.

After these steps, the book contents on OsmDocs will be update after every push to GitHub repository.

## Changing Git Branch

By default, the book on OsmDocs shows the contents from the latest commit on the `master` branch. 

If needed, enter the name of another branch into the `Branch` field on OsmDocs book settings page.  