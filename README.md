## Projeto da Aula

# Banco de dados

http://cl.ly/2e473b2M2k1Z

# Material da Disciplina

http://cl.ly/1n3E0K291I3h

# Apache

Exemplo de configuração do Apache

```
<VirtualHost *:80>
   DocumentRoot "/var/www/html/pos-webdev/public"
   ServerName api.pos-webdev.dev
   <Directory "/var/www/html/pos-webdev/public">
        Options Indexes MultiViews FollowSymLinks SymLinksIfOwnerMatch
        Order allow,deny
        Allow from all
        Header set Access-Control-Allow-Origin: "*"
        Header set Access-Control-Allow-Methods: "GET, POST, PUT, DELETE, OPTIONS"
        Header set Access-Control-Allow-Headers: "Accept, Authorization-Coderockr, Content-Type"

        RewriteEngine On
        RewriteRule .? - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
        RewriteCond %{REQUEST_FILENAME} -s [OR]
        RewriteCond %{REQUEST_FILENAME} -l [OR]
        RewriteCond %{REQUEST_FILENAME} -d
        RewriteRule ^.*$ - [NC,L]
        RewriteRule $ index.php
   </Directory>
</VirtualHost>

```
