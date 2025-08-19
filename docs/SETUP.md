# SETUP — Concise Walkthrough (Optional)

This repo focuses on results, not a long tutorial. Still, here's a compact path you can follow for reproducibility.

## 1) Environment
- VirtualBox installed
- Two VMs: **Ubuntu Server** (DVWA) and **Kali Linux**
- Networking: **Bridged Adapter** for both VMs

## 2) Ubuntu: LAMP + DVWA (very brief)
```bash
sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install -y apache2 php php-mysql mysql-server git net-tools openssl
cd /var/www/html && sudo git clone https://github.com/digininja/DVWA.git
sudo chown -R www-data:www-data DVWA && sudo chmod -R 755 DVWA
sudo mysql -u root -p <<'SQL'
CREATE DATABASE dvwa;
CREATE USER 'dvwa_user'@'localhost' IDENTIFIED BY 'p@ssw0rd';
GRANT ALL ON dvwa.* TO 'dvwa_user'@'localhost';
FLUSH PRIVILEGES;
SQL
# Move DVWA to port 8080
sudo sed -i 's/^Listen 80/Listen 8080/' /etc/apache2/ports.conf
sudo sed -i 's/<VirtualHost \*:80>/<VirtualHost *:8080>/' /etc/apache2/sites-available/000-default.conf
sudo systemctl restart apache2
```
Now browse `http://<ubuntu-ip>:8080/DVWA` and complete DVWA setup.

## 3) SSL (self-signed) for WAF
```bash
sudo mkdir -p /etc/ssl/dvwa
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048  -keyout /etc/ssl/dvwa/dvwa.key  -out /etc/ssl/dvwa/dvwa.crt
```

## 4) SafeLine WAF (auto deploy)
- Install via provided manager script
- Login to the WAF UI (default on `:9443`), import the cert/key above.
- Onboard the DVWA backend: `http://<ubuntu-ip>:8080`

## 5) Tests from Kali
- Open DVWA and set security level to **Low**
- Try SQLi payloads (e.g., `admin' OR '1'='1`) and confirm WAF blocks
- Check WAF logs and create a **custom deny rule** for Kali IP
- Optionally enable **HTTP flood defense** and observe behavior

> For a deeper, step-by-step guide, see **docs/Safeline_WAF_Guide.pdf**.
