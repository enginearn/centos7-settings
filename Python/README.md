# Python Environment

``` bash
$ cat /etc/redhat-release 
CentOS Linux release 7.9.2009 (Core)
```

## Installing Python 3.11.2 on CentOS 7

``` bash
$ sudo yum -y install wget perl perl-Test-Simple perl-Test-Harness libffi-devel gcc zlib-devel bzip2 bzip2-devel readline readline-devel sqlite sqlite-devel tcl tcl-devel
$ sudo yum -y groupinstall "Development Tools"
```

``` bash
$ sudo yum list installed | grep openssl
$ sudo yum -y remove openssl.x86_64
$ sudo yum list installed | grep openssl
```

Installing openssl-1.1.1

[Python 3.10の新機能(その8） OpenSSL 1.1.1が必須に](https://www.python.jp/news/wnpython310/require-openssl11.html)

> これまで、Pythonでは OpenSSL のVersion 1.0.2以降が利用可能でしたが、
> Python 3.10からは、OpenSSL 1.1.1以降が必須となりました([PEP 644 Require OpenSSL 1.1.1 or newer](https://peps.python.org/pep-0644/))。


``` bash
$ wget --no-check-certificate https://www.openssl.org/source/openssl-1.1.1s.tar.gz
$ tar xzf openssl-1.1.1s.tar.gz
$ cd openssl-1.1.1s
$ ./config
$ make
$ make test
$ sudo make install
$ sudo ldconfig -p | grep libssl.so.1.1s
$ ldd /usr/local/bin/openssl
$ sudo sh -c 'echo /usr/local/lib64 > /etc/ld.so.conf.d/local.conf'
$ sudo ldconfig
$ sudo ldconfig -p | grep libssl.so.1.1s
$ /usr/local/bin/openssl version
$ sudo ln -s /usr/local/bin/openssl /usr/bin/openssl
$ openssl version
```

Installing Python 3.11.2

``` bash
$ wget https://www.python.org/ftp/python/3.11.2/Python-3.11.2.tgz
$ tar -xzf Python-3.11.2.tgz
$ cd Python-3.11.2
$ ./configure
$ make
$ make test
$ sudo make install
$ sudo ln -s /usr/local/bin/python3.11 /usr/bin/python3
$ sudo ln -s /usr/local/bin/pip3.11 /usr/bin/pip3
$ python3 --version
$ pip3 --version
```

Remove unnecessary folders

``` bash
$ cd ~
$ rm -rf Python-3.11.2.tgz
$ rm -rf Python-3.11.2
$ rm -rf openssl-1.1.1s.tar.gz
$ rm -rf openssl-1.1.1s
```

[CentOS7.9(2009)に対してPython3.11のインストール手順メモ](https://qiita.com/hikaru3n/items/85edefd790f7dbf238fe)

[CentOS 環境のPython](https://www.python.jp/install/centos/index.html)

## Installing pyenv

[pyenv](https://github.com/pyenv/pyenv)

``` bash
$ curl https://pyenv.run | bash
```

> WARNING: seems you still have not added 'pyenv' to the load path.
>
> Load pyenv automatically by appending
> the following to 
> ~/.bash_profile if it exists, otherwise ~/.profile (for login shells)
> and ~/.bashrc (for interactive shells) :
>
> export PYENV_ROOT="$HOME/.pyenv"
> command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"
> eval "$(pyenv init -)"
>
> Restart your shell for the changes to take effect.

``` bash
$ vim ~/.bash_profile
```

Adding below lines at the last line on `.bash_profile` or `.profile` and so on.

``` bash_profile
# pyenv settings
export PYENV_ROOT="$HOME/.pyenv"
command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
```

``` bash
$ source ~/.bash_profile
```

Check pyenv version

``` bash
$ pyenv --version
pyenv 2.3.15
```
