# Node.js

##

`nodesource / distributions` says below...

> ~~ CentOS 7 (64-bit) ~~ WARNING: BUILD SYSTEM CURRENTLY BROKEN FOR NODEJS 18+

``` bash
$ curl -fsSL https://rpm.nodesource.com/setup_18.x | sudo bash -
[sudo] centos7 のパスワード:

## Installing the NodeSource Node.js 18.x repo...


## Inspecting system...

+ rpm -q --whatprovides redhat-release || rpm -q --whatprovides centos-release || rpm -q --whatprovides cloudlinux-release || rpm -q --whatprovides sl-release || rpm -q --whatprovides fedora-release
+ uname -m

## Confirming "el7-x86_64" is supported...

+ curl -sLf -o /dev/null 'https://rpm.nodesource.com/pub_18.x/el/7/x86_64/nodesource-release-el7-1.noarch.rpm'

## Downloading release setup RPM...

+ mktemp
+ curl -sL -o '/tmp/tmp.mbLyahIpAj' 'https://rpm.nodesource.com/pub_18.x/el/7/x86_64/nodesource-release-el7-1.noarch.rpm'

## Installing release setup RPM...

+ rpm -i --nosignature --force '/tmp/tmp.mbLyahIpAj'

## Cleaning up...

+ rm -f '/tmp/tmp.mbLyahIpAj'

## Checking for existing installations...

+ rpm -qa 'node|npm' | grep -v nodesource

## Run `sudo yum install -y nodejs` to install Node.js 18.x and npm.
## You may run dnf if yum is not available:
     sudo dnf install -y nodejs
## You may also need development tools to build native addons:
     sudo yum install gcc-c++ make
## To install the Yarn package manager, run:
     curl -sL https://dl.yarnpkg.com/rpm/yarn.repo | sudo tee /etc/yum.repos.d/yarn.repo
     sudo yum install yarn

[centos7@centos7 ~]$ sudo yum install nodejs npm
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.iij.ad.jp
 * epel: ftp.iij.ad.jp
 * extras: ftp.iij.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.iij.ad.jp
nodesource                                               | 2.5 kB     00:00     
nodesource/x86_64/primary_db                               |  39 kB   00:00     
依存性の解決をしています
--> トランザクションの確認を実行しています。
---> パッケージ nodejs.x86_64 2:18.15.0-1nodesource を インストール
--> 依存性の処理をしています: libstdc++.so.6(GLIBCXX_3.4.21)(64bit) のパッケージ: 2:nodejs-18.15.0-1nodesource.x86_64
--> 依存性の処理をしています: libc.so.6(GLIBC_2.28)(64bit) のパッケージ: 2:nodejs-18.15.0-1nodesource.x86_64
--> 依存性の処理をしています: libm.so.6(GLIBC_2.27)(64bit) のパッケージ: 2:nodejs-18.15.0-1nodesource.x86_64
--> 依存性の処理をしています: libstdc++.so.6(CXXABI_1.3.9)(64bit) のパッケージ: 2:nodejs-18.15.0-1nodesource.x86_64
--> 依存性の処理をしています: libstdc++.so.6(GLIBCXX_3.4.20)(64bit) のパッケージ: 2:nodejs-18.15.0-1nodesource.x86_64
---> パッケージ npm.x86_64 1:8.19.2-1.16.18.1.3.el7 を インストール
--> 依存性の処理をしています: nodejs = 1:16.18.1-3.el7 のパッケージ: 1:npm-8.19.2-1.16.18.1.3.el7.x86_64
--> 依存性解決を終了しました。
エラー: パッケージ: 2:nodejs-18.15.0-1nodesource.x86_64 (nodesource)
             要求: libm.so.6(GLIBC_2.27)(64bit)
エラー: パッケージ: 2:nodejs-18.15.0-1nodesource.x86_64 (nodesource)
             要求: libstdc++.so.6(CXXABI_1.3.9)(64bit)
エラー: パッケージ: 2:nodejs-18.15.0-1nodesource.x86_64 (nodesource)
             要求: libc.so.6(GLIBC_2.28)(64bit)
エラー: パッケージ: 2:nodejs-18.15.0-1nodesource.x86_64 (nodesource)
             要求: libstdc++.so.6(GLIBCXX_3.4.21)(64bit)
エラー: パッケージ: 1:npm-8.19.2-1.16.18.1.3.el7.x86_64 (epel)
             要求: nodejs = 1:16.18.1-3.el7
            利用可能: 1:nodejs-16.18.1-3.el7.x86_64 (epel)
                nodejs = 1:16.18.1-3.el7
            利用可能: 2:nodejs-18.0.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.0.0-1nodesource
            利用可能: 2:nodejs-18.1.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.1.0-1nodesource
            利用可能: 2:nodejs-18.2.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.2.0-1nodesource
            利用可能: 2:nodejs-18.3.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.3.0-1nodesource
            利用可能: 2:nodejs-18.4.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.4.0-1nodesource
            利用可能: 2:nodejs-18.5.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.5.0-1nodesource
            利用可能: 2:nodejs-18.6.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.6.0-1nodesource
            利用可能: 2:nodejs-18.7.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.7.0-1nodesource
            利用可能: 2:nodejs-18.8.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.8.0-1nodesource
            利用可能: 2:nodejs-18.9.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.9.0-1nodesource
            利用可能: 2:nodejs-18.9.1-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.9.1-1nodesource
            利用可能: 2:nodejs-18.10.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.10.0-1nodesource
            利用可能: 2:nodejs-18.11.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.11.0-1nodesource
            利用可能: 2:nodejs-18.12.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.12.0-1nodesource
            利用可能: 2:nodejs-18.12.1-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.12.1-1nodesource
            利用可能: 2:nodejs-18.13.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.13.0-1nodesource
            利用可能: 2:nodejs-18.14.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.14.0-1nodesource
            利用可能: 2:nodejs-18.14.1-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.14.1-1nodesource
            利用可能: 2:nodejs-18.14.2-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.14.2-1nodesource
            インストール中: 2:nodejs-18.15.0-1nodesource.x86_64 (nodesource)
                nodejs = 2:18.15.0-1nodesource
エラー: パッケージ: 2:nodejs-18.15.0-1nodesource.x86_64 (nodesource)
             要求: libstdc++.so.6(GLIBCXX_3.4.20)(64bit)
 問題を回避するために --skip-broken を用いることができます。
 これらを試行できます: rpm -Va --nofiles --nodigest
```

