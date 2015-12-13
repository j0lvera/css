# CSS Style Guide

*An almost reasonable approach to CSS and Sass*

With content and examples stolen from:

- [Airbnb CSS / Sass Styleguide](https://github.com/airbnb/css)
- [Idiomatic CSS](https://github.com/necolas/idiomatic-css)
- [CSS-Tricks Style Guide](https://css-tricks.com/css-style-guides/)
- [CSSComb](http://csscomb.com/)

## Table of contents

1. [Terminology](#terminology)
2. [Formatting](#formatting)
3. [Comments](#comments)
3. [Sass](#sass)
5. [File Structure](#file-structure)

## Terminology

### Rule declaration

A “rule declaration” is the name given to a selector (or a group of selectors) with an accompanying group of properties.

```css
.paragraph {
  font-size: 18px;
  line-height: 1.5;
}
```

### Selectors

In a rule declaration, “selectors” determine which elements in the DOM tree will be styled by the properties. Selectors can match HTML elements, as well as a class, ID, or any of its attributes.

```css
.selector {
  /* ... */

}

[aria-hidden] {
  /* ... */
}
```

### Properties

Properties are what give the selected elements of a rule declaration their style. Properties are key-value pairs, and a rule declaration can contain one or more property declarations.

```css
/* some selector */ {
  background: #fff;
  color: #333;
}
```

## Formatting

Write colors in lowercase.

```css
/* Bad */
.selector {
  color: #FFF;
  background-color: #AAA;
}

/* Good */
.selector {
  color: #fff;
  background-color: #aaa;
}
```

Indent with 2 spaces, not 4 spaces or tabs.

```css
/* Bad */
.selector {
    color: #fff;
    .b {
        color: #ccc;
    }
}

/* Good */
.selector {
  color: #fff;
  .b {
    color: #ccc;
  }
}
```

Use shorthands for hexadecimal colors.

```css
/* Bad */
.selector {
  color: #ffcc00;
  background: #cccccc;
}

/* Good */
.selector {
  color: #fc0;
  background: #ccc;
}
```

Write selectors in lowercase.

```css
/* Bad */
LI > A {
  color: #333;
}

/* Good */
li > a {
  color: #333;
}
```

Remove leading zero.

```css
/* Bad */
.selector {
  padding: 0.5em;
  font-size: 0.8em;
}

/* Good */
.selector {
  padding: .5em;
  font-size: .8em;
}
```

Use single quotes.

```css
/* Bad */
p[href^="https://"]:before {
  content: 'secure';
}

/* Good */
p[href^='https://']:before {
  content: 'secure';
}
```

Sort properties following the order:

1. Position
2. Box model
3. Typographic
4. Visual

```css
.declaration-order {
  /* Position */
  position: absolute;
  top: 0;
  right: 0;

  /* Box model */
  display: block;
  float: right;
  width: 6em;

  /* Typographic */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;

  /* Visual */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  opacity: 1;
}
```

Add a space after colon, but not before.

```css
/* Bad */
.selector {
  color : #fff;
  top : 0;
}

/* Bad */
.selector {
  color:#333;
  top:0;
}

/* Good */
.selector {
  color: #fff;
  top: 0;
}
```

Add a line break between declarations.

```css
/* Bad */
.selector {
  color: #999; top: 0; height: 0;
}

/* Good */
.selector {
  color: #999;
  top: 0;
  height: 0;
}
```

Add a space before open brace.

```css
/* Bad */
.selector{
  color: #333;
}

/* Good */
.selector {
  color: #333;
}
```

Add a line break before and after opening brace.

```css
/* Bad */
.selector { color: #333;
}

/* Bad */
.selector {
  color: #333; }

/* Good */
.selector { 
  color: #333;
}
```

Add a line break after selector delimiter

```css
/* Bad */
.selector, .b {
  color: #333;
}

/* Good */
.selector,
.b {
  color: #333;
}
```

Remove units in zero-valued dimensions

```css
/* Bad */
.selector {
  border: 0px;
}

/* Good */
.selector {
  border: 0;
}
```

## Comments

- Comments in their on line. Avoid end-of-line comments.
- Keep line-length to 80 columns.

Usage:

```css
/**
 * Document title
 */

/**
 * Document title with a short description
 *
 * Donec id elit non mi porta gravida at eget metus. 
 */

/*
 * Section comment block
 */

/* 
 * Section comment block with a short description
 *
 * Donec id elit non mi porta gravida at eget metus. 
 */

/* Basic comment */
```

## Sass

Order extend/inheritance by:

- `@extend`s
- `@include`s
- Regular styles
- Nested pseudo classes and pseudo elements
- Nested selectors

```scss
// Example
.selector {
  @extend %clearfix;
  @include .module;

  background-color: #fff;

  &:hover {
    background-color: #eee;
  }

  &::before {
    background-color: #ccc;
  }

  .nested-selector {
    float: left;
    display: block;
  }
}
```

Don't hardcode colors, use variables instead:

```scss
// Bad
.entry-title {
  color: $00f;
}

// Good
$brand-primary-color: #00f;

.entry-title {
  color: $brand-primary-color;
}
```

Nest your media queries.

```scss
// Bad
.selector {
  float: left;
  width: 50%;
}

// End of file 
@media (min-width: 48em) {
  .selector {
    float: left;
    width: 50%;
  }
}


// Good
.selector {
  float: left;
  width: 50%;

  @media (min-width: 48em) {
    float: none;
    width: 100%;
  }
}
```

## File Structure

```scss
// Utils
@import "utils/variables";
@import "utils/utils";

// Base
@import "base/base";
@import "base/forms";
@import "base/typo";
@import "base/tables";

// Components
@import "components/buttons";
@import "components/feedback";
@import "components/icons";
@import "components/images";
@import "components/navigation";

// Layout
@import "layout/footer";
@import "layout/grid";
@import "layout/header";
@import "layout/main";
@import "layout/sidebar";

// Pages
@import "pages/home";
@import "pages/contact”;

// Anything that can be categorized later
@import “todo”;
```

### `utils/`

Here are the files that have functions, mixins, extends, or classes that we use more than once in different folders.

### `base/`

Basic styles like `html`, `body`, `p`, and `a` tags.

### `components/`

UI components that can be used to build layouts

### `layout/`

Header, footer, sidebar and other elements that makes the site structure.

Layouts are built with components. We code the header with the `.site-logo`, `.site-navigation`, and `.social-icons` components and make them work together inside the `_header.scss` layout.

### `pages/`

Styles for specific pages:

- `_home.scss`
- `_contact.scss`
- `_portfolio.scss`
