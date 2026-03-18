# noura-store

Simple static test website for `noura-store.com`.

## Stack

- Static HTML/CSS
- Nginx

## Deploy on Ubuntu

```bash
sudo apt-get update
sudo apt-get install -y nginx
sudo mkdir -p /var/www/noura-store
sudo cp index.html styles.css /var/www/noura-store/
sudo cp deploy/nginx.conf /etc/nginx/sites-available/noura-store.conf
sudo ln -sf /etc/nginx/sites-available/noura-store.conf /etc/nginx/sites-enabled/noura-store.conf
sudo rm -f /etc/nginx/sites-enabled/default
sudo nginx -t
sudo systemctl reload nginx
```

Point DNS for `noura-store.com` and `www.noura-store.com` to the container IP after provisioning.
