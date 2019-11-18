# Readme
README to install Ripple to Windows!

1. You must use Python 3.6 for your Windows (because I build DLLs with Python 3.6 not sure if others Python will work)
2. Download <a href="https://go.microsoft.com/fwlink/?LinkId=691126">Visual C++ Build Tools 2015</a> and MySQLClient that is Windows Binaries from <a href="https://www.lfd.uci.edu/~gohlke/pythonlibs/#mysqlclient">here</a>
3. After you installed Visual C++ Build Tools 2015, You will need to open "x86 x64 Cross Build Tools Command Prompt" from Start Menu (at this point, you can even build your own DLLs. But you will need to know how cython works in Windows)
4. Type `pip install mysqlclient‑1.4.5‑cp36‑cp36m‑win_amd64.whl`
5. Download <a href="https://github.com/tporadowski/redis/releases">Redis</a> and <a href="https://dev.mysql.com/get/Downloads/MySQLInstaller/mysql-installer-web-community-8.0.18.0.msi">MySQL server</a> (or you can get MariaDB server from <a href="https://www.apachefriends.org/index.html">XAMPP</a>)
6. Download <a href="https://www.heidisql.com/download.php?download=installer">HeidiSQL</a> (or other software that can see and edit data and structures)
7. Connect to your database and import this SQL query
