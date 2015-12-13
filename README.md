## CSS Style Guide

## Table of contents

1. [Overview](#overview)
2. [Formatting](#formatting)
3. [Comments](#comments)
4. [File Structure](#filestructure)
4. [Sass](#sass)

## Overview

### Fromatting

- Use 2 spaces, not 4 spaces or tabs.
- 1 selector or parameter per line.
- Add a single space after, but not before, the `:` character.
- Put a space before opening brace `{`
- Closing brace `}` on its own line.
- Use hyphens for class names, not underscores or camelCase.
- Put blank lines between rule declarations

Set colors to lowercase

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

Set block to indent to 2 spaces

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

Use shorthands for hexadecimal colors

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

Write selectors in lowercase

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

Remove leading zero

```css
.selector {
  padding: 0.5em;
  font-size: 0.8em;
}

.selector {
  padding: .5em;
  font-size: .8em;
}
```

Use single quotes

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
/* Example */
.declaration-order {
  position: absolute;
  top: 0;
  right: 0;
  display: block;
  float: right;
  width: 6em;
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  opacity: 1;
}
```

Remove space before colon

```css
/* Bad */
.selector {
  color : #fff;
  top : 0;
}

/* Good */
.selector {
  color: #fff;
  top: 0;
}
```

Add space after colon

```css
/* Bad */
.selector {
  color:#333;
  top:0;
}

/* Good */
.selector {
  color: #333;
  top: 0;
}
```

Add a line break between declarations 

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

Add a space before open brace

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

Add a line break after opening brace

```css
/* Bad */
.selector { color: #333;
}

/* Good */
.selector { 
  color: #333;
}
```

Add a line break before closing brace

```css
/* Bad */
.selector {
  color: #fff; }

/* Good */
.selector {
  color: #fff;
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

```css
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
@import "pages/home”;
@import "pages/contact”;

// Anything that can be categorized later
@import “todo”;
```

## Sass

Order extend/inheritance by:

- `@extend`s
- `@include`s
- Regular styles
- Nested pseudo classes and pseudo elements
- Nested selectors

```scss
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
$brand-primary-color: #00f;

.entry-title {
  color: $brand-primary-color;
}
```

Nest your media queries.

```scss
.selector {
  float: left;
  width: 50%;

  @media (min-width: 48em) {
    float: none;
    width: 100%;
  }
}
```
