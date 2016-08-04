## Mixin libraries
* [Bourbon](http://bourbon.io)
* [Compass](http://compass-style.org)
* [Eyeglass](http://eyeglass.rocks)

---

### _mixins.scss
  
```css
// fonts
@mixin font-primary($weight: $font-wt-primary) {
    font-family: $font-fam-primary;
    font-weight: $weight;
}
@mixin font-highlight($weight: $font-wt-highlight) {
    font-family: $font-fam-highlight;
    font-weight: $weight;
}
@mixin font-family-weight($family: $font-fam-primary, $weight: $font-wt-highlight) {
    font-family: $family;
    font-weight: $weight;
}
@mixin font-size-line($size: 14px, $line: 16px) {
    font-size: $size;
    line-height: $line;
}


// text
@mixin text-truncate() {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}


// banner
@mixin banner-img($url, $pos: center center) {
    background-image: url($url);
    background-position: $pos;
    background-repeat: no-repeat;
    background-size: 100%;
    background-size: cover;
}



// misc
@mixin vert-parent {
    display: table;
}
@mixin vert-child {
    display: table-cell;
    vertical-align: middle;
}

@mixin clearfix {
    &:before,
    &:after {
        content: '';
        display: table;
    }
    &:after {
        clear: both;
    }
}
```
  

__button placeholder and mixin__
```css
%btn {
    color: #fff;
    font-size: 14px;
    text-align: center;
    padding: 10px 15px;
    border: none;
    shadow: none;
    display: block;
    curser: pointer;
}
@mixin btn-background($btn-background) {
    @extend %btn;
    background-color: $btn-background;
    &:hover {
        background-color: lighten($btn-background, 10%);
    }
}
.btn-primary {
    @include btn-background(blue);
}
```
