# PHP Environment

``` bash
$ sudo yum install -y https://rpms.remirepo.net/enterprise/remi-release-7.rpm
```

``` bash
$ sudo yum -y install --enablerepo=remi,remi-php82 php php-fpm php-devel php-cli php-common php-mbstring php-mysqlnd php-pear php-tcpdf php-mcryptphp-process php-pdo php-bcmath php-xml php-gd php-recode php-pecl-msgpack php-pecl-memcached
```

``` bash
$ php -v
PHP 8.2.4 (cli) (built: Mar 14 2023 16:11:05) (NTS gcc x86_64)
Copyright (c) The PHP Group
Zend Engine v4.2.4, Copyright (c) Zend Technologies
```

``` bash
$ sudo systemctl start php-fpm.service
$ sudo systemctl enable php-fpm.service
Created symlink from /etc/systemd/system/multi-user.target.wants/php-fpm.service to /usr/lib/systemd/system/php-fpm.service.
```

``` bash
$ sudo vim /etc/php.ini
display_errors = On
```

## Web Server settings

### Apache2

``` bash
$ yum info httpd
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.tsukuba.wide.ad.jp
 * epel: ftp.riken.jp
 * extras: ftp.tsukuba.wide.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.tsukuba.wide.ad.jp
インストール済みパッケージ
名前                : httpd
アーキテクチャー    : x86_64
バージョン          : 2.4.6
リリース            : 98.el7.centos.6
容量                : 9.4 M
リポジトリー        : installed
提供元リポジトリー  : updates
要約                : Apache HTTP Server
URL                 : http://httpd.apache.org/
ライセンス          : ASL 2.0
説明                : The Apache HTTP Server is a powerful, efficient, and extensible
                    : web server.
```

``` bash
$ sudo yum install httpd
[sudo] centos7 のパスワード:
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.iij.ad.jp
 * epel: ftp.iij.ad.jp
 * extras: ftp.iij.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.iij.ad.jp
パッケージ httpd-2.4.6-98.el7.centos.6.x86_64 はインストール済みか最新バージョンです
何もしません
```

``` bash
$ httpd -v
Server version: Apache/2.4.6 (CentOS)
Server built:   Jan 27 2023 17:36:29
```

``` bash
$ systemctl status httpd
● httpd.service - The Apache HTTP Server
   Loaded: loaded (/usr/lib/systemd/system/httpd.service; disabled; vendor preset: disabled)
   Active: inactive (dead)
     Docs: man:httpd(8)
           man:apachectl(8)
```

``` bash
$ systemctl enable httpd.service
Created symlink from /etc/systemd/system/multi-user.target.wants/httpd.service to /usr/lib/systemd/system/httpd.service.
```

``` bash
$ systemctl start httpd
$ systemctl status httpd
● httpd.service - The Apache HTTP Server
   Loaded: loaded (/usr/lib/systemd/system/httpd.service; enabled; vendor preset: disabled)
   Active: active (running) since 月 2023-03-20 00:40:25 JST; 5s ago
     Docs: man:httpd(8)
           man:apachectl(8)
 Main PID: 26340 (httpd)
   Status: "Processing requests..."
    Tasks: 6
   CGroup: /system.slice/httpd.service
           ├─26340 /usr/sbin/httpd -DFOREGROUND
           ├─26346 /usr/sbin/httpd -DFOREGROUND
           ├─26347 /usr/sbin/httpd -DFOREGROUND
           ├─26348 /usr/sbin/httpd -DFOREGROUND
           ├─26349 /usr/sbin/httpd -DFOREGROUND
           └─26350 /usr/sbin/httpd -DFOREGROUND

 3月 20 00:40:24 centos7 systemd[1]: Starting The Apache HTTP Server...
 3月 20 00:40:25 centos7 httpd[26340]: AH00558: httpd: Could not reliably determine the server's fully qualified domain name, using 192.168.1.203. Set the 'ServerName' directive globa...s this message
 3月 20 00:40:25 centos7 systemd[1]: Started The Apache HTTP Server.
Hint: Some lines were ellipsized, use -l to show in full.
```

Access to localhost

### nginx

``` bash
$ sudo vim /etc/yum.repos.d/nginx.repo

[nginx-stable]
name=nginx stable repo
baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
gpgcheck=1
enabled=1
gpgkey=https://nginx.org/keys/nginx_signing.key
module_hotfixes=true

[nginx-mainline]
name=nginx mainline repo
baseurl=http://nginx.org/packages/mainline/centos/$releasever/$basearch/
gpgcheck=1
enabled=0
gpgkey=https://nginx.org/keys/nginx_signing.key
module_hotfixes=true
```

``` bash
$ yum info nginx
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.tsukuba.wide.ad.jp
 * epel: ftp.riken.jp
 * extras: ftp.tsukuba.wide.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.tsukuba.wide.ad.jp
nginx-stable                                                                                                                                                                      | 2.9 kB  00:00:00     
nginx-stable/7/x86_64/primary_db                                                                                                                                                  |  81 kB  00:00:01     
利用可能なパッケージ
名前                : nginx
アーキテクチャー    : x86_64
エポック            : 1
バージョン          : 1.22.1
リリース            : 1.el7.ngx
容量                : 797 k
リポジトリー        : nginx-stable/7/x86_64
要約                : High performance web server
URL                 : https://nginx.org/
ライセンス          : 2-clause BSD-like license
説明                : nginx [engine x] is an HTTP and reverse proxy server, as well as
                    : a mail proxy server.
```

