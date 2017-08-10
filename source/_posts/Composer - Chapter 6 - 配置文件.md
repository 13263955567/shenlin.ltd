title: Composer - Chapter 6 - �����ļ�
categories:
  - PHP
  - Composer
tags:
  - PHP
  - Composer

---

## Ŀ¼�ṹ

ȫ�������ļ�
config.json

�ֲ������ļ�
composer.json

�����������֤�ļ�
auth.json

composer.lock
/vendor

## ����������

### require ����

�� composer.json �ļ���ָ�� require key ��ֵ������ Composer ��Ŀ��Ҫ������Щ����

    {
        "require": {
            "monolog/monolog": "1.0.*"
        }
    }

### require-dev ���Ժ� --no-dev ѡ��

һЩ����������Ҫ�õ��İ����������������������貿��������԰�����Щ���������� `composer.json` �ļ��������� `require-dev` ָ����

```
"require-dev": {
    "fzaninotto/faker": "~1.4",
    "mockery/mockery": "0.9.*",
    "phpunit/phpunit": "~5.7"
}
```

�ڲ�������������ʱ�����`--no-dev`ָ����������Щ�������ɡ�
```
$ composer install --no-dev
```

## ��װ������

### ���� composer.json ��װ������

```
composer install
```

��Ҫ��ǰĿ¼����һ�� composer.json

install �������һ�� composer.lock �ļ�������Ŀ�ĸ�Ŀ¼��

�������ѵ������Ĵ��뵽ָ����Ŀ¼ vendor������� monolog ���ᴴ�� vendor/monolog/monolog Ŀ¼��

Git �������Ŀ��Ҫ��� vendor �� .gitignore �ļ��С� �������е���������붼����ӵ��汾���С�

### ֱ�������а�װ������

```
$ composer require mustache/mustache
```

composer���Զ����� composer.json �� composer.lock �ļ������Ӱ�װ�������������Ϣ

## �Զ����ذ�װ�Ŀ�

Composer ��׼����һ���Զ������ļ��������Լ��� Composer ���صĿ������е����ļ���ʹ��������ֻ��Ҫ���������д�����ӵ�����Ŀ�������ļ��У�

```
require 'vendor/autoload.php';
```

## composer.json �� composer.lock

### ��װ������ʱ

composerִ��installʱ�������ȼ��composer.lock���ļ��Ƿ���ڣ�
��������ڣ�Composer ����ȡ composer.json ���������ļ�����������װ���ȷ�а汾��д�� composer.lock �ļ���
������ڣ�Composer ������composer.json�ļ�����ʹ�� composer.lock �ж����ȷ�а汾���������⡣
����ζ�� composer.lock �ļ���������Ŀ��������ض��汾��

�����������ۣ�Ӧ�ð�composer.lock�ύ���汾�⣬
���Ա�֤�Ŷӵ��κ���Ա������Ŀʱ����������ʹ����ȫ��ͬ���������Ӷ�����Ǳ�ڴ���Բ����Ӱ�졣
���ڶ���������Ա��Ҳ���Ա�֤�ںܳ�ʱ���Ժ����²�����Ŀʱ����ʹ�õ�������û��һ����ı䣬��ʹ�������Ѿ����˸��µİ汾��

��ʵ������Ϊ��������������ύ���汾�⣬Ϊ��֤����������һ�����ȶ��ԣ�ʹ��
composer.lock �������������� 

### ����������ʱ

��Ҫ����������İ汾ʱ�����޸� composer.json �ļ��еİ汾���壬
��ʱ������� `composer install`��composer �ᷢ�� composer.json �� composer.lock �ļ��İ汾��ƥ�䣬�ᾯ�棺
```
Warning: The lock file is not up to date with the latest changes in composer.json. You may be getting outdated dependencies. Run update to update them.
Nothing to install or update
```
��ʱӦ������ `composer update` ���
composer �����ȡ composer.json �ļ����������İ汾��Ȼ���ȷ�еİ汾�Ÿ��µ� composer.lock �ļ�

### ��������ʼ��ʱ

��Ŀ��û�������⣬�����ֿ��ܣ�
һ�ǻ�û���й�composer
������Ŀ�����ǴӰ汾�������صģ�ֻ��composer.lock��composer.json�ļ�
��ʱӦ������composer install�������ȶ�ȡ composer.lock �ļ���

��Ŀ���������⣬��Ҫ����������а汾����ʱ��
Ӧ������composer update����ȡ composer.json �ļ��µİ汾���岢���� composer.lock �ļ�


