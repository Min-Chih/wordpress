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
- Able to dynamic change the web title and description by adding template tags for title
``` template tag title
<?php bloginfo('name');?>
```
``` template tag tagline
<?php bloginfo('description');?>
```
