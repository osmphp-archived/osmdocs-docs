# How It Works


 
Contents:

{{ toc }}


## Using Version Control

Having book copy locally as suggested above has yet another important benefit: you can put book files under Git version control and share it with other team members so that everyone can edit the same book on their own computers simultaneously and then merge individual efforts into the final result. With version control, you'll also have a clear change history of everyone's work. 

In case you don't know what is Git and how it works, this user guide provide this information along with organizing basic team workflow.

Also, host an additional book in your OsmDocs account which is rendered not from edits you make via SFTP, but rather from Git repository on GitHub or other Git hosting provider. This way, you can publish merged result of everyone's work each time new contribution is merged.

## Using Custom Domains

By default, every book's root URL is `https://osmdocs.com/{user}/{book}/`.

If you have purchased your own domain, show your book on it instead. So that book's root URL becomes `https://yourdomain.com/`.

This user guide is an example of using custom domain for book's root URL. As you can see, its URL is `https://docs.osmdocs.com`.

## Customizing OsmDocs

You can also download the open-source version of OsmDocs - the software which displays book files as a website - and install it on your server. 

Once installed, customize visual appearance and behavior of your copy of OsmDocs.

## Contributing To OsmDocs

And please, contribute back:

* Develop visual appearance of your book as a separate theme and publish it as a Composer package.
* Develop custom behavior of your book as a separate modules and publish your modules as a Composer package. 

 This way, everyone can easily install your themes and modules on their own copies of OsmDocs.
 
 Finally, please document your Composer packages. Use OsmDocs!