# Bài 3 — Nginx website tĩnh PTIT

## File nộp

- `index.html` — nội dung trang
- `ptit-web.conf` — Server Block cổng 80

## Lệnh trên Droplet (user devops + sudo)

```bash
sudo apt update
sudo apt install -y nginx

sudo mkdir -p /var/www/ptit-web/html
sudo nano /var/www/ptit-web/html/index.html
# dán nội dung index.html

sudo nano /etc/nginx/sites-available/ptit-web.conf
# dán nội dung ptit-web.conf

sudo ln -s /etc/nginx/sites-available/ptit-web.conf /etc/nginx/sites-enabled/
sudo rm -f /etc/nginx/sites-enabled/default

sudo nginx -t
sudo systemctl reload nginx
```

## Kiểm tra

- `sudo nginx -t` → syntax is ok
- Trình duyệt: `http://<IP_DROPLET>` → hiện *Welcome to PTIT DevOps Course - Session 02*
