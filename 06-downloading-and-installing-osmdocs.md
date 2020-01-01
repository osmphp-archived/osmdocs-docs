# Downloading And Installing OsmDocs

Minimum installation steps:

1. Install [PHP 7.2](https://www.php.net/downloads.php) or later.

2. Download [pre-installed project](#todo).

3. Start PHP built-in Web server in the project's root directory:

        php -S localhost:8000 -d public

After OsmDocs is installed and running, edit book contents in the project's `data/book` directory and check how it looks in browser using URL address <http://localhost:8000/>. 

Note that OsmDocs caches book contents. Whenever you add/rename/delete book files, clear the cache in the project's root directory:

    php fresh

The minimum installation described above has certain limitations: 

* OsmDocs works faster under full-fledged Web server such as [Nginx](https://nginx.org/en/download.html) or [Apache](https://httpd.apache.org/download.cgi). 
* Using [Node.js](https://nodejs.org/en/download/) and [Gulp.js CLI](https://gulpjs.com/docs/en/getting-started/quick-start) for automatically clearing book cache is more convenient than doing it manually  using `php fresh` command.
* 

Read this article in full to pick professional installation options instead:        

{{ toc }}

## Using Nginx

At the very least, install [PHP 7.2](https://www.php.net/downloads.php) or later.

Other recommended software:

1. [Nginx](https://nginx.org/en/download.html) or [Apache](https://httpd.apache.org/download.cgi) Web server.
2. [Node.js](https://nodejs.org/en/download/) for building CSS, JS and other assets.
3. [Gulp.js CLI](https://gulpjs.com/docs/en/getting-started/quick-start) for automatically clearing book cache after content changes.
4. [Osm CLI](https://github.com/osmscripts/osm-runner) for fast module development.
5. [Let's Encrypt Certbot](https://letsencrypt.org/docs/client-options/) for free SSL certificate.

