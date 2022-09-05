## Website subscription service

- Use composer to install all necessary vendor packages
- Update .env with the database connection settings
- Update .env as follows
```
QUEUE_CONNECTION=database
...
MAIL_MAILER=smtp
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME={mailtrap_USERNAME}
MAIL_PASSWORD={mailtrap_PASSWORD}
MAIL_ENCRYPTION=tls
```

- Run migrations to generate all database tables

Once website posts and subscribers have been created using the shared Postman collection, you can test the service by running these commands below:

- To send job to queue
```
php artisan email:subscribers
```

- Execute queued jobs
```
php artisan queue:work --stop-when-empty
```