## autoloader

composer�����ذ�װ������� ����vendorĿ¼��������һ�� `autoload.php` �ļ��������Զ����ؿ��е��ࡣ

```php
require 'vendor/autoload.php';
```

�������ʹ�� Composer �ṩ�� autoloader�����Խ������� `vendor/composer/autoload_*.php` �ļ���������һ���������飬�����ͨ������������������Լ��� autoloader��

### autoload �ֶ�

������ composer.json �� autoload �ֶ��������Լ��� autoloader��

```javascript
{
    "autoload": {
        "psr-4": {"Acme\\": "src/"}
    }
}
```

��� autoload �ֶκ���Ҫ�ٴ����� install ���������� vendor/autoload.php �ļ���

Composer ��ע��һ�� PSR-4 autoloader �� Acme �����ռ䡣

���Զ���һ���������ռ䵽Ŀ¼��ӳ�䡣��ʱ src Ӧ������Ŀ�ĸ�Ŀ¼���� vendor �ļ���ͬ�������� src/Foo.php �ļ�Ӧ�ð��� Acme\Foo �ࡣ

��������ļ�Ҳ������ autoloader ��ʵ��������Խ��������õķ���ֵ�洢�ڱ����У�����Ӹ���������ռ䡣
�������һ�������׼����Զ��������ļ��Ƿǳ����õģ�����

```php
$loader = require 'vendor/autoload.php';
$loader->add('Acme\\Test\\', __DIR__);
```

���� PSR-4 �Զ����أ�classmap Ҳ��֧�ֵġ��������౻�Զ����أ���ʹ������ PSR-0 �淶��


## composer install ���Ŀ¼�ṹ

    MyProject
        |--file1.php
        |--��������
        |--installer
        |--composer
        |--composer.json
        |--composer.lock
        |--vendor
            |--monolog(��װ��������)
            |--autoload.php
            |--composer
                |--autoload_classmap.php
                |--autoload_namespaces.php
                |--autoload_psr4.php
                |--autoload_real.php
                |--autoload_static.php
                |--ClassLoader.php
                |--installed.json
                |--LICENSE




composer update ����ɾ��ԭ����װ�İ汾���ٰ�װ composer.json�ļ�ָ���İ汾


## �漰���İ�

monolog/monolog

mustache/mustache

slim/slim

phpunit

laravel/laravel

laracasts/Laravel-5-Generators-Extended

barryvdh/laravel-debugbar

psr/log

## Q&amp;A

���������require����ݹ����أ�

## source �� dist

```
$ composer info --all slim/slim
name     : slim/slim
descrip. : Slim is a PHP micro framework that helps you quickly write simple yet powerful web applications and APIs
keywords : framework, api, micro, router
versions : 4.x-dev, 3.x-dev, 3.8.1, 3.8.0, 3.7.0, 3.6.0, 3.5.0, 3.4.2, 3.4.1, 3.4.0, 3.3.0, 3.2.2, 3.2.1, 3.2.0, 3.1.0, 3.0.0, 3.0.0-RC3, 3.0.0-RC2, 3.0.0-RC1, 3.0.0-beta2, 3.0-beta1, 2.x-dev, 2.6.3, 2.6.2, 2.6.1, 2.6.0, 2.5.0, 2.4.3, 2.4.2, 2.4.1, 2.4.0, 2.3.5, 2.3.4, 2.3.3, 2.3.2, 2.3.1, 2.3.0, 2.2.0, 2.1.0, 2.0.0, 1.6.7, 1.6.6, 1.6.5, 1.6.4, 1.6.3, 1.6.2, 1.6.1, 1.6.0
type     : library
license  : MIT License (MIT) (OSI approved) https://spdx.org/licenses/MIT.html#licenseText
source   : [git] https://github.com/slimphp/Slim.git 6f765adb5dad996b586ecf6e362bb2ef7ae64ea4
dist     : [zip] https://files.phpcomposer.com/files/slimphp/Slim/6f765adb5dad996b586ecf6e362bb2ef7ae64ea4.zip 6f765adb5dad996b586ecf6e362bb2ef7ae64ea4
names    : slim/slim, psr/http-message-implementation

$ composer install --prefer-source
$ composer install --prefer-dist
```
* --prefer-dist   distribution��ǿ�ƴ��Ѿ����е��ȶ��汾��Դ�ⰲװ����ʹ�� dev �汾
* --prefer-source ǿ�ƴӿ����е�Դ����ⰲװ�������� VCS ��Ϣ
    

