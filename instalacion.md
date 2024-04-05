Sube la que esta en la carpeta pterodactyl en la carpeta /var/www/pterodactyl de su vps

Abre /var/www/pterodactyl/resources/views/templates/wrapper.blade.php

Busca

<link rel="apple-touch-icon" sizes="180x180" href="/favicons/apple-touch-icon.png">
<link rel="icon" type="image/png" href="/favicons/favicon-32x32.png" sizes="32x32">
<link rel="icon" type="image/png" href="/favicons/favicon-16x16.png" sizes="16x16">
<link rel="manifest" href="/favicons/manifest.json">
<link rel="mask-icon" href="/favicons/safari-pinned-tab.svg" color="#bc6e3c">
<link rel="shortcut icon" href="/favicons/favicon.ico">

Remplazalo por

<link rel="manifest" href="/favicons/manifest.json">
<link rel="icon" type="image/png" id="hedystiaimage" href="#">
<link rel="mask-icon" href="/favicons/safari-pinned-tab.svg" color="#bc6e3c">

Busca

</head>

Pon abajo

<script type="text/javascript">
        fetch('/hedystia/icon.json')
        .then(response => response.json())
        .then(data => {
                document.getElementById('hedystiaimage').href=data.icon;
        });
    </script>

Guarda y cierra el archivo

Abre /var/www/pterodactyl/resources/views/layouts/admin.blade.php

Busca

<link rel="apple-touch-icon" sizes="180x180" href="/favicons/apple-touch-icon.png">
<link rel="icon" type="image/png" href="/favicons/favicon-32x32.png" sizes="32x32">
<link rel="icon" type="image/png" href="/favicons/favicon-16x16.png" sizes="16x16">
<link rel="manifest" href="/favicons/manifest.json">
<link rel="mask-icon" href="/favicons/safari-pinned-tab.svg" color="#bc6e3c">
<link rel="shortcut icon" href="/favicons/favicon.ico">

Remplazalo por

<link rel="manifest" href="/favicons/manifest.json">
<link rel="mask-icon" href="/favicons/safari-pinned-tab.svg" color="#bc6e3c">
<link rel="icon" type="image/png" id="hedystiaimage" href="#">

Busca

</head>

Pon abajo

<script type="text/javascript">
        fetch('/hedystia/icon.json')
        .then(response => response.json())
        .then(data => {
                document.getElementById('hedystiaimage').href=data.icon;
        });
    </script>

Guarda y cierra el archivo

Como poner el icono personalizado

Abre /var/www/pterodactyl/public/hedystia/icon.json

Busca
"icon": "https://cdn.discordapp.com/attachments/851919671878746112/955534101627162624/pterodactylicon.png"

Reemplaza el link por la imagen que gusta como icono del panel

https://cdn.discordapp.com/attachments/851919671878746112/955534101627162624/pterodactylicon.png

Guarda y cierra el archivo

Comando de la terminal (SÓLO PROBADOS EN UBUNTU, PUEDE QUE NO FUNCIONEN EN OTRO SISTEMA OPERATIVO):

cd /var/www/pterodactyl
chown -R www-data:www-data /var/www/pterodactyl/
chmod -R 755 storage/* bootstrap/cache/
php artisan optimize:clear

Una vez puesto si no te carga debes usar control + f5 de 3 a 4 veces para recargar el cache de la pagina y ya te cargue correctamente.

Si tienes alguna duda, puedes contactar conmigo en el siguiente servidor de discord:

https://discord.gg/aXvuUpvRQs
