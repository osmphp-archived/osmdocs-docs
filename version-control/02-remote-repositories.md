# Remote Repositories

So far, all the operations were made in the Git repository of your book located in a local directory on your computer.

To share your work with a team mates, don't just copy book files to their computers manually. Instead upload your Git repository to GitHub or other Git hosting provider and ask your team mates to retrieve it from there. This way you'll enable very effective way of syncing everyone's work across the whole team:

![Team workflow](team-workflow.png)

This article goes into details of configuring a remote repository and working with it:

{{ toc }}

## Creating Remote Repository

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

Remote repository also has `master` branch. After initial push or clone operation: 

* the remote repository's `master` branch is attached to the same commit as your local `master` branch.
* the remote repository's `master` branch position is also remembered in your local repository as `origin/master` branch.
   
You can see `origin/master` in [the commit history](git-concepts.html#commit-history) of your local repository:

    * fee87e8 - (HEAD -> master, origin/master) commit #3 (6 hours ago) <Vladislav Osmianskij>
    * ca17a3b - commit #2 (7 hours ago) <Vladislav Osmianskij>
    * f708164 - commit #1 (9 hours ago) <Vladislav Osmianskij>

Note that `origin/master` branch show remote repository's `master` branch position at the moment of last synchronization (push, clone or fetch) operation. Since then, position of the remote repository `master` branch may change.   

## Fetching Remote Changes

To download new commits you team mates pushed to the remote repository, use the following command:

    git fetch
    
This command also reattaches `origin/master` branch to the same commit as remote repository's `master` branch.

## Merging Remote Changes

To merge remote changes into your own local `master` branch, run the following command:

    git merge origin/master
    
If you didn't commit any changes since last fetch/merge operations, you can use the following shorter command to do both fetch and then merge:

    git pull origin master

## Pushing Local Changes

After you write and commit more content locally, you can push your changes to the remote repository:

    git push origin master
    
This operation also reattaches remote `master` branch and `origin/master` branch to the same commit as your local `master` branch.

In case someone pushed commits you didn't fetch, your push may fail. In this case, fetch, merge and then push again:

    git fetch
    git merge origin/master
    git push origin master
