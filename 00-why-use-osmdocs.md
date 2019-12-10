# Why Use OsmDocs

> [If isn't documented, it doesn't exist](https://blog.codinghorror.com/if-it-isnt-documented-it-doesnt-exist/) - Jeff Atwood.

This project started as I searched for a documentation tool for my open-source projects and for a blog. While existing solutions are very good at what they do, I felt that something is missing. And I thought to myself: "Well, we as an industry are very efficient at writing and deploying code and yet, writing and deploying content is not like that".

All solutions I saw fell into three big categories.

1. In the first category, platforms offer their own rich text editor available in website's backend. While it seems convenient at the first glance, rare developer would like to edit her code in website's text editor (and certainly I wouldn't!):

    * Session may expire and the latest changes may be lost.
    * We all have our own preferences about how perfect code editor looks like. There is no chance that a single provider can offer the perfect editor for all. Especially in the long run.

2. Another category is static website generators. You create content files, run a tool and build a website. With every content update, you run the tool again to rebuild the website.

3. Finally, solutions from the last category provide hosting of websites deployed from a Git repository containing content files. You edit files, push the changes and you website is deployed. With every content update, you just push again to deploy the website.

    While solutions from the second and the third categories resolve problems of the first category, I felt that the build step in static website generators and the push-to-deploy step in Git repository content hosting solutions slow down edit-preview loop. I wanted to edit the changes and then just check how they look in the browser, without additional "manual labor".

And so I built OsmDocs.

In OsmDocs, you edit content in some directory on the server and then check how it looks in a browser.

Or even better, you edit content in a local directory and run a tool which syncs the changes to the server as you edit automatically. Such tools are already available in IDEs we normally use for coding and this User Guide reviews such tools. If there is none in yours, use a standalone file sync software such as [OsmSync](using-sftp/osmsync.html), also the work of yours truly.

This way, edit-preview loop is very fast.

Also, there is:

* **No vendor lock-in**

    You may pick any text editor which works best for you. Any SFTP client. You don't even need to use OsmDocs server - you can download self-hosted solution instead.

* **Push-to-deploy Git repository feature**

    Git is indispensable when working in a team and deploying final result of the team effort automatically from the Git repository is very convenient.

* **Open-source self-hosted solution**

    All your writing will have professional look, will be easy to navigate and SEO friendly from day 1.

    Still, you can self-host and customize it as needed.

* More

    You will find more productivity hacks such as table of contents placeholders which expand dynamically when the page is rendered.

    You can host the website on OsmDocs server under your own domain name.

If you have software development background, you will find everything familiar and intuitive. If not, keep reading - I tried hard to explain all of that to you in this User Guide.

And by the way, I eat my own dog's food - this User Guide itself is hosted on OsmDocs!
