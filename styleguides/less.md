# LESS/CSS Style Guide

In this styleguide CSS will actually be LESS syntax.

## Quick Points

* Use four-space indentation.
* Never leave trailing whitespace.
* Use `//` comments instead of `/* */`.

## Documentation

Every file should include a header like so:

```less
# Module Name
### Description of what it does.
```

Comments generate docs in markdown fashion.

## Blocks

Use a single space before `{` in rule blocks and place it on the same line as
the last selector.

Prefer to keep selectors on the same line. Wrap if it's hard to read.

Pad modifiers like `+`, `>`, and `~` with a single space.

## Properties & Values

Use a single space after `:` in declarations. Not before.

Units should not be used with a `0` (`padding: 0;`).

Lead decimals with a `0` (`opactiy: 0.3;`).

Keep properties and values in lowercase and short if possible. Prefer shorthand
for hex values (`#fff`).

Prefer `em` when font size in relative to a component's context, `rem` when
setting fixed font sizes. Don't use units with `line-height`.

Stack properties like the box model with outer properties nearer the top and inner
or existential properties nearer the bottom. Place `display` at the top.

Example:

```less
.styleguide {
  display: none;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 100;
  float: left;
  clear: both;
  margin: 0;
  width: 300rem;
  height: 200rem;
  border: 1px solid #0f0;
  padding: 0;
  font: 1.5em helvetica, sans-serif;
  line-height: 2;
  color: #c00;
  background: rgba(0, 0, 0, 0.5);
  cursor: pointer;
}
```

## Nesting

Use nesting sparingly! It comes with a cost. A common mistake is to think of CSS preprocessor
nesting like the DOM. Not everything should be nested. Nesting merely saves you
the hassle of having to retype selectors multiple times for *modifying* situations.

Don't nest any deeper than **3 levels deep**.

Never nest an id `#` selector.

Never specify tags with id selectors (`ul#my-list`). This trashes speed!

Place a single empty line between nested declarations.

Order your nesting blocks in the general order of your HTML structure.

## Mobile-First & Media Queries

If at all possible rely on pre-defined media queries set on classes (`.col-lg-6`).

When writing media queries prefer to use pre-defined breakpoints (`@screen-sm-min`).

Place media queries at the bottom of the file. Prefer to nest selectors within the query
rather than multiple queries within selectors.

## Nomenclature

Classes are for appending styles. Ids are for context lookups.

Use `lower-case-hyphen-css-case`.

Prefer direct descendant selectors by defualt (`ul > li`).

Use as few selectors as needed to match an element.

Describe what a components function is rather than using generic names.

## Images

Use CSS properties wherever possible over images.

Image filenames are specially named with each part separated by a hyphen. A name
should contain the following:

1. UI Module
1. Function of Module
1. Interative State *(optional)*

Examples:

    module-function-state.png
    accordion-titlearrow-on.png
    nav-bg.png
    icon-facebook.png
    logo-sitename.png
    btn-buynow.png

Use shorthand for things that are easily recognizable like `bg`, `bd`, and `btn`.

Prefer to use SVG over bitmap.
