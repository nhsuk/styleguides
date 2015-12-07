## CSS Coding Style

## Contents

* [Whitespace](#whitespace)
* [Sass nesting](#sass-nesting)

## Whitespace

Use soft tabs with a two space indent.

**Why:** This follows the conventions used within our other projects.

## Sass nesting

* Where possible rather than repeating selectors nest blocks together

  ```scss
  // Bad
  .header h1 {
    font-weight: bold;
  }
  .header span {
    color: lightgray;
  }
  .header .date {
    color: blue;
  }

  // Good
  .header {
    h1 {
      font-weight: bold;
    }
    span {
      color: lightgray;
    }
    .date {
      color: blue;
    }
  }
  ```

  **Why:** by nesting selectors it is clearer for future developers to work out
  that rules all affect the same elements. It also stops people accidentally
  adding unrelated selectors between related rules.
