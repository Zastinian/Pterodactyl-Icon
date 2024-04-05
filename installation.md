Upload the one in the pterodactyl folder in the /var/www/pterodactyl folder of your vps

Open /var/www/pterodactyl/resources/views/templates/wrapper.blade.php

Search

<link rel="apple-touch-icon" sizes="180x180" href="/favicons/apple-touch-icon.png">
<link rel="icon" type="image/png" href="/favicons/favicon-32x32.png" sizes="32x32">
<link rel="icon" type="image/png" href="/favicons/favicon-16x16.png" sizes="16x16">
<link rel="manifest" href="/favicons/manifest.json">
<link rel="mask-icon" href="/favicons/safari-pinned-tab.svg" color="#bc6e3c">
<link rel="shortcut icon" href="/favicons/favicon.ico">

Replace it with

<link rel="manifest" href="/favicons/manifest.json">
<link rel="icon" type="image/png" id="hedystiaimage" href="#">
<link rel="mask-icon" href="/favicons/safari-pinned-tab.svg" color="#bc6e3c">

Search

</head>

Put down

<script type="text/javascript">
        fetch('/hedystia/icon.json')
        .then(response => response.json())
        .then(data => {
                document.getElementById('hedystiaimage').href=data.icon;
        });
    </script>

Save and close the file

Open /var/www/pterodactyl/resources/views/layouts/admin.blade.php

Search

<link rel="apple-touch-icon" sizes="180x180" href="/favicons/apple-touch-icon.png">
<link rel="icon" type="image/png" href="/favicons/favicon-32x32.png" sizes="32x32">
<link rel="icon" type="image/png" href="/favicons/favicon-16x16.png" sizes="16x16">
<link rel="manifest" href="/favicons/manifest.json">
<link rel="mask-icon" href="/favicons/safari-pinned-tab.svg" color="#bc6e3c">
<link rel="shortcut icon" href="/favicons/favicon.ico">

Replace it with

<link rel="manifest" href="/favicons/manifest.json">
<link rel="mask-icon" href="/favicons/safari-pinned-tab.svg" color="#bc6e3c">
<link rel="icon" type="image/png" id="hedystiaimage" href="#">

Search

</head>

Put down

<script type="text/javascript">
        fetch('/hedystia/icon.json')
        .then(response => response.json())
        .then(data => {
                document.getElementById('hedystiaimage').href=data.icon;
        });
    </script>

Save and close the file

How to put the custom icon

Open /var/www/pterodactyl/public/hedystia/icon.json

Search
"icon": "https://cdn.onlinewebfonts.com/svg/img_337531.png"

Replace the link with the image you like as the panel icon

https://cdn.onlinewebfonts.com/svg/img_337531.png

Save and close the file

Terminal command (ONLY TESTED ON UBUNTU, MAY NOT WORK ON OTHER OPERATING SYSTEMS):

cd /var/www/pterodactyl
chown -R www-data:www-data /var/www/pterodactyl/
chmod -R 755 storage/* bootstrap/cache/
php artisan optimize:clear

Once set, if it does not load, use control + f5 3 or 4 times to reload the page cache and load correctly.

If you have any questions, you can contact me at the following discord server:

https://discord.gg/aXvuUpvRQs
