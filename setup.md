sudo apt update

sudo apt install nginx -y


sudo systemctl start nginx
sudo systemctl enable nginx

sudo systemctl status nginx

sudo apt install php-fpm php-mysql php-cli php-curl php-gd php-mbstring php-xml php-zip php-bcmath php-json -y

php -v

sudo systemctl status php8.3-fpm


sudo systemctl start php8.3-fpm
sudo systemctl enable php8.3-fpm

sudo apt update
sudo apt install php8.3-pgsql

sudo apt install curl unzip -y
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer

composer --version


cd /var/www/html

sudo apt install git


sudo su -

ssh-keygen -t ed25519 -C "ahmedj@logicodetech.com"

ssh-keygen -t rsa -b 4096 -C "ahmedj@logicodetech.com"

eval "$(ssh-agent -s)"

ssh-add ~/.ssh/id_ed25519

cat ~/.ssh/id_ed25519.pub

add this key in github


ssh -T git@github.com

(If Successfull Run the clone command)

git clone -b basicSetup git@github.com:Logicode-Technologies/Inkit2.0BackEnd.git

sudo chown -R www-data:www-data /var/www/html/Inkit2.0BackEnd
sudo chmod -R 755 /var/www/html/Inkit2.0BackEnd
sudo chmod -R 775 /var/www/html/Inkit2.0BackEnd/storage
sudo chmod -R 775 /var/www/html/Inkit2.0BackEnd/bootstrap/cache

sudo nano /ETC/nginx/sites-available/Inkit2.0BackEnd

server {
    listen 80;
    server_name 56.228.28.96;
    root /var/www/html/Inkit2.0BackEnd/public;
    index index.php index.html index.htm;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php8.3-fpm.sock; # Adjust to your PHP version
        fastcgi_index index.php; #comment this if error occur
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~ /\.ht {
        deny all;
    }
}

sudo ln -s /etc/nginx/sites-available/Inkit2.0BackEnd /etc/nginx/sites-enabled/

sudo nginx -t

sudo systemctl reload nginx

sudo systemctl status php8.3-fpm
// If not running
sudo systemctl start php8.3-fpm
sudo systemctl enable php8.3-fpm

cp .env.example .env

 php artisan key:generate


postgres
    postgres
    dY#H9jp65-`a

DB Port
5432

