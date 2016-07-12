### Links
* [https://codex.wordpress.org/Child_Themes](https://codex.wordpress.org/Child_Themes)
* [http://stevenslack.com/choosing-wordpress-themes](http://stevenslack.com/choosing-wordpress-themes/)

---

### Plugins
* __Child Theme Configurator__

---

### Steps to customize
1. Plugins -> Child Theme Configurator
2. Tools -> Child Themes -> create a new theme based on current theme
3. Appearance -> activate child theme
4. Appearance -> Editor -> functions.php
	- the child .css should load after parent .css, if not:
	```php
	// BEGIN ENQUEUE PARENT ACTION

	function my_theme_enqueue_styles() {

	    $parent_style = 'parent-style';

	    wp_enqueue_style( $parent_style, get_template_directory_uri() . '/style.css' );
	    wp_enqueue_style( 'child-style',
	        get_stylesheet_directory_uri() . '/style.css',
	        array( $parent_style )
	    );
	}
	add_action( 'wp_enqueue_scripts', 'my_theme_enqueue_styles' );

	// END ENQUEUE PARENT ACTION
	```
5. Appearance -> Editor -> style.css

---

### Customization
* Appearance -> Menus
	1. Register in functions.php
	```
	register_nav_menus(
		array(
			'events-nav' => __( 'Events Menu', 'My Primary' ),
		)
	);
	```
	2. Insert into template/header/footer
		```php
		<nav role="navigation">
			<?php wp_nav_menu( array (
				'container' => '',
				'container_class' => '',
				'menu' => __( 'Events Menu', 'My Primary' ),
				'menu_class' => 'nav secondary-navigation',
				'theme_location' => 'events-nav',
				'before' => '',
				'after' => '',
				'link_before' => '',
				'link_after' => '',
				'depth' => 0
			)); ?>
		</nav>
		```

	3. copy footer.php and header.php from parent into child (will override parent)

