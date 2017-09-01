# frontend-code-conventions
Generic code conventions for html, css and javascript.

## HTML

### Filenames
* Component templates > `some-name.template.html`
* Partials >  > `some-name.partial.html`
* Other files > `some-name.html`

### Formatting
* Sibling elements with children should have a line serving as separator.
* Use semantic html.
* Line breaking when attributes make the line are too long
- 1 soft tab indentation
- html attributes first (id, class, type, name...)
- angular attributes next (*, [], ())


## CSS

### Formatting
* Use soft tabs (2 spaces) for indentation.
* When using multiple selectors in a rule declaration, give each selector its own line.
* Put blank lines between rule declarations.
* Order properties alphabetacaly

**Bad**

```css
.avatar{
    color: black;
    border-radius:50%;
    border:2px solid white; }
.no, .nope, .not_good {
    // ...
}
```

**Good**

```css
.avatar {
  border-radius: 50%;
  border: 2px solid white;
  color: black;
}

.one,
.selector,
.per-line {
  // ...
}
```

### Selectors
* Use dashes in class selectors.
* Do not use ID selectors.
* Avoid element selectors, except for top level rules.

### Comments
* Comments on their own line. Avoid end-of-line comments.

### Border
* Use `0` instead of `none` to specify that a style has no border.

**Bad**

```css
.foo {
  border: none;
}
```

**Good**

```css
.foo {
  border: 0;
}
```


## Sass

### Syntax
* Use the `.scss` syntax, never the original `.sass` syntax
* Order your regular CSS and `@include` declarations logically (see below)

### Filename
* For angular components use `some-name.style.scss`

### Variables & Mixins
* Use baseline size variables whenever possible (`$baseline = 10px`).
* Use font-size mixin whenever possible.

### Colours
* Always use variables for colours. Do not use colour variable directly, use a semantic variable instead.

### Ordering of property declarations

1. Property declarations

    List all standard property declarations, anything that isn't an `@include` or a nested selector.

    ```scss
    .btn-green {
      background: green;
      font-weight: bold;
      // ...
    }
    ```

2. `@include` declarations

    Grouping `@include`s at the end makes it easier to read the entire selector.

    ```scss
    .btn-green {
      background: green;
      font-weight: bold;

      @include transition(background 0.5s ease);
      // ...
    }
    ```

3. Nested selectors

    Nested selectors, _if necessary_, go last, and nothing goes after them. Add whitespace between your rule declarations and nested selectors, as well as between adjacent nested selectors. Apply the same guidelines as above to your nested selectors. Extra rules for the same element go before nested selectors.

    ```scss
    .btn {
      background: green;
      font-weight: bold;

      @include transition(background 0.5s ease);

      &:after {
        content: '';
      }

      .icon {
        margin-right: 10px;
      }
    }
    ```

### Nested selectors

**Do not nest selectors more than three levels deep!**

```scss
.page-container {
  .content {
    .profile {
      // STOP!
    }
  }
}
```

## JavaScript
