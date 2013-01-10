lnrl-vs-lamp
============

Linux-Nginx-Redis-Lua versus Linux-Apache-Mysql-Php


Draft
=====


source: http://owncloud.org/support/install/

To run ownCloud, your webserver must have the following installed:
php5 (>= 5.3), php5-json php-xml php-mbstring php5-zip php5-gdAnd as optional dependencies: php5-sqlite (>= 3), curl, libcurl3, libcurl3-dev, php5-curl, php-pdo

apt-get install apache2 php5 php5-json php-xml php-mbstring php5-zip php5-gd
apt-get install php5-sqlite curl libcurl3 libcurl3-dev php5-curl php-pdo

You don’t need any WebDAV support of your webserver (i.e. apache’s mod_webdav) to access your ownCloud data via WebDAV, ownCloud has a WebDAV server built in.



Essayons d'avoir l'equivalent avec du lua ...


| Original   | Targeted | URL | comment |
|:-----------|:---------|:----|:--------|
| apache2    | nginx    | ... | [url.openresty][] |
| (webdav)   | (webdav) | (nginx ./configure --with-http_dav_module) | |
| php5       | Lua      | LuaJIT | [url.luajit][] |
| php5-json  | cjson    | ... | |
| php-xml    | ?        | [url.luaxml][] | |
| php-mbstring | ?      | multibyte ... Unicode [ http://php.net/manual/fr/book.mbstring.php ]  [ http://ittner.github.com/lua-iconv/ ] | |
| php5-zip   | luazip   | [url.luazip][] | |
| php5-gd    | lua-gd   | ... | |
| And as optional dependencies: |
| php5-sqlite (>= 3) | ? | ... | |
| curl, libcurl3, libcurl3-dev | = idem | ... | |
| php5-curl | lua-curl  | http://msva.github.com/lua-curl/ (fork of LuaCURL) | fail to compile |
| php-pdo   | ?         | ... | |



http://php.net/manual/fr/book.mbstring.php

https://code.google.com/p/luaforwindows/

[url.luazip]: http://www.keplerproject.org/luazip/
[url.openresty]: http://openresty.org
[url.luajit]: http://luajit.org
[url.luaxml]: http://lua-users.org/wiki/LuaXml
[url.lua-iconv]: http://ittner.github.com/lua-iconv/  http://www.gnupg.org/download/iconv.en.html http://gnuwin32.sourceforge.net/packages/libiconv.htm
[url.lua-gd]: http://ittner.github.com/lua-gd/

