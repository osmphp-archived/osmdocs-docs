# Downloading And Installing OsmDocs

To get started, [download OsmDocs project](#downloading-project-files) and configure the Web server to show it in your browser. Then just edit the book contents in the `data/book` directory. 

For the Web server, I recommend [Nginx](#nginx). You can also use [Apache](#apache) or [PHP built-in Web server](#php-built-in-web-server).

As you edit, [watch book files](#watching-book-files) to refresh the table of contents.

[Update OsmDocs](#updating-osmdocs) to the latest version periodically. 

OsmDocs is an open-source project. Feel free to customize it or [contribute](contributing-to-osmdocs.html).

Contents:

{{toc}}

## Prerequisites

You will need:

* [PHP 7.2](https://www.php.net/downloads.php) or later
    * and [Composer](https://getcomposer.org/download/) for installing and updating OsmDocs
* [Node.js](https://nodejs.org/en/download/) for watching files and building assets
    * and [Gulp.js CLI](https://gulpjs.com/docs/en/getting-started/quick-start)
* [Nginx](https://nginx.org/en/download.html)
    * or [Apache](https://httpd.apache.org/download.cgi) Web server
    * or PHP built-in Web server for local use

## Placeholders

This guide uses `{placeholders}`, please replace them as follows:

* `{home_dir}` - directory where you keep all the projects. On Linux, consider `~` (your user's home directory). 
* `{project}` - project directory name and Web domain name. Example: `my.osmdocs.com`.
* `{server_ip}` - IP of the server on which the project is installed. For your computer, it is `127.0.0.1`. 

## Downloading Project Files

1. Download all the project files, install NPM modules and build JS, CSS and other assets in shell:

        cd {home_dir}
        composer create-project osmphp/osmdocs {project}

    In the rest of this guide, `{home_dir}/{project}` is referred to as **project root directory**.  

2. To enable book rendering, create `config/settings.php` file with the following contents:

        <?php
        
        return [
            'doc_url_path' => '',
        ];  

3. Copy book files to `data/book` directory. At the very minimum there should be `index.md` in this directory.  

## Configuring The Web Server

### Nginx

1. Add project directory to Nginx configuration in project's root directory, with `root` user:

        php run config:nginx

2. Add a line to your OS `hosts` file (or DNS configuration of your hosting provider) to resolve `{project} to the server's IP address`. 

        {server_ip} {project}

3. The book is available at URL address <http://{project}/>.

### Apache

1. In Apache `htdocs` directory, create a symlink to the `public` directory of the project.

    On Linux, run:
    
        ln -s "{home_dir}/{project}/public" "{apache_htdocs_dir}/{project}"
    
    On Windows, run with administrative privileges:
    
        mklink /d "{apache_htdocs_dir}/{project}" "{home_dir}/{project}/public"

2. [Enable Apache `AllowOverride All` directive](https://stackoverflow.com/questions/18740419/how-to-set-allowoverride-all).

3. The book is available at URL address <http://{server_ip}/{project}/>.

### PHP Built-In Web Server

Locally, you can avoid installing and configuring full-fledged Web server. Instead:

1. Start PHP built-in Web server by running the following command in the project's root directory:
                                                                                    
        php -S localhost:8000 -d public

2. The book is available at URL address <http://localhost:8000/>.

## Editing Book Files

Edit the book in `data/book` directory.
    
### Watching Book Files

OsmDocs caches table of contents for faster rendering. Keep the cache fresh with the following command run in the project's root directory:

    npm run watch-data

### Clearing The Cache Manually 

Alternatively, you may clear the cache manually after modifying book contents by running the following command in the project's root directory:

    php fresh

## Updating OsmDocs 

Use Composer in the project's root directory to update the project to the latest version:

    composer update
