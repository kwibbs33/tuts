### Links
* [Sass guide](http://sass-lang.com/guide)
* [style guide](https://css-tricks.com/sass-style-guide)
  
### Files
* [_variables.scss](variables.md)
* [_mixins.scss](mixins.md)
* [_helpers.scss](helpers.md)
* [_base.scss](base.md)

---

### Ordering
$variables, @extend placeholders, @include mixins, styles, pseudo-classes, nested selectors, media queries
```css
.element {
    $bg-color: #d90000;

    @extend %btn;

    @include btn-lg;

    color: #fff;
    font-size: 14px;

    &:hover {
        background-color: darken($bg-color, 20%);
    }

    > i {
        padding-left: 5px;
    }

    @media (max-width: 400px) {
        font-size: 10px;
    }
}
```

### app.scss
```css
// vendor dependencies
@import 'breakpoint';        // https://github.com/at-import/breakpoint/wiki
@import 'vendor/normalize';

// authored dependencies
@import 'variables';
@import 'mixins';            // placeholders, mixins, functions
@import 'helpers';
@import 'base';

// modules
@import 'global/buttons';

// sections
@import 'global/header';
@import 'global/footer';

@import 'shame';
```
