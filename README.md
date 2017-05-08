ysblogbundle
============

##### 1. Add to parameters.yml
```
parameters:
    database_host: 172.18.0.1
    database_port: null
    database_name: ysblogbundle
    database_user: root
    database_password: root
    mailer_transport: smtp
    mailer_host: 127.0.0.1
    mailer_user: yaroslav.solokha@gmail.com
    mailer_password: null
    secret: 8ed60d15706d13261ee6705544edc13db3b61711
    facebook_client_id: 1834510506871534
    facebook_client_secret: 834958a863dcdc669064e626b88653f7
    google_client_id: 289872286967-n8jv6dh4ds29fon1fo53d4luhrr713k5.apps.googleusercontent.com
    google_client_secret: a46i7rjxVnx3nP-4oJn-Udb5
```
##### 2. Create DB
```
$ bin/console doctrine:database:create
```
##### 3. Add to your composer:
```
"require": {
    ...
    "ys/user-bundle" : "dev-master",
    "sonata-project/user-bundle": "dev-add_support_for_fos_user2"
    },
"repositories" : [
...
{
    "type" : "vcs",
    "url" : "https://github.com/yaroslavsolokha/YSUserBundle.git"
}],
```
##### 4. Composer update
```
$ composer update
```
##### 5. Setup YSUserBundle - https://github.com/yaroslavsolokha/YSUserBundle
##### 6. Add to AppKernel.php
```
 $bundles = [
     ...
     new YS\BlogBundle\YSBlogBundle()
 ];
```
##### 7. Create schema
```
$ bin/console doctrine:schema:create
```
##### 8. Add import to config.yml
```
imports:
    ...
    - { resource: "@YSBlogBundle/Resources/config/config.yml" }
```
        