``` bash
$ sudo yum install libstdc++.so.6
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.iij.ad.jp
 * epel: ftp.iij.ad.jp
 * extras: ftp.iij.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.iij.ad.jp
依存性の解決をしています
--> トランザクションの確認を実行しています。
---> パッケージ libstdc++.i686 0:4.8.5-44.el7 を インストール
--> 依存性の処理をしています: libm.so.6(GLIBC_2.0) のパッケージ: libstdc++-4.8.5-44.el7.i686
--> 依存性の処理をしています: libm.so.6 のパッケージ: libstdc++-4.8.5-44.el7.i686
--> 依存性の処理をしています: libgcc_s.so.1(GLIBC_2.0) のパッケージ: libstdc++-4.8.5-44.el7.i686
--> 依存性の処理をしています: libgcc_s.so.1(GCC_4.2.0) のパッケージ: libstdc++-4.8.5-44.el7.i686
--> 依存性の処理をしています: libgcc_s.so.1(GCC_3.3) のパッケージ: libstdc++-4.8.5-44.el7.i686
--> 依存性の処理をしています: libgcc_s.so.1(GCC_3.0) のパッケージ: libstdc++-4.8.5-44.el7.i686
--> 依存性の処理をしています: libgcc_s.so.1 のパッケージ: libstdc++-4.8.5-44.el7.i686
--> 依存性の処理をしています: libc.so.6(GLIBC_2.4) のパッケージ: libstdc++-4.8.5-44.el7.i686
--> 依存性の処理をしています: ld-linux.so.2(GLIBC_2.3) のパッケージ: libstdc++-4.8.5-44.el7.i686
--> 依存性の処理をしています: ld-linux.so.2 のパッケージ: libstdc++-4.8.5-44.el7.i686
--> トランザクションの確認を実行しています。
---> パッケージ glibc.i686 0:2.17-326.el7_9 を インストール
--> 依存性の処理をしています: libfreebl3.so(NSSRAWHASH_3.12.3) のパッケージ: glibc-2.17-326.el7_9.i686
--> 依存性の処理をしています: libfreebl3.so のパッケージ: glibc-2.17-326.el7_9.i686
---> パッケージ libgcc.i686 0:4.8.5-44.el7 を インストール
--> トランザクションの確認を実行しています。
---> パッケージ nss-softokn-freebl.i686 0:3.79.0-4.el7_9 を インストール
--> 依存性解決を終了しました。

依存性を解決しました

================================================================================
 Package                  アーキテクチャー
                                     バージョン             リポジトリー   容量
================================================================================
インストール中:
 libstdc++                i686       4.8.5-44.el7           base          319 k
依存性関連でのインストールをします:
 glibc                    i686       2.17-326.el7_9         updates       4.3 M
 libgcc                   i686       4.8.5-44.el7           base          111 k
 nss-softokn-freebl       i686       3.79.0-4.el7_9         updates       325 k

トランザクションの要約
================================================================================
インストール  1 パッケージ (+3 個の依存関係のパッケージ)

総ダウンロード容量: 5.0 M
インストール容量: 16 M
Is this ok [y/d/N]: y
Downloading packages:
(1/4): libgcc-4.8.5-44.el7.i686.rpm                        | 111 kB   00:01     
(2/4): nss-softokn-freebl-3.79.0-4.el7_9.i686.rpm          | 325 kB   00:01     
(3/4): libstdc++-4.8.5-44.el7.i686.rpm                     | 319 kB   00:01     
(4/4): glibc-2.17-326.el7_9.i686.rpm                       | 4.3 MB   00:03     
--------------------------------------------------------------------------------
合計                                               1.5 MB/s | 5.0 MB  00:03     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
警告: RPMDB は yum 以外で変更されました。
  インストール中          : libgcc-4.8.5-44.el7.i686                        1/4 
  インストール中          : glibc-2.17-326.el7_9.i686                       2/4 
  インストール中          : nss-softokn-freebl-3.79.0-4.el7_9.i686          3/4 
  インストール中          : libstdc++-4.8.5-44.el7.i686                     4/4 
  検証中                  : libstdc++-4.8.5-44.el7.i686                     1/4 
  検証中                  : nss-softokn-freebl-3.79.0-4.el7_9.i686          2/4 
  検証中                  : libgcc-4.8.5-44.el7.i686                        3/4 
  検証中                  : glibc-2.17-326.el7_9.i686                       4/4 

インストール:
  libstdc++.i686 0:4.8.5-44.el7                                                 

依存性関連をインストールしました:
  glibc.i686 0:2.17-326.el7_9                   libgcc.i686 0:4.8.5-44.el7     
  nss-softokn-freebl.i686 0:3.79.0-4.el7_9     

完了しました!
```

