# Directory Structure

Contents:

{{ toc }}

## Pages

* Every book contains at least one file - `index.md` - representing topmost or **home** page of the book. It is added during book creation automatically. Don't delete this file.

* Beside this file, you may add more Markdown files to the book directory as child pages of the home page.

    **Example**

    Book directory:

        index.md
        page1.md
        page2.md

    Logical page structure:

        index.md
            page1.md
            page2.md

* You may also create a directory with the same name as child page (excluding file extension). Any Markdown files in such directory are child pages of that child page.

    **Example**

    Book directory:

        page1/
            topic1.md
            topic2.md
        index.md
        page1.md
        page2.md

    Logical page structure:

        index.md
            page1.md
                topic1.md
                topic2.md
            page2.md

    This way, you can create book page structure of any depth. I recommend limiting book depth to one or two levels as deep page structure may make your book harder to navigate.

## Table Of Contents

Add table of contents to your pages to make them easier to navigate:

* Use [`{{ child_pages }}` tag](formatting.html#child_pages) in pages having child pages. This tag adds list of child pages to the page.

* Use [`{{ toc }}` tag](formatting.html#toc) in pages not having child pages of their own. This tag adds list of page headings to the page.

## Page Order

* Pages are always ordered by file name.

    **Example**

    Book directory:

        index.md
        controllers.md
        databases.md
        getting-started.md

    Logical page structure:

        index.md
            controllers.md
            databases.md
            getting-started.md

* Add numeric **order prefix** to file names to change the order.

    **Example**

    Book directory:

        index.md
        01-getting-started.md
        02-controllers.md
        03-databases.md

    Logical page structure:

        index.md
            01-getting-started.md
            02-controllers.md
            03-databases.md

* Don't add order prefix to directories containing deeper child pages.

    **Example**

    Book directory:

        controllers/
            01-rendering-pages.md
            02-sending-ajax-responses.md
        index.md
        01-getting-started.md
        02-controllers.md
        03-databases.md

    Logical page structure:

        index.md
            01-getting-started.md
            02-controllers.md
                01-rendering-pages.md
                02-sending-ajax-responses.md
            03-databases.md

    Such "inconsistency" makes page order easier to manage: you have to rename only one file name instead of two.

## Page URLs

URL of a page (relative to book URL) is almost the same as page relative file path inside the book directory with few exceptions:

* URL of the book home page is always `/`
* Order prefixes are not included (again, page order is easier to manage: if you change page order, URLs stay the same)
* `.md` extension is replaced with `.html` extension (so browsers and search bots "see" book pages as static HTML pages)

**Example**

Book directory:

    controllers/
        01-rendering-pages.md
        02-sending-ajax-responses.md
    index.md
    01-getting-started.md
    02-controllers.md
    03-databases.md

Logical page structure:

    index.md
        01-getting-started.md
        02-controllers.md
            01-rendering-pages.md
            02-sending-ajax-responses.md
        03-databases.md

Page URLs:

    /
    /getting-started.html
    /controllers.html
        /controllers/rendering-pages.html
        /controllers/sending-ajax-responses.html
    /databases.html

## Links To Pages

Use relative URLs to link pages in the same book.

**Example**

Book directory:

    controllers/
        01-rendering-pages.md
        02-sending-ajax-responses.md
    index.md
    01-getting-started.md
    02-controllers.md
    03-databases.md

Page URLs:

    /
    /getting-started.html
    /controllers.html
        /controllers/rendering-pages.html
        /controllers/sending-ajax-responses.html
    /databases.html

`index.md` and `03-databases.md` are in the same directory, so link from `index.md` to `03-databases.md` is just file name:

    [Databases](databases.html)

`03-databases.md` is in parent directory of `01-rendering-pages.md`, so link from `01-rendering-pages.md` to `03-databases.md` should contain navigating to parent directory:

    [Databases](../databases.html)

Backward link from `03-databases.md` to `01-rendering-pages.md` should contain navigating to child directory:

    [Rendering Pages](controllers/rendering-pages.html)

## Links To Headings

OsmDocs makes every heading on every book page linkable. Use relative links to the book page combined with hash tag of the heading.

**Example**

Book directory:

    controllers/
        01-rendering-pages.md
        02-sending-ajax-responses.md
    index.md
    01-getting-started.md
    02-controllers.md
    03-databases.md

Page URLs:

    /
    /getting-started.html
    /controllers.html
        /controllers/rendering-pages.html
        /controllers/sending-ajax-responses.html
    /databases.html

Contents of `03-databases.md`:

    # databases

    ## MySql

    ...

    ## SqLite

    ...

Link from `index.md` to `MySql` section of `03-databases.md`:

    [MySql Databases](databases.html#mysql)

Link from `01-rendering-pages.md` to `MySql` section of `03-databases.md`:

    [MySql Databases](../databases.html#mysql)

Link inside of `03-databases.md` to `MySql` section:

    [MySql Databases](#mysql)

## Images

Upload images into book directory and use relative URLs to add images to the book pages.

* **Example**

    Book directory:

        index.md
        01-getting-started.md
        concept-map.png

    Add `concept-map.png` to `01-getting-started.md` using Markdown image syntax and relative URL:

        ![Concept map](concept-map.png)

* **Example**

    Book directory:

        getting-started/
            concept-map.png
        index.md
        01-getting-started.md

    Add `concept-map.png` to `01-getting-started.md` using Markdown image syntax and relative URLs:

        ![Concept map](getting-started/concept-map.png)
