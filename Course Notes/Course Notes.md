# Udemy - 2020 Web Dev Bootcamp

[Link to to course.](https://apple.udemy.com/course/the-complete-web-development-bootcamp/)

[Course resources.](https://www.appbrewery.co/p/web-development-course-resources/)

- [Udemy - 2020 Web Dev Bootcamp](#udemy---2020-web-dev-bootcamp)
  - [Introduction to HTML](#introduction-to-html)
    - [Tags](#tags)
    - [Comments](#comments)
    - [HTML Boilerplate](#html-boilerplate)
  - [Intermediate HTML](#intermediate-html)
    - [Tables](#tables)
    - [Forms](#forms)

## Introduction to HTML

Aggregated web dev doumentation can be found at devdocs.io.

MDN uses thumbs down symbols to denote things that are deprecated.

Emmet abbreviations can be found at emmet.io.

### Tags

Most tags need to be closed explicitly. Some, like `<br>` or `<hr>` don't (or can't). The rules can be found in the "tag omission" section of each tag's doc page.

Each tag can also accept certain attributes such as size or color.

### Comments

HTML comment syntax is kind of clunky but this is how it looks: `<!-- I'm a comment -->`.

### HTML Boilerplate

Meta tags are supplied in the `<head>` section of HTML files.

Unicode UTF-8 (`<meta charset="UTF-8">`) should be used as the default encoding attribute. In addition to text scripts, Unicode also has other non-text symbols like emojis.

The `description` meta-element attribute sets the text that will be displayed under the title of the webpage in search engine results.

## Intermediate HTML

### Tables 

Tables are used to display organized data or as a tool to style webpage elements direclty in HTML (or later in CSS). Header and footer rows can be called out explicitly or via `<th>` and `<tf>` tags. Most of the table styling attributes in HTML are deprecated. Styling should be done with CSS in practice.

Tables can be nested inside of tables. This is useful if you want to keep blocks of information grouped together within a larger table. I.e., you can make a $m$ x $n$ table where each element $T_{m, n}$ is itself an arbitrarily sized table.

### Forms

Forms are used to collect user inputs. Within the `<form>` element `<input>`s elements are specified along with a type attribute. Many default input types exist with built-in functionalities (see docs). Default input types are styled automatically and will look different across browsers.

 `<label>`s can either wrap `<input>`s or be associated with them via the `for=""` and `id=""` attributes, like so:

```HTML
    <form action="index.html" method="post">
        <label for="mailing-list">Join my readers' list</label>
        <input type="text", id="mailing-list">
    </form>
```

Input elements can be given a `name` attribute in addition to an `id`. The `name` will be associated with the value of the input field (as a "name/value" pair) when the form is submitted. I.e., the `name` is a variable whose value is set by the input data.