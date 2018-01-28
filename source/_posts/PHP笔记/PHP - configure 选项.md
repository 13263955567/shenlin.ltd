
```bash
[ssy@localhost php-7.1.5]$ \
./configure \
--prefix=/usr/local/php7.1.5/ 
--with-config-file-path=/usr/local/php7.1.5/etc/ 
--with-apxs2=/usr/local/httpd-2.4.25/bin/apxs 
--enable-mysqlnd 
--with-mysqli=mysqlnd 
--with-pdo-mysql=mysqlnd 
--enable-bcmath 
--enable-mbstring
```

PHP�ͷ������������ַ�����
1. ��Ϊģ�飺ͨ��PHP��ģ��ӿ�SAPI��Ϊweb��������ģ�飬֧�ֵķ������� apache
2. ��ִ�г�����ΪCGI��FastCGI������

**--enable-fpm**

���� FPM(FastCGI Process Manager) ֧��

����Ϊ FPM ����ľ������ò�����ȫ��Ϊ��ѡ��������

   --with-fpm-user - ���� FPM ���е��û���ݣ�Ĭ�� - nobody��

   --with-fpm-group - ���� FPM ����ʱ���û��飨Ĭ�� - nobody��

   --with-fpm-systemd - ���� systemd ���� (Ĭ�� - no)

   --with-fpm-acl - ʹ��POSIX ���ʿ����б� (Ĭ�� - no) 5.6.5�汾����Ч

��ϸ���ã�http://php.net/manual/zh/install.fpm.configuration.php


--with-apxs2= \

    --with-apxs2 �Ͳ������� libphp5.so

--with-mysql=/usr/bin/mysql_config  \


**--with-apxs2=FILE**
Build shared Apache 2.0 Handler module. FILE is the optional pathname to the Apache apxs tool apxs


**--enable-mysqlnd**
Enable mysqlnd explicitly, will be done implicitly when required by other extensions


**--with-mysqli=FILE**
Include MySQLi support.
FILE is the path to mysql_config.
If no value or mysqlnd is passed as FILE, the MySQL native driver will be used

    --with-mysqli=mysqlnd \
    --with-mysqli=/usr/local/mysql/bin/mysql_config \

**--with-pdo-mysql=DIR**
PDO: MySQL support. 
DIR is the MySQL base directory
If no value or mysqlnd is passed as DIR, the MySQL native driver will be used

    --with-pdo-mysql=mysqlnd \
    --with-pdo-mysql=/usr/local/mysql \



���֮ǰ���� `make` ʧ��,�ǵ��� `make clean` ���� `make distclean` ���֮ǰ����Ļ����ļ�,Ȼ�������� `make && make install`