``` bahs
$ wget http://mirror.ghettoforge.org/distributions/gf/el/7/gf/x86_64/gcc10-libstdc++-10.2.1-7.gf.el7.x86_64.rpm
```

``` bash
$ sudo yum --nogpg install https://mirror.ghettoforge.org/distributions/gf/gf-release-latest.gf.el7.noarch.rpm
[sudo] centos7 のパスワード:
読み込んだプラグイン:fastestmirror, langpacks
gf-release-latest.gf.el7.noarch.rpm                      | 8.0 kB     00:00     
/var/tmp/yum-root-l1Eokw/gf-release-latest.gf.el7.noarch.rpm を調べています: gf-release-7-12.gf.el7.noarch
/var/tmp/yum-root-l1Eokw/gf-release-latest.gf.el7.noarch.rpm をインストール済みとして設定しています
依存性の解決をしています
--> トランザクションの確認を実行しています。
---> パッケージ gf-release.noarch 0:7-12.gf.el7 を インストール
--> 依存性解決を終了しました。

依存性を解決しました

================================================================================
 Package      アーキテクチャー
                       バージョン      リポジトリー                        容量
================================================================================
インストール中:
 gf-release   noarch   7-12.gf.el7     /gf-release-latest.gf.el7.noarch   4.5 k

トランザクションの要約
================================================================================
インストール  1 パッケージ

合計容量: 4.5 k
インストール容量: 4.5 k
Is this ok [y/d/N]: y
Downloading packages:
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  インストール中          : gf-release-7-12.gf.el7.noarch                   1/1 
  検証中                  : gf-release-7-12.gf.el7.noarch                   1/1 

インストール:
  gf-release.noarch 0:7-12.gf.el7                                               

完了しました!
```

