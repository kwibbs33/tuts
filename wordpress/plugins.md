## Tips
* Choosing a plugin:
    - updated recently
    - many downloads
    - read reviews for issues and conflicts
    - FAQ info

* Plugin doesn't work:
    1. uninstall and reinstall
    2. Check settings
    3. Check developer console for errors
    4. Pick another plugin

---

---

### Favicon
* __Favicon__ by RealFaviconGenerator
    * Appearance -> Favicon -> upload .png at 260x260

---

### Videos
* Youtube or other hosted source: 'Share' to get short url and copy/paste into page
    * to make it responsive:
        * Manual - [http://alxmedia.se/code/2013/10/make-wordpress-default-video-embeds-responsive/](http://alxmedia.se/code/2013/10/make-wordpress-default-video-embeds-responsive/)
        * Plugin -> __Advanced Responsive Video Embedder__

* Use your own video: must have .mp4, .ogv, .webm
    * Plugin -> __Video.js HTML5__

* You can use `[video]` tag in page, then save: a box will let you edit the options

---

### Slideshow
* tip: make sure it has touch/swipe support (for mobile)
* __Meta slider__

---

### Fonts
* __Easy Google Fonts__
    * Appearance -> Customize -> Typography

---

### Icons
* Favicons
    * functions.php:
    ```php
    function favicons_styles() {
        wp_enqueue_style( 'mycustom-fontawesome', 'https://maxcdn.bootstrapcdn.com/font-awesome/4.6.3/css/font-awesome.min.css' );
    }
    add_action( 'wp_enqueue_scripts', 'favicons_styles' );
    ```


* Wordpress dashicons
    * Icons: [http://developer.wordpress.org/resource/dashicons](http://developer.wordpress.org/resource/dashicons)

    * functions.php:
    ```php
    add_action( 'wp_enqueue_scripts', 'wp_dashicons' );
    function wp_dashicons() {
        wp_enqueue_scripts( 'font-style', get_stylesheet_uri(), array('dashicons' ), '1.0' );
    }
    ```

    * style.css:
    ```css
    .dashicons:before {
        display: inline-block;
        -webkit-font-smoothing: antialiased;
        font: normal 20px/1 'dashicons';
        vertical-align: top;
    }
    .dashicons-admin-users:before {
        content: "\f110";
    }
    ```

---

### Responsive Images
* __RespImage__ [http://s2webpress.com/responsive-featured-image-function-in-wordpress-themes/](http://s2webpress.com/responsive-featured-image-function-in-wordpress-themes/) - not on Wordpress plugins
    1. Download and move to plugins folder
    2. Plugins -> Add New -> Upload Plugin
    3. Settings -> RespImage
        - Yes - use full size image
        - No  -
        - Yes - asynchronis picturefill.js
    4. must make various sizes of the image:

        - make yourself and upload all sizes (or)

        - __Regenerate Thumbnails__ plugin
            - Media Library -> bulk actions -> Regenerate Thumbnails

            - Plugin -> Editor -> Responsive Featured Images:
            ```php
            change:
            add_action( 's2_res_featured_theme_support' );
            to:
            add_action( 's2_res_featured_img_theme_support' );
            ```

---

### Retina display
* [http://bjango.com/articles/min-device-pixel-ratio](http://bjango.com/articles/min-device-pixel-ratio)
* [http://www.iosres.com](http://www.iosres.com)
* [http://iosdesign.ivomynttinen.com](http://iosdesign.ivomynttinen.com)

* __Retina Images__ [http://retina-images/complexcompulsions.com](http://retina-images/complexcompulsions.com)
    * best but difficult to use

* __WP Retina 2x__
    1. 'View details' for installation
    2. Settings -> WP Retina 2x
        - BASIC disable sizes you don't need
        - BASIC Yes - Generate Retina images auto (will generate LOTS of images)
        - ADVANCED Method - Picturefill
    3. Media ->
    4. Pages -> Add Media to page

---

### SVG
* [http://css-tricks.com/using-svg](http://css-tricks.com/using-svg)

* if you need it to work in old IE: __SVG Modernizer__

* to use SVG if this is not already in the theme:
    1. functions.php:
    ```php
    function fix_svg_thumb_display() {
        echo '<style>td.media-icon img[src$=".svg"], img[src$=".svg"].attachment-post-thumbnail {width: 100% !important; height: auto !important; }</style>';
    }
    add_action('admin-head', 'fix_svg_thumb_display');

    function cc_mime_types($mimes) {
        if (current_user_can('administrator')) {
            $mimes['svg'] = 'image/svg+xml';
            return $mimes;
        } else {
            return $mimes;
        }
    }
    add_filter('upload_mimes', 'cc_mime_types');
    ```

    2. upload SVG into Media
    3. Add Media to page, then go to Text and delete size (will be set at height/width of 0)

---

### Forms
* __Contact Form 7__ emails data
    1. Contact -> Add New

---

### Others
* __Smooth Scroll Up__
    * to edit CSS:
        1. copy file to child folder
        2. functions.php:
        ```php
        // customize the styles of the 'smooth scroll up' widget
        function my_deregister_styles() {
            wp_deregister_style( 'scrollup-css' );
            wp_dequeue_style('scrollup-css');
        }
        add_action('wp_print_styles', 'my_deregister_styles', 9999); // 9999 : happen after everything

        function my_register_styles() {
            wp_enqueue_style('style', get_stylesheet_uri() );
            wp_enqueue_style('scrollup-custom', get_stylesheet_directory_uri() . '/scrollup-custom.css');
        }
        add_action('wp_print_styles', 'my_register_styles');
        // get_stylesheet_directory_uri() : child theme folder
        ```
