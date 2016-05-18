# CSS Coding Style

## Contents

* [Naming](#naming)
* [Code style](#code-style)

## Naming

We use the [BEM methodology](https://en.bem.info/methodology/key-concepts/).

Our version of BEM follows this syntax:

* .block {}
* .block__element {}
* .block--modifier {}

For example:

```
<div class="card">
  <h1 class="card__title">Card</h1>
  <img class="card__image card__image--large" />
  <p class="card__description">Lorem ipsum dolor...</p>
</div>
```

**Why:** Naming things is hard but worth taking the time to think about and get
right. To make this simpler we use BEM for naming CSS classes. BEM also allows
us to clearly see intent and relationships within the markup and to scale and
maintain our codebase moving forward.

**Note:** This version differs slightly from traditional BEM and is loosely
based around a version described in a [blog post](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
by Harry Roberts at CSS Wizardry.

### State

We use a `is-` prefix to show state:

```
<ul class="nav">
  <li class="nav__item is-selected">Nav item one</li>
  <li class="nav__item">Nav item two</li>
</ul>
```

### Utilities

We use a `u-` prefix for utility classes.

**Why:** It allows us to see that these classes are more reusable and not tied
to a specific block.

### Javascript hooks

We use a `js-` to show an element that is being interacted with by Javascript:

```
<div class="tab js-tab">This element can be reached by Javascript</div>
```

**Why:** This maintains a distinction between presentation classes and
functionality. These should never be styled.

## Code style

### Whitespace

Use soft tabs with a 2 space indent.

**Why:** This follows the conventions used within our other projects.

### Extend

Only use the `@extend` directive to extend [placeholders](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#placeholder_selectors_),
not other selectors.

**Why:** Placeholders are ignored in CSS output when extended, classes are not.
Extending only from placeholders prevents bloated output.

### Sass nesting

Where possible limit nesting to 1 level deep.

**Why:** Multiple levels of nesting make code harder to read. With BEM you don't
need to nest as much. If you're more than 3 levels deep then you selector is
either too reliant on HTML structure, overly specific, or not very reusable.
