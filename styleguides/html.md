# HTML

This style guide is concerned with HTML but also includes Angular-flavored
HTML. In particular, Angular attributes can load up an HTML tag.

## Quick Points

* Use four-space indentation.
* Never leave trailing whitespace.
* Always use HTML5.

## Head

Asset links like stylesheets and icons that are needed on page set up should reside in the head.

Group tags together. Don't mix `<meta>` tags with `<link>`.

Generally, tags should be listed in the order: meta, link, script.

Script tags should be kept to a minimum to speed page loading.

## Body

Place `<script>` tags before the `</body>` tag.

## Tags

Limit the use of `<img>` tags where possible and substitute for background images.

Instead of using `<br>` more than once, wrap text in `<p>` tags.

Don't repeat spacing tags or characters (`<br>`, `&nbsp;`, `<p></p>`). Prefer
to use CSS spacing instead.

List items should always be wrapped in `<ul>`, `<ol>`, or `<dl>`.

As a general rule separate tags by a newline. Opening and Closing tags should wrap
to their own lines unless they contain no or little content.

Do not use end slashes for self-closing tags (`<img alt>`, not `<img alt/>`).

## Attributes

Always use double quotes `<p class="some-class">`.

Prefer a `title` attribute for anchor tags.

Do not use quotes for empty attributes. Just specify the attribute without the
`=""`.

Do not use JS event attributes. Rely on Angular (`ng-click="..."`).

When a tag contains many attributes wrap at the end of the line to a single 
attribute per line, indent two steps in, and place the closing `>` after the last 
attribute:

```html
<section id="section-id" class="one two three four"
        ng-click="doSomething()"
        validate
        required="true">
    <div class="inner-div">
```

## Structuring

Use HTML5 tags whenever lexically possible. Use `<nav>` for navigation, `<header>`
for headers, `<footer>` for footers, `<section>` for layout sections, `<aside>`
for pull-out content, and `<article>` for modular, repeatable markup.

Do not use `<section>` in place of `<div>`. Use them only for major sections
of modular layout.

## Scripts

Prefer to place JS code in an external file.

## Comments

Comments in HTML should be avoided.

## Includes

If at all possible avoid using `ng-include` in favor of directives with templates.
