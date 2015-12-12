## CSS Style Guide

Set colors to lowercase

```css
/* Bad */
.a {
  color: #FFF;
    background-color: #AAA;

}

/* Good */
.a {
  color: #fff;
    background-color: #aaa;

}
```

Set block to indent to 2 spaces

```css
// Bad
.a {
    color: #fff;
    .b {
            color: #ccc;
                
    }

}

// Bad
.a {
    color: #fff;
    .b {
            color: #ccc;
                
    }

}

// Good
.a {
  color: #fff;
  .b {
      color: #ccc;
        
  }

}
```

Use shorthands for hexadecimal colors

```css
// Bad
.a {
  color: #ffcc00;
    background: #cccccc;

}

// Good
.a {
  color: #fc0;
    background: #ccc;

}
```

Write selectors in lowercase

```css
// Bad
LI > A {
  color: #333;

}

// Good
li > a {
  color: #333;

}
```

Remove leading zero

```css
.a {
  padding: 0.5em;
    font-size: 0.8em;

}

.a {
  padding: .5em;
    font-size: .8em;

}
```

Use single quotes

```css
// Bad
p[href^="https://"]:before {
  content: 'secure';

}

// Good
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
// Bad
.a {
  color : #fff;
  top : 0;
}

// Good
.a {
  color: #fff;
  top: 0;
}
```

Add space after colon

```css
// Bad
.a {
  color:#fff;
  top:0;
}

// Good
.a {
  color: #fff;
  top: 0;
}
```

Add a line break between declarations 

```css
// Bad
.a {
  color: #999; top: 0; height: 0;
}

// Good
.a {
  color: #999;
  top: 0;
  height: 0;
}
```

Add a space before open brace

```css
// Bad
.a{
  color: #333;
}

// Good
.a {
  color: #333;
}
```

Add a line break after opening brace

```css
// Bad
.a { color: #333;
}

// Good
.a { 
  color: #333;
}
```

Add a line break before closing brace

```css
// Bad
.a {
  color: #fff; }

// Good
.a {
  color: #fff;
}
```

Add a line break after selector delimiter

```css
// Bad
.a, .b {
  color: #333;
}

// Good
.a,
.b {
  color: #333;
}
```

Remove units in zero-valued dimensions

```css
// Bad
.a {
  border: 0px;
}

// Good
.a {
  border: 0;
}
```
