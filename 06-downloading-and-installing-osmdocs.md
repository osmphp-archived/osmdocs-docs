# Downloading And Installing OsmDocs

To get started, [download OsmDocs project](#downloading-project-files) and configure the Web server to show it in your browser. Then just edit the book contents in the `data/book` directory. 

For the Web server, I recommend [Nginx](#nginx). You can also use [Apache](#apache) or [PHP built-in Web server](#php-built-in-web-server).

As you edit, [watch book files](#watching-book-files) to refresh the table of contents.

[Update OsmDocs](#updating-osmdocs) to the latest version periodically. 

OsmDocs is an open-source project. Please [customize](#customizing-osmdocs) it or [contribute](contributing-to-osmdocs.html).

Contents:

{{toc}}

## Prerequisites

You will need:

* [PHP 7.2](https://www.php.net/downloads.php) or later
* [Nginx](https://nginx.org/en/download.html)
    * or [Apache](https://httpd.apache.org/download.cgi) Web server
    * or PHP built-in Web server for local use
* [Node.js](https://nodejs.org/en/download/) for watching data and source files
    * and [Gulp.js CLI](https://gulpjs.com/docs/en/getting-started/quick-start)
* [Composer](https://getcomposer.org/download/) for updating OsmDocs

## Downloading Project Files

## Configuring The Web Server

### Nginx

### Apache

### PHP Built-In Web Server

Locally, you can avoid installing and configuring full-fledged Web server. Instead:

1. Start PHP built-in Web server by running the following command in the project's root directory:
                                                                                    
        php -S localhost:8000 -d public

2. The book is available at URL address <http://localhost:8000/>.

## Watching Book Files

Alternatively, you may clear the cache manually by running the following command in the project's root directory:

    php fresh

## Updating OsmDocs 

## Customizing OsmDocs

### Watching Source Files



