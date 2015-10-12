# Frontend precommit rules for Javascript, SASS and ReactJS

### The main goal of this set of rules is to establish healthy boundaries where cleaner code will be easier to share, more scalable, more readable and easier to maintain for everyone.

----

In order to do so we decided to rely on [Eslint](http://eslint.org/), a great Javascript linter by [Nicholas C. Zakas](https://twitter.com/slicknet) and [SCSS-Lint](https://github.com/brigade/scss-lint) for... yes! SASS linting.

#### Index
* [SASS](sass-syntax)
    * [Naming Convention](#naming-convention)
    *

#### TL;DR
If you are wondering if this set of rules if for you here's a brief description. Keep reading to get a detailed description.

####**SASS Linting won't let you:**
- Leave empty declarations or duplicate properties.
- Add comments
- Add color values directly to a property. You must use **variables** instead.
- Set short #hex values.
- Use of `!important`
- Nest properties beyond 4 levels.
- Write a selector in a single line.
- ...

####**in SASS linting you must:
- Leave a space after colon.
- Leave an empty line between blocks.
- Merge rules of same selector.
- Set properties to `0` instead of `none`.
- Match the selector format to the [Naming Convention](#naming-convention)
- ...

----

# SASS Syntax
Here you'll find a use case example for every SASS linting rule specified in this set:

### BangFormat

Defines the right use of  *the bang* `!` in `!default`, `!global`,  and `!optional` flags.

**Bad**
```scss
$c-bg-light: #ffffff!default
```

**Good**
```scss
$c-bg-light: #ffffff !default
```

## BorderZero

Set properties to `border: 0` over `border: none`.

**Bad**
```scss
border: none;
```

**Good**
```scss
border: 0;
```

## ColorVariable

To avoid colour entropy all arround the site is mandatory to set colour using SASS variables as shown in the example below. Colour parametrization ensures better maintainability and are more verbose than setting an hex value as `#bada55`

**Bad: literal color**
```scss
.sui-Card-title {
  color: green;
}
```

**Good: refer to color by variable name**
```scss
$body-color: #c0ffee;

...

.sui-Card-title {
  color: $body-color;
}
```


## Naming Convention
Based in [SUIT CSS](https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md)

Example:
```
.pre-MyComponent {}
.pre-MyComponent.is-animating {}
.pre-MyComponent--modifier {}

.pre-MyComponent-element {}
.pre-MyComponent-anotherElement {}
```
