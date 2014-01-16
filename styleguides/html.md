# HTML Formatting Guide

## Indentation

Use four-space indentation.

## Whitespace

Never leave trailing whitespace or whitespace on empty lines.

## Validation

All HTML must pass the WC3 Validator.

Warning are OK.

## Doctype

Always use the HTML5 Doctype.

    <!DOCTYPE html>

## Head

Asset links like stylesheets, icons, RSS, etc. should reside in the head.

Like-tags should be grouped together. Don't mix `<meta>` tags with `<link>`
tags or any `<script>` tags.

Script tags should be kept to a minimum in favor of the bottom of the `<body>`.

## Body

Place `<script>` tags before the end `</body>` tag.

## Tags

Limit the use of `<img>` tags where possible and substitute for background images.

Instead of using `<br>` more than once, wrap text in `<p>` tags.

List items should always be wrapped in `<ul>`, `<ol>`, or `<dl>`.

As a general rule separate tags by a newline. Opening and Closing tags should wrap
to their own lines unless they contain no or little content.

Do not use end slashes for self-closing tags (`<img src=”myimg.png” alt>`).

Good:

    <img src="myimg.png" alt />
    <br />

Bad:

    <img src="miimg.png" alt>
    <br>

## Attributes

Always use double quotes `<p class="some-class">`.

Prefer a `title` attribute for anchor tags.

Do not use quotes for empty attributes. Just specify the attribute without the
`=""`.

Do not use event attributes.

## Structuring

Use HTML5 tags whenever lexically possible. Use `<nav>` for navigation, `<header>`
for headers, `<footer>` for footers, `<section>` for layout sections, `<aside>`
for pull-out content, and `<article>` for modular, repeatable markup.

Do not use `<section>` in place of `<div>`. Use them only for major sections
of modular layout.