``` bash
$ sudo yum install nginx
[sudo] centos7 のパスワード:
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.iij.ad.jp
 * epel: ftp.iij.ad.jp
 * extras: ftp.iij.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.iij.ad.jp
nginx-stable                                                                                                                                                                      | 2.9 kB  00:00:00     
nginx-stable/7/x86_64/primary_db                                                                                                                                                  |  81 kB  00:00:01     
依存性の解決をしています
--> トランザクションの確認を実行しています。
---> パッケージ nginx.x86_64 1:1.22.1-1.el7.ngx を インストール
--> 依存性の処理をしています: openssl >= 1.0.2 のパッケージ: 1:nginx-1.22.1-1.el7.ngx.x86_64
--> トランザクションの確認を実行しています。
---> パッケージ openssl.x86_64 1:1.0.2k-25.el7_9 を インストール
--> 依存性解決を終了しました。

依存性を解決しました

=========================================================================================================================================================================================================
 Package                                     アーキテクチャー                           バージョン                                                リポジトリー                                      容量
=========================================================================================================================================================================================================
インストール中:
 nginx                                       x86_64                                     1:1.22.1-1.el7.ngx                                        nginx-stable                                     797 k
依存性関連でのインストールをします:
 openssl                                     x86_64                                     1:1.0.2k-25.el7_9                                         updates                                          494 k

トランザクションの要約
=========================================================================================================================================================================================================
インストール  1 パッケージ (+1 個の依存関係のパッケージ)

総ダウンロード容量: 1.3 M
インストール容量: 3.6 M
Is this ok [y/d/N]: y
Downloading packages:
(1/2): openssl-1.0.2k-25.el7_9.x86_64.rpm                                                                                                                                         | 494 kB  00:00:00     
warning: /var/cache/yum/x86_64/7/nginx-stable/packages/nginx-1.22.1-1.el7.ngx.x86_64.rpm: Header V4 RSA/SHA256 Signature, key ID 7bd9bf62: NOKEY====================-  ] 139 kB/s | 1.2 MB  00:00:00 ETA 
nginx-1.22.1-1.el7.ngx.x86_64.rpm の公開鍵がインストールされていません
(2/2): nginx-1.22.1-1.el7.ngx.x86_64.rpm                                                                                                                                          | 797 kB  00:00:03     
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
合計                                                                                                                                                                     324 kB/s | 1.3 MB  00:00:03     
https://nginx.org/keys/nginx_signing.key から鍵を取得中です。
Importing GPG key 0x7BD9BF62:
 Userid     : "nginx signing key <signing-key@nginx.com>"
 Fingerprint: 573b fd6b 3d8f bc64 1079 a6ab abf5 bd82 7bd9 bf62
 From       : https://nginx.org/keys/nginx_signing.key
上記の処理を行います。よろしいでしょうか？ [y/N]y
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  インストール中          : 1:openssl-1.0.2k-25.el7_9.x86_64                                                                                                                                         1/2 
  インストール中          : 1:nginx-1.22.1-1.el7.ngx.x86_64                                                                                                                                          2/2 
----------------------------------------------------------------------

Thanks for using nginx!

Please find the official documentation for nginx here:
* https://nginx.org/en/docs/

Please subscribe to nginx-announce mailing list to get
the most important news about nginx:
* https://nginx.org/en/support.html

Commercial subscriptions for nginx are available on:
* https://nginx.com/products/

----------------------------------------------------------------------
  検証中                  : 1:nginx-1.22.1-1.el7.ngx.x86_64                                                                                                                                          1/2 
  検証中                  : 1:openssl-1.0.2k-25.el7_9.x86_64                                                                                                                                         2/2 

インストール:
  nginx.x86_64 1:1.22.1-1.el7.ngx                                                                                                                                                                        

依存性関連をインストールしました:
  openssl.x86_64 1:1.0.2k-25.el7_9                                                                                                                                                                       

完了しました!
```

``` bash
$ sudo systemctl enable nginx
[sudo] centos7 のパスワード:
Created symlink from /etc/systemd/system/multi-user.target.wants/nginx.service to /usr/lib/systemd/system/nginx.service.
```

``` bash
$ sudo systemctl enable nginx
$ sudo vim /etc/nginx/nginx.conf

user  nginx;
worker_processes  auto;

error_log  /var/log/nginx/error.log notice;
pid        /var/run/nginx.pid;


events {
    worker_connections  1024;
}


http {
    include       /etc/nginx/mime.types;
    default_type  application/octet-stream;

    log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for"';

    access_log  /var/log/nginx/access.log  main;

    sendfile        on;
    #tcp_nopush     on;

    keepalive_timeout  65;

    #gzip  on;

    #include /etc/nginx/conf.d/*.conf;
    
    ##### Added
    server {
        listen       49152;
        listen       [::]:49152;
        server_name  _;
        root         /usr/share/nginx/html;

        # Load configuration files for the default server block.
        include /etc/nginx/default.d/*.conf;

        error_page 404 /404.html;
        location = /404.html {
        }

        error_page 500 502 503 504 /50x.html;
        location = /50x.html {
        }
    }
    #### Added
}
~          
```

``` bash
$ sudo systemctl start nginx
```

Access to localhost:49152

## Refs

[CentOS7にPHP8.0をyumインストールする方法](https://php-junkie.net/env/php8/)

[CentOS7 に PHP8.x をインストールする](http://psychedelicnekopunch.com/archives/2763)

[Apache httpd 2.4 を CentOS 7 に yum でインストールする手順](https://weblabo.oscasierra.net/apache-installing-apache24-yum-centos7-1/)

[Nginx を CentOS 7 にインストールする手順](https://weblabo.oscasierra.net/nginx-centos7-install/)

[【Nginx】待ち受けポート番号を変更する方法 【Nginx】待ち受けポート番号を変更する方法 ](https://syutaku.blog/nginx-1-20-port-change/)