[http://ghettoforge.org](http://ghettoforge.org/index.php/Usage)

``` bash
$ sudo yum --enablerepo=gf install gcc10-libstdc++
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.iij.ad.jp
 * epel: ftp.iij.ad.jp
 * extras: ftp.iij.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.iij.ad.jp
依存性の解決をしています
--> トランザクションの確認を実行しています。
---> パッケージ gcc10-libstdc++.x86_64 0:10.2.1-7.gf.el7 を インストール
--> 依存性解決を終了しました。

依存性を解決しました

================================================================================
 Package                アーキテクチャー
                                      バージョン                リポジトリー
                                                                           容量
================================================================================
インストール中:
 gcc10-libstdc++        x86_64        10.2.1-7.gf.el7           gf        3.8 M

トランザクションの要約
================================================================================
インストール  1 パッケージ

総ダウンロード容量: 3.8 M
インストール容量: 17 M
Is this ok [y/d/N]: y
Downloading packages:
警告: /var/cache/yum/x86_64/7/gf/packages/gcc10-libstdc++-10.2.1-7.gf.el7.x86_64.rpm: ヘッダー V4 RSA/SHA1 Signature、鍵 ID da8b7718: NOKEY
gcc10-libstdc++-10.2.1-7.gf.el7.x86_64.rpm の公開鍵がインストールされていません
gcc10-libstdc++-10.2.1-7.gf.el7.x86_64.rpm                 | 3.8 MB   00:04     
file:///etc/pki/rpm-gpg/RPM-GPG-KEY-gf.el7 から鍵を取得中です。
Importing GPG key 0xDA8B7718:
 Userid     : "Ghettoforge (el7) <gf@ghettoforge.org>"
 Fingerprint: b43e a892 86f4 b6fd ff83 fed1 d005 ae31 da8b 7718
 Package    : gf-release-7-12.gf.el7.noarch (@/gf-release-latest.gf.el7.noarch)
 From       : /etc/pki/rpm-gpg/RPM-GPG-KEY-gf.el7
上記の処理を行います。よろしいでしょうか？ [y/N]y
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  インストール中          : gcc10-libstdc++-10.2.1-7.gf.el7.x86_64          1/1 
  検証中                  : gcc10-libstdc++-10.2.1-7.gf.el7.x86_64          1/1 

インストール:
  gcc10-libstdc++.x86_64 0:10.2.1-7.gf.el7                                      

完了しました!$ sudo yum --enablerepo=gf install gcc10-libstdc++
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.iij.ad.jp
 * epel: ftp.iij.ad.jp
 * extras: ftp.iij.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.iij.ad.jp
依存性の解決をしています
--> トランザクションの確認を実行しています。
---> パッケージ gcc10-libstdc++.x86_64 0:10.2.1-7.gf.el7 を インストール
--> 依存性解決を終了しました。

依存性を解決しました

================================================================================
 Package                アーキテクチャー
                                      バージョン                リポジトリー
                                                                           容量
================================================================================
インストール中:
 gcc10-libstdc++        x86_64        10.2.1-7.gf.el7           gf        3.8 M

トランザクションの要約
================================================================================
インストール  1 パッケージ

総ダウンロード容量: 3.8 M
インストール容量: 17 M
Is this ok [y/d/N]: y
Downloading packages:
警告: /var/cache/yum/x86_64/7/gf/packages/gcc10-libstdc++-10.2.1-7.gf.el7.x86_64.rpm: ヘッダー V4 RSA/SHA1 Signature、鍵 ID da8b7718: NOKEY
gcc10-libstdc++-10.2.1-7.gf.el7.x86_64.rpm の公開鍵がインストールされていません
gcc10-libstdc++-10.2.1-7.gf.el7.x86_64.rpm                 | 3.8 MB   00:04     
file:///etc/pki/rpm-gpg/RPM-GPG-KEY-gf.el7 から鍵を取得中です。
Importing GPG key 0xDA8B7718:
 Userid     : "Ghettoforge (el7) <gf@ghettoforge.org>"
 Fingerprint: b43e a892 86f4 b6fd ff83 fed1 d005 ae31 da8b 7718
 Package    : gf-release-7-12.gf.el7.noarch (@/gf-release-latest.gf.el7.noarch)
 From       : /etc/pki/rpm-gpg/RPM-GPG-KEY-gf.el7
上記の処理を行います。よろしいでしょうか？ [y/N]y
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  インストール中          : gcc10-libstdc++-10.2.1-7.gf.el7.x86_64          1/1 
  検証中                  : gcc10-libstdc++-10.2.1-7.gf.el7.x86_64          1/1 

インストール:
  gcc10-libstdc++.x86_64 0:10.2.1-7.gf.el7                                      

完了しました!
```

nodejs 18をインストールするのはライブラリが対応していないようなのであきらめる。

## Install node16

``` bash
$ sudo yum --enablerepo=nodesource install nodejs@17 npm
[sudo] centos7 のパスワード:
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.iij.ad.jp
 * epel: ftp.iij.ad.jp
 * extras: ftp.iij.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.iij.ad.jp
パッケージ nodejs@17 は利用できません。
依存性の解決をしています
--> トランザクションの確認を実行しています。
---> パッケージ npm.x86_64 1:8.19.2-1.16.18.1.3.el7 を インストール
--> 依存性の処理をしています: nodejs = 1:16.18.1-3.el7 のパッケージ: 1:npm-8.19.2-1.16.18.1.3.el7.x86_64
--> トランザクションの確認を実行しています。
---> パッケージ nodejs.x86_64 1:16.18.1-3.el7 を インストール
--> 依存性の処理をしています: nodejs-libs(x86-64) = 1:16.18.1-3.el7 のパッケージ: 1:nodejs-16.18.1-3.el7.x86_64
--> 依存性の処理をしています: libuv >= 1:1.43.0 のパッケージ: 1:nodejs-16.18.1-3.el7.x86_64
--> 依存性の処理をしています: openssl11 >= 1:1.1.1 のパッケージ: 1:nodejs-16.18.1-3.el7.x86_64
--> 依存性の処理をしています: libbrotlidec.so.1()(64bit) のパッケージ: 1:nodejs-16.18.1-3.el7.x86_64
--> 依存性の処理をしています: libbrotlienc.so.1()(64bit) のパッケージ: 1:nodejs-16.18.1-3.el7.x86_64
--> 依存性の処理をしています: libcrypto.so.1.1()(64bit) のパッケージ: 1:nodejs-16.18.1-3.el7.x86_64
--> 依存性の処理をしています: libnode.so.93()(64bit) のパッケージ: 1:nodejs-16.18.1-3.el7.x86_64
--> 依存性の処理をしています: libssl.so.1.1()(64bit) のパッケージ: 1:nodejs-16.18.1-3.el7.x86_64
--> 依存性の処理をしています: libuv.so.1()(64bit) のパッケージ: 1:nodejs-16.18.1-3.el7.x86_64
--> トランザクションの確認を実行しています。
---> パッケージ libbrotli.x86_64 0:1.0.9-10.el7 を インストール
---> パッケージ libuv.x86_64 1:1.44.2-1.el7 を インストール
---> パッケージ nodejs-libs.x86_64 1:16.18.1-3.el7 を インストール
---> パッケージ openssl11.x86_64 1:1.1.1k-5.el7 を インストール
---> パッケージ openssl11-libs.x86_64 1:1.1.1k-5.el7 を インストール
--> 依存性解決を終了しました。

依存性を解決しました

=========================================================================================================
 Package                   アーキテクチャー  バージョン                            リポジトリー     容量
=========================================================================================================
インストール中:
 npm                       x86_64            1:8.19.2-1.16.18.1.3.el7              epel            2.2 M
依存性関連でのインストールをします:
 libbrotli                 x86_64            1.0.9-10.el7                          epel            308 k
 libuv                     x86_64            1:1.44.2-1.el7                        epel            145 k
 nodejs                    x86_64            1:16.18.1-3.el7                       epel             96 k
 nodejs-libs               x86_64            1:16.18.1-3.el7                       epel             13 M
 openssl11                 x86_64            1:1.1.1k-5.el7                        epel            693 k
 openssl11-libs            x86_64            1:1.1.1k-5.el7                        epel            1.5 M

トランザクションの要約
=========================================================================================================
インストール  1 パッケージ (+6 個の依存関係のパッケージ)

総ダウンロード容量: 18 M
インストール容量: 64 M
Is this ok [y/d/N]: y
Downloading packages:
(1/7): libuv-1.44.2-1.el7.x86_64.rpm                                              | 145 kB  00:00:00     
(2/7): openssl11-1.1.1k-5.el7.x86_64.rpm                                          | 693 kB  00:00:00     
(3/7): libbrotli-1.0.9-10.el7.x86_64.rpm                                          | 308 kB  00:00:00     
(4/7): openssl11-libs-1.1.1k-5.el7.x86_64.rpm                                     | 1.5 MB  00:00:00     
npm-8.19.2-1.16.18.1.3.el7.x86 FAILED                                          
https://mirror.01link.hk/epel/7/x86_64/Packages/n/npm-8.19.2-1.16.18.1.3.el7.x86_64.rpm: [Errno 14] curl#60 - "Peer's Certificate has expired."
他のミラーを試します。
It was impossible to connect to the CentOS servers.
This could mean a connectivity issue in your environment, such as the requirement to configure a proxy,
or a transparent proxy that tampers with TLS security, or an incorrect system clock.
You can try to solve this issue by using the instructions on https://wiki.centos.org/yum-errors
If above article doesn't help to resolve this issue please use https://bugs.centos.org/.

(5/7): nodejs-16.18.1-3.el7.x86_64.rpm                                            |  96 kB  00:00:01     
(6/7): npm-8.19.2-1.16.18.1.3.el7.x86_64.rpm                                      | 2.2 MB  00:00:00     
(7/7): nodejs-libs-16.18.1-3.el7.x86_64.rpm                                       |  13 MB  00:00:04     
---------------------------------------------------------------------------------------------------------
合計                                                                     3.9 MB/s |  18 MB  00:00:04     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  インストール中          : 1:openssl11-libs-1.1.1k-5.el7.x86_64                                     1/7 
  インストール中          : libbrotli-1.0.9-10.el7.x86_64                                            2/7 
  インストール中          : 1:libuv-1.44.2-1.el7.x86_64                                              3/7 
  インストール中          : 1:nodejs-libs-16.18.1-3.el7.x86_64                                       4/7 
  インストール中          : 1:openssl11-1.1.1k-5.el7.x86_64                                          5/7 
  インストール中          : 1:nodejs-16.18.1-3.el7.x86_64                                            6/7 
  インストール中          : 1:npm-8.19.2-1.16.18.1.3.el7.x86_64                                      7/7 
  検証中                  : 1:openssl11-1.1.1k-5.el7.x86_64                                          1/7 
  検証中                  : 1:npm-8.19.2-1.16.18.1.3.el7.x86_64                                      2/7 
  検証中                  : 1:libuv-1.44.2-1.el7.x86_64                                              3/7 
  検証中                  : 1:nodejs-16.18.1-3.el7.x86_64                                            4/7 
  検証中                  : 1:openssl11-libs-1.1.1k-5.el7.x86_64                                     5/7 
  検証中                  : 1:nodejs-libs-16.18.1-3.el7.x86_64                                       6/7 
  検証中                  : libbrotli-1.0.9-10.el7.x86_64                                            7/7 

インストール:
  npm.x86_64 1:8.19.2-1.16.18.1.3.el7                                                                    

依存性関連をインストールしました:
  libbrotli.x86_64 0:1.0.9-10.el7                  libuv.x86_64 1:1.44.2-1.el7                          
  nodejs.x86_64 1:16.18.1-3.el7                    nodejs-libs.x86_64 1:16.18.1-3.el7                   
  openssl11.x86_64 1:1.1.1k-5.el7                  openssl11-libs.x86_64 1:1.1.1k-5.el7                 

完了しました!
```

``` bash
$ node -v
node: relocation error: /lib64/libnode.so.93: symbol FIPS_selftest, version OPENSSL_1_1_0g not defined in file libcrypto.so.1.1 with link time reference
```

``` bash
$ yum list | grep openssl11
openssl11.x86_64                         1:1.1.1k-5.el7                @epel    
openssl11-libs.x86_64                    1:1.1.1k-5.el7                @epel    
openssl11-devel.x86_64                   1:1.1.1k-5.el7                epel     
openssl11-static.x86_64                  1:1.1.1k-5.el7                epel
```

``` bash
$ sudo yum install openssl11.x86_64
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.iij.ad.jp
 * epel: ftp.iij.ad.jp
 * extras: ftp.iij.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.iij.ad.jp
パッケージ 1:openssl11-1.1.1k-5.el7.x86_64 はインストール済みか最新バージョンです
何もしません$ sudo yum install openssl11.x86_64
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.iij.ad.jp
 * epel: ftp.iij.ad.jp
 * extras: ftp.iij.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.iij.ad.jp
パッケージ 1:openssl11-1.1.1k-5.el7.x86_64 はインストール済みか最新バージョンです
何もしません
```

``` bash
$ ln -s libcrypto.so.1.1 libcrypto.so
$ ln -s libssl.so.1.1 libssl.so
$ sudo ldconfig
```

``` bash
$ unlink libssl.so 
$ unlink libcrypto.so.1.1
$ unlink libcrypto.so
```

``` bash
$ sudo find libcrypto.so.1.1 / | grep libcrypto.so.1.1
[sudo] centos7 のパスワード:
find: ‘libcrypto.so.1.1’: そのようなファイルやディレクトリはありません
find: ‘/run/user/1000/doc’: 許可がありません
find: ‘/run/user/1000/gvfs’: 許可がありません
/usr/lib64/.libcrypto.so.1.1.1k.hmac
/usr/lib64/.libcrypto.so.1.1.hmac
/usr/lib64/libcrypto.so.1.1
/usr/lib64/libcrypto.so.1.1.1k
/usr/local/lib64/libcrypto.so.1.1
```

``` bash
$ ls -al /usr/lib64/libcrypto.so.1.1
lrwxrwxrwx. 1 root root 19  3月 21 11:10 /usr/lib64/libcrypto.so.1.1 -> libcrypto.so.1.1.1k
```

``` bash
$ ls -al /usr/lib64/libssl.so.1.1
lrwxrwxrwx. 1 root root 16  3月 21 11:10 /usr/lib64/libssl.so.1.1 -> libssl.so.1.1.1k
```

```bash
$ wget  https://download-ib01.fedoraproject.org/pub/epel/7/x86_64/Packages/o/openssl11-libs-1.1.1k-5.el7.x86_64.rpm
```

``` bash
$ ls
Desktop      Documents  Music     Public     Videos
Development  Downloads  Pictures  Templates  openssl11-libs-1.1.1k-5.el7.x86_64.rpm
```

``` bash
$ sudo yum localinstall openssl11-libs-1.1.1k-5.el7.x86_64.rpm 
読み込んだプラグイン:fastestmirror, langpacks
openssl11-libs-1.1.1k-5.el7.x86_64.rpm を調べています: 1:openssl11-libs-1.1.1k-5.el7.x86_64
openssl11-libs-1.1.1k-5.el7.x86_64.rpm: インストールされたパッケージを更新しません。
何もしません
```

``` bash
$ sudo yum install openssl11-libs
読み込んだプラグイン:fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: ftp.iij.ad.jp
 * epel: ftp.iij.ad.jp
 * extras: ftp.iij.ad.jp
 * remi-safe: ftp.riken.jp
 * updates: ftp.iij.ad.jp
パッケージ 1:openssl11-libs-1.1.1k-5.el7.x86_64 はインストール済みか最新バージョンです
何もしません
```

## Refs

[nodesource / distributions](https://github.com/nodesource/distributions)

[CentOSにNode.jsをインストール | キャンパーSEの備忘録](https://shoboon.net/?p=749)

[GitHub - nodesource/distributions: NodeSource Node.js Binary Distributions](https://github.com/nodesource/distributions#rpm)

[CentOS7でnコマンドを使用して nodejs のバージョンを簡単に切り替えられるようにした | うら紙のメモ](http://memo755.blog.fc2.com/blog-entry-188.html?sp)

[【CentOS】PhoenixMiner実行時にlibstdc関連のエラーが出る | ちりつもぶろぐ](https://chiritsumo-blog.com/centos-phoenix-miner-libstdc/)

[Index of /software/gcc/releases/](http://ftp.tsukuba.wide.ad.jp/software/gcc/releases/)

[kernelとgccのアップデート　CentOS7](https://node4u.info/2022/07/03/kernel%e3%81%a8gcc%e3%81%ae%e3%82%a2%e3%83%83%e3%83%97%e3%83%87%e3%83%bc%e3%83%88%e3%80%80centos7/)

[yum groupinstall "Development tools" で入るパッケージ一覧（CentOS） - Qiita](https://qiita.com/old_/items/6f9da09b9af795c11b71)

[gcc10-libstdc++-10.2.1-7.gf.el7.x86_64.rpm CentOS 7, RHEL 7, Rocky Linux 7, AlmaLinux 7 Download](https://rhel.pkgs.org/7/ghettoforge-x86_64/gcc10-libstdc++-10.2.1-7.gf.el7.x86_64.rpm.html)

[ロックファイル /var/run/yum.pidが存在します: PID 11412として別に実行されています。 | urashita.com 浦下.com (ウラシタドットコム)](https://urashita.com/archives/1353)

[Index of /distributions/gf/el/7/gf/x86_64](http://mirror.ghettoforge.org/distributions/gf/el/7/gf/x86_64/)

[gf-release-7-12.gf.el7.noarch.rpm CentOS 7, RHEL 7, Rocky Linux 7, AlmaLinux 7 Download](https://rhel.pkgs.org/7/ghettoforge-x86_64/gf-release-7-12.gf.el7.noarch.rpm.html)

[Usage - Ghettoforge](http://ghettoforge.org/index.php/Usage)

[パッケージ依存関係を解消する(rpm) - Qiita](https://qiita.com/happykikaku/items/2395c13b00a334e909ce)

[Libc.so.6(glibc_2.28)(64bit) Download (RPM)](https://pkgs.org/download/libc.so.6(GLIBC_2.28)(64bit))

[nodeのv18を使ったらエラーになった（CentOS7） - ITのプロへ](https://it.ama2pro.net/2022/05/31/node%E3%81%AEv18%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%82%89%E3%82%A8%E3%83%A9%E3%83%BC%E3%81%AB%E3%81%AA%E3%81%A3%E3%81%9F%EF%BC%88centos7%EF%BC%89/)

[Node.js v12 -> v16にyumでアップデートしてみた。(CentOS 7) - Qiita](https://qiita.com/daichi_pd/items/b3d8d968f36e6197bec4)

[GitHub - nodesource/distributions: NodeSource Node.js Binary Distributions](https://github.com/nodesource/distributions)

[javascript - node: relocation error: node: symbol SSL_set_cert_cb, version libssl.so.10 not defined in file libssl.so.10 with link time reference - Stack Overflow](https://stackoverflow.com/questions/46473376/node-relocation-error-node-symbol-ssl-set-cert-cb-version-libssl-so-10-not-d)

[CentOS7.9にMySQL8を入れる - Qiita](https://qiita.com/gunkan8mmt/items/d9b90c2114e738b31474)

[Openssl11-libs Download (RPM)](https://pkgs.org/download/openssl11-libs)

[openssl - error while loading shared libraries: libcrypto.so.1.1 - Server Fault](https://serverfault.com/questions/818445/error-while-loading-shared-libraries-libcrypto-so-1-1)

[Linux | シンボリックリンクの作成, 確認, 削除 - わくわくBank](https://www.wakuwakubank.com/posts/342-linux-ln-unlink/)

[CentOS7.9安装Nodejs爬坑 - Liao's blog](https://www.laobaiblog.top/2022/07/19/centos7-9%E5%AE%89%E8%A3%85nodejs%E7%88%AC%E5%9D%91/)

[Previous Releases | Node.js](https://nodejs.org/en/download/releases)

[Index of /download/release/v16.19.1/](https://nodejs.org/download/release/v16.19.1/)

[[Solved] relocation error: /lib64/libc.so.6: symbol _dl_starting_up 解決法 - Qiita](https://qiita.com/sachiotomita/items/ef29520c55fc168191d8)

[翻訳 - Google 検索](https://www.google.com/search?client=firefox-b-e&q=%E7%BF%BB%E8%A8%B3)

[Linux | 共有ライブラリの確認(ldd)と設定(ldconfig) - わくわくBank](https://www.wakuwakubank.com/posts/395-linux-ldd-ldconfig/)

[grepコマンドの詳細まとめました【Linuxコマンド集】](https://eng-entrance.com/linux-command-grep)

[docs.oracle.com/cd/E19253-01/816-3946/filesearch-4/index.html](https://docs.oracle.com/cd/E19253-01/816-3946/filesearch-4/index.html)

[openssl11-libs-1.1.1k-5.el7.x86_64.rpm CentOS 7, RHEL 7, Rocky Linux 7, AlmaLinux 7 Download](https://rhel.pkgs.org/7/epel-x86_64/openssl11-libs-1.1.1k-5.el7.x86_64.rpm.html)

[openssl11-libs-1.1.1k-5.el7.x86_64.rpm CentOS 7, RHEL 7, Rocky Linux 7, AlmaLinux 7 Download](https://rhel.pkgs.org/7/epel-x86_64/openssl11-libs-1.1.1k-5.el7.x86_64.rpm.html)

[CentOS7.9にMySQL8を入れる - Qiita](https://qiita.com/gunkan8mmt/items/d9b90c2114e738b31474)

[yum install と localinstallの違い - Qiita](https://qiita.com/mashiro_lain/items/c37ab3e33e244784bd2f)
