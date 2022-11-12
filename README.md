# Wordpress
A repository to record my journey of learning bulding a WordPress web.

# Setup
- Get a domain ✔️
- Get a server to host the web ✔️
- Use Cyberduck for FTP (File transfer protocol)➡️need to use cPanel login to connect to your domain ✔️

# Theme
- Activated your own theme by putting your web folder in public_html/theme folder in Cyberduck
- A wordpress theme needs: index.php and style.css
- CSS might not applied, needs to add a Bloginfo() Template Tags for the CSS link, as well as <img src>
``` template tag
<?php bloginfo('template_directory');?>
```
- Able to dynamic change the web title and description by replacing title to template tags like below:
``` template tag title
<?php bloginfo('name');?>
```
``` template tag tagline
<?php bloginfo('description');?>
```
# The Wordpress Loop
- created a header.php, a footer.php, and a sidebar.php files
- moved everything before main to header.php, things after main to footer.php, and things in the sidebar to sidebar.php file
- added below first to tags below on index.php file, and sidebar tag in footer.php file
```
<?php get_header(); ?> 
```
```
<?php get_footer(); ?> 
```
```
<?php get_sidebar(); ?> 
```
- through replacing title/content/author/time to template tags to make dynamic change on the wordpress theme
```
<?php the_title(); ?>
<?php the_content(); ?>
<?php the_excerpt(); ?>
<?php the_category(); ?>
<?php the_autho(' ')r; ?>
<?php the_time( 'l, F jS, Y' ); ?>
```
- Permalinks: you can add permalink tag to any href if you want to link it to some pages
```
<?php the_permalink(); ?>
```

# CSS for your WordPress

- Add the body_class(); on the open <body> tag. Like this:
```
<body <?php body_class(); ?>>
```
It generates lots of class helper classes for CSS styling later on. 
- Also add these tags in the opening "div" classes and IDs like below:
```
<div id="post-<?php the_ID(); ?>" <?php post_class(); ?>>
```
It changes the output of our "div" from the static to the dynamic IDs and classes. This means (get excited) that you can target each individual post now with CSS/JS.

# Template Hierarchy
- You can use different file name to overwrite specific page you want to customise
- For more info, visit [WordPress Single Post](https://developer.wordpress.org/themes/basics/template-hierarchy/#single-post)

# Comments
- you can added comment template for the post like below:
```
<?comments_template( '', true );;?>
```
# SideBar
- Create a function.php file
- added below code in the file
```
<?php register_sidebar(); ?>
```
- and now you can customise your sidebar on wordpress admin page
- you can add new widgets to your sidebar by adding the below code in your file
```
  /* add this in function.php */
  <?php $args = array(
	'name'          => __( 'Sidebar name', 'theme_text_domain' ),
	'id'            => 'unique-sidebar-id',
	'description'   => '',
        'class'         => '',
	'before_widget' => '<li id="%1$s" class="widget %2$s">',
	'after_widget'  => '</li>',
	'before_title'  => '<h2 class="widgettitle">',
	'after_title'   => '</h2>' ); ?>
```
```
/* add this in sidebar.php */
<?php if ( ! dynamic_sidebar('RenPower Sidebar') ) : ?>
<?php endif; ?>
```

# Navigation Menu
	
- you can add a nav menu for your web by registering your nav menu first in function.php
```
register_nav_menu('main', 'Main navigation menu');
```

- and replace the hardcode "ul and li tags" in header.php file to code below
```
<?php wp_nav_menu( $args );?>
```

# Advanced theming
- Edit this post tag
```
<?php edit_post_link(__('Edit This Post'));?>
```
- Allowed Plugins: added below codes to two files
``` 
/* add this to header.php */
<?php wp_head(); ?>
```
``` 
/* add this to footer.php */
<?php wp_footer(); ?>
```
- you can now install plugins through the admin page







