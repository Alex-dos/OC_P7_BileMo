[![Codacy Badge](https://app.codacy.com/project/badge/Grade/18c1b997565e4f66a5f4c1d9608a4266)](https://app.codacy.com/gh/Alex-dos/OC_P7_BileMo/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)
# ⚙️ Installation
____________________
### Requirement 
(you can use this command "composer check" for verify):

- php 7.4+
- composer > 2.0.0

#### Installation :

```bash
composer install
```

You need to create your .env.local with .env and modify with your parameters.
```bash
cp .env .env.local
```

To create a database and install migrations :

```bash
php bin/console doctrine:database:create
php bin/console doctrine:migrations:migrate
php bin/console doctrine:schema:update --force
```

To generate SSL keys for JWT Token :
```bash
mkdir config/jwt
openssl genrsa -out config/jwt/private.pem 4096
openssl rsa -pubout -in config/jwt/private.pem -out config/jwt/public.pem
chmod -R 775 config/
```

Fixtures :
```bash
php bin/console hautelook:fixtures:load  
```   

After that, you can use this command to run this Api :

```bash
symfony serve
```

You can access to Swagger Api from this link : http://localhost:8000/api.
