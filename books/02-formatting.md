# Formatting

Contents:

{{ toc }}

## Markdown

All book pages use Markdown.

Markdown is lightweight markup language for plain text files. It is easy to read in the original text file. It is also nicely shown as HTML.

It has been written a lot about Markdown, and I couldn't explain it better:

* [Getting Started](https://www.markdownguide.org/getting-started/)
* [Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)
* [Basic Syntax](https://www.markdownguide.org/basic-syntax/)
* [Extended Syntax](https://www.markdownguide.org/extended-syntax/)

## Tags

In addition, you can also use **tags** in Markdown files - placeholders which expand dynamically when the page is rendered.

### `child_pages`

Renders hierarchy of child pages of the current page.

Use this tag in a separate paragraph:

    {{ child_pages }}

You can also limit depth of child page hierarchy by using `depth` parameter. For example, render only direct children of the current page with:

    {{ child_pages depth="1" }}

### `toc`

Renders hierarchical table of contents of the current page.

Use this tag in a separate paragraph:

    {{ toc }}

This tag makes table of contents from all the headers n the page except top level header and headers using single-dash syntax.

You can also limit depth of table of contents hierarchy by using `depth` parameter. For example, render only second-level headers of the current page with:

    {{ toc depth="1" }}
