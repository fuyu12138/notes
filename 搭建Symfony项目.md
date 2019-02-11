## 创建项目
composer create-project symfony/skeleton my-project<br>
cd my-project<br>
composer require symfony/web-server-bundle --dev

## 路由
composer require annotations


## apache配置
composer require symfony/apache-pack

## ORM-Doctrine
composer require symfony/orm-pack<br>
composer require symfony/maker-bundle --dev

## 数据库配置
.env<br>
DATABASE_URL="mysql://db_user:db_password@127.0.0.1:3306/db_name"

## LexikJWTAuthenticationBundle安装
1. composer require lexik/jwt-authentication-bundle --dev
2. 生成ssh秘钥
$ mkdir -p config/jwt # For Symfony3+, no need of the -p option<br>
$ openssl genrsa -out config/jwt/private.pem -aes256 4096<br>
$ openssl rsa -pubout -in config/jwt/private.pem -out config/jwt/public.pem
3. 配置
.env修改密码
config/packages/lexik_jwt_authentication.yaml


## 从数据库生成实体
https://symfony.com/doc/current/doctrine/reverse_engineering.html<br>
php bin/console doctrine:mapping:import App\Entity annotation --path=src/Entity<br>
get/set<br>
php bin/console make:entity --regenerate App

## //修改实体
 php bin/console make:migration<br>
 php bin/console doctrine:migrations:migrate
 
## JWT配置
配置security.yaml
