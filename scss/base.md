### _base.scss
  
includes fixed nav
```css

/* ==========================================================================
   ALL
   ========================================================================== */

html {
    font-size: $font-size-root;
    // Changes the default tap highlight to be completely transparent in iOS.
    -webkit-tap-highlight-color: rgba(0,0,0,0);
}

body {
    font-family: $font-fam-primary;
    font-size: $font-size-base;
    line-height: $line-height;
    color: $body-color;
    background-color: $body-bg;
    letter-spacing: $kerning-sm;

    @include respond-to('sm down') {
        font-size: $font-size-sm;
    }
}

:focus {
    outline-style: none;
    box-shadow: none;
    border-color: transparent;
}

/* nav bar
   ========================================================================== */
.navbar-default,
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
    border: none;
}
.navbar-default .navbar-nav>.active>a,
.navbar-default .navbar-nav>.active>a:focus,
.navbar-default .navbar-nav>.active>a:hover {
    color: darken($blue-dk, 50%);
}

.navbar-nav > li > a {
    @include font-highlight;
}

.navbar-brand {
    padding: $nav-brand-pad 15px;
    overflow: hidden;

    img {
        height: $nav - ($nav-brand-pad * 2);

        body#home & {
            margin-top: $nav;
        }
    }
}


/* ==========================================================================
   banner / main
   ========================================================================== */

.banner {
    position: fixed;
    top: 0;
    width: 100%;
    @include banner-img("../img/", center top);

    @include respond-to('sm down') {
        background-image: url("../img/");
    }
}
.banner,
.page-header {
    margin-top: $nav;
}
main {
    margin-top: 0;
    display: block;
    position: relative;
    width: 100%;
    z-index: $z-main;
}


@include respond-to('xs down') {
    .banner,
    .page-header {
        height: $banner-xs;
        position: relative;
        text-align: center;
    }
}
@include respond-to('xs to sm') {
    .banner,
    .page-header {
        height: $banner-sm;
    }
}
@include respond-to('sm to md') {
    .banner,
    .page-header {
        height: $banner-md;
    }
}
@include respond-to('md up') {
    .banner,
    .page-header {
        height: $banner-lg;
    }
}

/* form */
#formnope {
    display: none;
}
label {
    color: #fff;
    font-weight: 300;
    margin-bottom: 1px;
}
label.error {
    display: none !important;
}

$formBorder: $blue-md;
.form-control {
    border: 2px solid lighten($formBorder, 15%);
    height: 39px;
    padding: 10px 12px;
    margin-bottom: 20px;
    resize: none;

    &:focus {
        border-color: $formBorder;
    }
}
.form-control.error {
    border-color: #dd0000 !important;
}

.form-success {
    color: #222;
    font-size: 1.2rem;
    font-weight: 600;
    text-align: center;
    padding: 10px 0;
    margin-bottom: 15px;
}


/* ==========================================================================
   footer
   ========================================================================== */
footer {
    @include bg-white;
    color: #888;
    @include font-highlight;
    font-size: 0.8rem;
    padding: 30px 0;
}

```
