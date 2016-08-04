### _helpers.scss
  
```css
// vertical align middle
//    @extend %vert-parent;
%vert-parent {
    display: table;
}
%vert-child {
    display: table-cell;
    vertical-align: middle;
}


// clearfix
//    @extend %clearfix
%clearfix {
    &:before,
    &:after {
        content: '';
        display: table;
    }
    &:after {
        clear: both;
    }
}


// media queries
//    @include break(0, ($window-xs - 1)) {
@mixin break($args...) {
    @if length($args) == 1 {
        @media (min-width: nth($args, 1)) {
            @content;
        }
    }
    @if length($args) == 2 {
        @media (min-width: nth($args, 1)) and (max-width: nth($args, 2)) {
            @content;
        }
    }
}
//    @include respond-to('')
@include add-breakpoint('xs down', 0 ($bp-xs - 1));
@include add-breakpoint('sm down', 0 ($bp-sm - 1));
@include add-breakpoint('md down', 0 ($bp-md - 1));
@include add-breakpoint('lg down', 0 ($bp-lg - 1));
@include add-breakpoint('xs up', $bp-xs);
@include add-breakpoint('sm up', $bp-sm);
@include add-breakpoint('md up', $bp-md);
@include add-breakpoint('lg up', $bp-lg);
@include add-breakpoint('xs to sm', $bp-xs ($bp-sm - 1));
@include add-breakpoint('sm to md', $bp-sm ($bp-md - 1));
@include add-breakpoint('md to lg', $bp-md ($bp-lg - 1));
}
```
  
  
__output rem property with mixin fallback (IE8)__
  
@include rem-px(font-size, 1.8);
font-size: 18px;
font-size: 1.8em;
  
@include rem-px(padding, 1, 0, 5, 0);
font-size: 10px 0 50px 0;
font-size: 1rem 0 5rem 0;
```css
@mixin rem-px($property, $remValues...) {
    // create empty lists
    $pxs: ();
    $rems: ();

    // loop through remValues
    @each $value in $remValues {
        // append to existing list: append($list, $value, [auto/comma/space])
        $pxs: append($pxs, $value * 10 + 10px, space);
        $rems: append($rems, $value + rem, space);
    }

    #{$property}: $pxs;
    #{$property}: $rems;
}
```
