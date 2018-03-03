### Setup of https://happyuc-explorer.007.li on Ubuntu 16.04

    apt update
    apt upgrade
    apt install git python-software-properties software-properties-common nginx
    curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
    npm install pm2 --global
    add-apt-repository ppa:certbot/certbot
    apt update
    apt upgrade
    apt install python-certbot-nginx
    
Copy content from [./happyuc-explorer.007.li.conf](./happyuc-explorer.007.li.conf) into `/etc/nginx/sites/happyuc-explorer.007.li.conf`

    certbot --nginx -d happyuc-explorer.007.li
    cd /etc/ssl/certs
    openssl dhparam -out dhparam.pem 4096
    cd /home/happyuc
    git clone https://github.com/dreamxyp/happyuc-explorer.git
    cd /home/happyuc/happyuc-explorer
    npm install
    pm2 start bin/www --name "happyuc-explorer"
