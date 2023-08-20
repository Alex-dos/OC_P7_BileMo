[![Codacy Badge](https://app.codacy.com/project/badge/Grade/a4b4ab97ebda4db390f9f568bf513e5a)](https://app.codacy.com/gh/Alex-dos/OC_P7_BileMo/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)

Documentation :
https://candy-akubra-ce2.notion.site/Documentation-Technique-API-BileMO-ad6c9292ae0544f589ce7146642b812e?pvs=4

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
