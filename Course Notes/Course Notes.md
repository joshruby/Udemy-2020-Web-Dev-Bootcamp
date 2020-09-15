# Udemy - 2020 Web Dev Bootcamp

[Link to to course.](https://apple.udemy.com/course/the-complete-web-development-bootcamp/)

[Course resources.](https://www.appbrewery.co/p/web-development-course-resources/)

- [Udemy - 2020 Web Dev Bootcamp](#udemy---2020-web-dev-bootcamp)
  - [HTML](#html)
    - [Tags](#tags)
    - [Comments](#comments)
    - [HTML Boilerplate](#html-boilerplate)
    - [Tables](#tables)
    - [Forms](#forms)
    - [Divs](#divs)
    - [Spans](#spans)
  - [CSS](#css)
    - [Values](#values)
    - [Browser Defaults](#browser-defaults)
    - [Inline CSS](#inline-css)
    - [Internal CSS](#internal-css)
    - [External CSS](#external-css)
    - [Selectors - Tags, Classes, and IDs](#selectors---tags-classes-and-ids)
      - [Pseudo Classes](#pseudo-classes)
    - [The Box Model of Website Styling](#the-box-model-of-website-styling)
    - [The Display Property](#the-display-property)
    - [Positioning](#positioning)
      - [Static](#static)
      - [Relative](#relative)
      - [Absolute](#absolute)
      - [Fixed](#fixed)
    - [Centering in CSS](#centering-in-css)
    - [Fonts](#fonts)

## HTML

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

### Divs

`Div` elements are used to create divisions within HTML files (i.e. groups of other elements) so that they can later be styled together using CSS. No styling is applied to divs by default.

### Spans

Spans, like divs, are used to group elements or sections of a single element so that they can be styled togther in CSS. By default, unlike divs, spans are "inline" elements rather than "block" elements ([more on this in the CSS section here)](#the-display-property). For example, a `<span>` can be used to style a selection of words in a paragaph without splitting the paragaph element up into different blocks.

## CSS

### Values

Values can be specified absolutely, such as with a pixel value, or relatively, such as with a % or em (which is relative to the font size of the surrounding element).

### Browser Defaults

Even if you don't provide any CSS, some amount of styling will be done automatially by the browser. The default CSS attributes for HTML elements can be [found here](https://www.w3schools.com/cssref/css_default_values.asp). It's also possible to determine which CSS attributes are being applied to any HTML element by using the Chrome developer tools inspector or *Pesiticide* extension.

If you attempt to style an element and see an unexpected result, a good first debugging step is to check which CSS attributes are being applied automatically and figure out how they relate to and interact with the attriubutes you specified.

### Inline CSS

CSS attributes can be passed directly in HTML tags, but generally speaking it's better to use internal or external CSS.

### Internal CSS

Internal CSS declarations can be made inside of HTML files by placing a `<style>` element between the `<head>` and `<body>` elements. Within `<style>`, CSS attributes are defined like this:

```HTML
 <style>
    body {
      background-color: blue;
    }
  </style>
```

This snippet will style the entire `body` element wit the specified `background-color`.

Internal CSS only applies to the single HTML file it's specified in.

### External CSS

External .css files can be linked to an html file via self-closing `link` elements wihin the HTML `head` element like so:

```HTML
 <head>
    <meta charset="UTF-8" />
    <link rel="stylesheet" href="css/styles.css">
    <title>Josh's Site</title>
  </head>
```

Note that internal CSS overrules external CSS where there are collisions. The Chrome inspection tool will let you know which rules are being applied to any element and what their hierarchy is.

### Selectors - Tags, Classes, and IDs

Classes and ids are used to apply styles to specific elements.

In general, the more specific the selector, the higher in the hierarchy it sits.

Classes are specified with .s can be applied to any number of elements within an HTML file. A single element can also how multiple classes associted with it that are separated by spaces.

Ids are specified with #s and can only be applied to one element per HTML file and each element can only be associated with one id.

Classes are much more widely used than ids in practice.

#### Pseudo Classes

Some HTML elements change state when interacted with. Pseudo classes are used to change the display properties of elements only when they're in a particular state. All pseudo classes contain a leading colon.

For example, to change an element's background color when it's hovered over, the `:hover` psuedo class is used:

```CSS
img:hover {
    background-color: white;
}
```

### The Box Model of Website Styling

Content sits at the center, surounded by the padding. Outside of the padding sits the border, followed by the margin (empty space between elements).

When the height or width of an element is specified, only the content's dimensions are changed. The total size of the element is governed by the sum of the dimensions of the content, padding, border, and margin.

### The Display Property

**Block** elements take up the entire page width by default but have configurable dimensions. Text elements are styled as blocks by default.

**Inline** elements take up the minimum amount of space necesary to "span" their dimensions. As a result, the dimensions of inline elements cannot be explicitly set (e.g. you can't set an inline element to have a width of 100px). Common inline elements are `<span>`s, `<img>`s, and `<a>`s.

**Inline-block** elements are displayed inline, but have configurable dimensions like block elements.

**None** elements are hidden and removed from the webpage entirely. Setting `visbility: none;` is similar to `display: none;`, but retains the space that the element takes up on the page as blank space.

### Positioning

#### Static

Elements are statically positioned by default in the order they're written in HTML. If two elements are nested, the child will be positioned "on top" of the parent (imagine that there's a z-axis protruding perpendicular to the screen). The default static position can be overwritten if desired.

#### Relative

Relative positions are referenced to the default static position of each element.

If an element is moved via relative positioning, it's new position will not affect any other elements' position. It's as if an invisble placeholder is kept in the original position of the moved element.

Changing and element's relative-position is akin to modifying it's margin.

#### Absolute

Absolute positioning positions elements relative to their parent (which could be the entire `<body>`). Here, parent is defined as the closest parent element that is *relatively* positioned.

Changing and element's absolute position is akin to modifying the margin between it and its parent.

Unlike relatively-positioned elements, absolutely-positioned elements do change the flow of the webpage. They do not leave behind a "ghost" placeholder. I.e., they are taken "out of the flow" of the webpage, causing the other elements to be "re-flowed".

#### Fixed

Fixed-position elements stay in the positions they're placed at (via static, relative, or absolue positioning) even when the user changes the view of the webpage (such has by scrolling). E.g., think of a nav bar that maintains its position at the top of a webpage even when the user scrolls down to view other content.

### Centering in CSS

Setting `text-align: center;` in a *parent* element will center any children within it that don't have a specified width (e.g. block elements that span the entire width of the webpage or inline block elements).

`auto` margin values can also be used like so:

```CSS
h1 {
  margin: 0 auto;
}
```

Here, the top and bottom margins will be 0 and the right and left margins will be automatically adjusted to center the element.

Block elements with explicitly defined widths 

### Fonts

