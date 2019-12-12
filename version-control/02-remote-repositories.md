# Remote Repositories

{{ toc }}

## Creating Remote Repository

So far, all the operations were made in the Git repository of your book located in a local directory on your computer.

To share your work with a team mates, don't just copy book files to their computers manually. Instead upload your Git repository to GitHub or other Git hosting provider and ask your team mates to retrieve it from there. This way you'll enable very effective way of syncing everyone's work across the whole team.

The copy of your repository on GitHub is known as a **remote repository**

To create the remote repository for your book, create new account on [GitHub](https://github.com/) and follow [Creating a new repository](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-new-repository) guide.

## Configuring GitHub Account

To upload your Git repository to GitHub, you need to allow your computer to access your GitHub account:

1. Generate your SSH key pair on your computer by running the command:

        ssh-keygen

    It creates two files in your home directory:

    * `.ssh/id_rsa` contains your SSH private key (don't share it with anyone)
    * `.ssh/id_rsa.pub` - contains your SSH public key

    These two files are known as **SSH key pair**.

2. Click on the account icon in your GitHub account, pick `Settings -> SSH and GPG keys`, press `New SSH key` button, paste contents of `.ssh/id_rsa.pub` file located in your home directory into the `Key` field and press `Add SSH key` button.

    Read [Adding a new SSH key to your GitHub account](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account) for more details.

## Pushing To GitHub

Uploading commits from your local repository to the GitHub repository is known as **pushing**.

Before the first push, link your local repository to your GitHub repository:

1. in GitHub, copy GitHub repository URL by pressing `Clone or download` on your GitHub repository page, clicking on `Use SSH` and copying `git@github...git` URL from the text box. 

2. Use copied GitHub repository URL in the following command:

    cd {book_dir}
    git remote add origin git@github...git

After your local repository is linked to the repository on GitHub, push your local commits to GitHub repository:

    cd {book_dir}
    git checkout master
    git push origin master

## Allowing Others To Push To Your GitHub Repository

Open GitHub repository page, and add your team mate's username to `Settings -> Collaborators & teams -> Collaborators` and press `Add collaborator` button.

## Cloning Repository From GitHub

Creating local Git repository and downloading all commits from GitHub repository is known as **cloning**.

If you have push access to someone's repository, open GitHub repository page, click on `Use SSH` and copy `git...git` URL from the text box into the following command:

    cd {parent_dir}
    git clone git...git

If you don't have push access to someone's repository, open GitHub repository page, click on `Use HTTPS` and copy `https...git` URL from the text box into the following command:

    cd {parent_dir}
    git clone https...git

Either command will download book files from the latest commit on `master` branch to the directory `{parent_dir}/repository_name`. It will also create local Git repository and download all commits from GitHub repository.

## `origin/master` Branch



## Syncing Changes
