# Git Concepts

Git is the world's leading distributed version control system.

Git is mostly used to store software's source code as it especially shines in handling text files. It is also often used to store documentation files.

In this guide, we will use Git to store book files and to organize team workflow.

To run Git operations, we will use command line. You may also use a visual alternative:

* [GitHub Desktop](https://desktop.github.com/)
* [Sourcetree](https://www.sourcetreeapp.com/)
* [PhpStorm](https://www.jetbrains.com/help/phpstorm/using-git-integration.html) or other [JetBrains](https://www.jetbrains.com/products.html) product

{{ toc }}

## Learning Resources

Git is known for its steep learning curve. Keep in mind, however, that lots of people use it every day, and that you can do that too.

To get started with Git, check official learning resources:

* [Pro Git book](https://git-scm.com/book/en/v2) by Scott Chacon and Ben Straub
* [Introductory videos](https://git-scm.com/videos)
* [Curated list of tutorials](https://git-scm.com/doc/ext)
* [Reference documentation](https://git-scm.com/docs)

## Installing Git

1. Download [Git](https://git-scm.com/downloads), run the installer and follow installations steps.
2. Provide Git with information about yourself by running the following commands (replace placeholders with your name and email):

        git config --global user.name "John Doe"
        git config --global user.email johndoe@example.com

## Repository

Git **repository** is a directory storing all the versions of your book.

To get started with Git, download your book files to a local directory (we will refer to it as `{book_dir}`) and create a repository for it by running the following commands in shell:

    cd {book_dir}
    git init

Git repository is created in `{book_dir}/.git` subdirectory.

## Commits

**Commit** is a single version of all book files stored in Git repository.

Create a initial commit or "the first version" of your book files by running the following commands in shell:

    cd {book_dir}
    git add .
    git commit -am "Initial commit"

Do some changes in the book directory - create, edit or delete files. After that, create another commit or "the second version" containing all changed book files  by running the the same commands in shell:

    cd {book_dir}
    git add .
    git commit -am "Describe your changes"

Internally, Git stores full copy of all your book files in every commit. It means that you will be able to get every version of your book later if you need it.

By the way, you may use the verb "to commit" instead of "to create a commit".

Git also stores who created the commit and when.

Run the following command in shell to see all your commits (it's quite long, make sure to copy it to the end):

    git log "--pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset'" --abbrev-commit
