# Readme
README to install Ripple to Windows!

# Basic way to run LETS and pep.py
So, as you know... You will need Python PIP module to make LETS and pep.py working, follow the step below to get it working!

1. You must use Python 3.6 for your Windows (because I build DLLs with Python 3.6 not sure if others Python will work)
2. Download <a href="https://go.microsoft.com/fwlink/?LinkId=691126">Visual C++ Build Tools 2015</a> and MySQLClient that is Windows Binaries from <a href="https://www.lfd.uci.edu/~gohlke/pythonlibs/#mysqlclient">here</a>
3. After you installed Visual C++ Build Tools 2015, You will need to open "x86 x64 Cross Build Tools Command Prompt" from Start Menu (at this point, you can even build your own DLLs. But you will need to know how cython works in Windows)
4. Type `pip install mysqlclient‑1.4.5‑cp36‑cp36m‑win_amd64.whl`
5. Download <a href="https://github.com/tporadowski/redis/releases">Redis</a> and <a href="https://dev.mysql.com/get/Downloads/MySQLInstaller/mysql-installer-web-community-8.0.18.0.msi">MySQL server</a> (or you can get MariaDB server from <a href="https://www.apachefriends.org/index.html">XAMPP</a>)
6. Download <a href="https://www.heidisql.com/download.php?download=installer">HeidiSQL</a> (or other software that can see and edit data and structures)
7. Connect to your database and import <a href="https://raw.githubusercontent.com/osuthailand/ripple-auto-installer/master/ripple_database.sql">this</a> SQL query
8. Run MySQL server and Redis
9. Run pep.py and LETS to make default configuration
10. Enjoy the bancho and LETS!

# Configuring Nginx 
We still need to make the proxy_pass with NGINX so you can run the fully functional Ripple! Follow the step below to get it working!

1. Get <a href="http://nginx.org/en/download.html">nginx Windows</a>
2. Extract nginx at your Ripple folder (or somewhere it suits you)
3. Download the <a href="https://github.com/Kanaze-chan/nginx-conf">NGINX configs</a> and edit "conf/nginx.conf", "osu/nginx.conf" and "osu/old-frontend.conf" (Read README.md first)
4. Start nginx and edit the hosts

# Host File
Add these to your host file, Hamachi IP is also working with this too!
```
#<domain that support in certificate> default is i-need-to.click

<127.0.0.1 or your Public IP> osu.ppy.sh
<127.0.0.1 or your Public IP> c.ppy.sh
<127.0.0.1 or your Public IP> c1.ppy.sh
<127.0.0.1 or your Public IP> c2.ppy.sh
<127.0.0.1 or your Public IP> c3.ppy.sh
<127.0.0.1 or your Public IP> c4.ppy.sh
<127.0.0.1 or your Public IP> c5.ppy.sh
<127.0.0.1 or your Public IP> c6.ppy.sh
<127.0.0.1 or your Public IP> c7.ppy.sh
<127.0.0.1 or your Public IP> ce.ppy.sh
<127.0.0.1 or your Public IP> a.ppy.sh
<127.0.0.1 or your Public IP> i.ppy.sh
<127.0.0.1 or your Public IP> <domain that support in certificate>
<127.0.0.1 or your Public IP> c.<domain that support in certificate>
<127.0.0.1 or your Public IP> i.<domain that support in certificate>
<127.0.0.1 or your Public IP> a.<domain that support in certificate>
<127.0.0.1 or your Public IP> old.<domain that support in certificate>
```

These domain are supported by osu!thailand certificate (You can make your by doing a new self-signed certificate)
- tatoe.pw
- i-need-to.click
- keidas.pw
- cookiezi.pw
- kawata.pw

# What password? My MD5 password is not working!
Alright... so right now Ripple is using Password -> MD5 -> BCrypt Hash (10 rounds) for the password to login so in `users` table in `password_md5` column will be like this

1. If I want to make my password `HelloRipple123`, first I need to hash it as MD5. So the hash will be `6d246d0f30cdc5b829c8e21c290f8ea9` (You can hash your password at http://www.md5.cz/)
2. Then after I hash it, I still need to make it as BCrypt Hash (10 Rounds) so I will use <a href="https://bcrypt-generator.com/">this website</a> as BCrypt encryptor.
3. Put the MD5 Hash to `String to encrypt` box, change rounds to 10 and then click `Hash!` button
4. You'll get the hash like `$2y$10$4mO9E2m7b6B0Z039ikDvSOXk2KBg9uAobGixVDv6NihQ4RL/itplq` as the hash (which is our MD5 hash. HelloRipple123)
5. Put your BCrypt hash in `password_md5` in your user data and profit!

Note: The BCrypt hash will be always different because BCrypt hash it 10 times!

# My PP is not calculating!
Replace the `E:/GitHub/LETS-windows/pp` to your directory such as `C:/lets/pp` in following files:
- pp/rippoppai.py
- pp/relaxoppai.py

## Help!
You can add me on Discord: `@Aoba Suzukaze#0900`
