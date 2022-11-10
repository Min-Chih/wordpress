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









