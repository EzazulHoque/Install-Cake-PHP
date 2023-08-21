# Install-Cake-PHP
Install CakePHP in WSL Ubuntu 

```markdown
# CakePHP Installation Guide 🍰

Follow the step-by-step guide below to install CakePHP on your machine:

## 1. Install Composer 🎼
sudo apt-get install composer
```

## 2. Install PHP 8.1 Extensions 🐘
Install the necessary extensions for PHP 8.1:
```bash
sudo apt-get install php8.1 libapache2-mod-php8.1 php8.1-common php8.1-gd php8.1-mysql php8.1-curl php8.1-intl php8.1-xsl php8.1-mbstring php8.1-zip php8.1-bcmath php8.1-soap php-xdebug php-imagick
```

For SQLite support:
```bash
sudo apt-get install php-sqlite3
```

## 3. Install Apache2 🌐
```bash
sudo apt-get install apache2
```

## 4. Start Apache Server 🚀
```bash
sudo service apache2 start
```
After this step, open your browser and navigate to `localhost`. You should see the default Apache2 HTML page.

## 5. Create CakePHP Project 🍰
Navigate to the appropriate directory and create your CakePHP project:
```bash
cd /var/www/
composer create-project --prefer-dist cakephp/app:~4.0 my_app_name
```
> Note: Replace `my_app_name` with your desired project folder name.

## 6. Configure Apache for CakePHP 🛠
Navigate to Apache's sites-available directory:
```bash
cd /etc/apache2/sites-available
```

Edit the default configuration:
```bash
sudo nano 000-default.conf
```

In the editor:

- Comment out the existing `DocumentRoot` line by adding a `#` at the beginning:
```plaintext
# DocumentRoot /var/www/
```

- Then, add your CakePHP project's Webroot path:
```plaintext
DocumentRoot /var/www/my_app_name/Webroot
```
> Note: Adjust the path `my_app_name` to match your project folder name.

Save the file:
- Press `Control + O`
- Hit `Enter`

## 7. Restart Apache Server 🔄
```bash
sudo service apache2 restart
```

---

Congratulations 🎉! Your CakePHP setup should now be complete. Enjoy building with CakePHP!
