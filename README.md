# Nepal Map

The Nepal instance of [Wazimap](https://github.com/Code4SA/wazimap), a Django application for exploring census and other similar data.

## Local development

1. clone the repo
2. ``cd nepalmap``
2. ``mkvirtualenv nepalmap``
3. ``pip install -r requirements.txt``

You will need a Postgres database:

```
psql -U postgres
create user wazimap_np with password 'wazimap_np';
create database wazimap_np;
grant all privileges on database wazimap_np to wazimap_np;
```

Import the data into the new database:
```
cat sql/*.sql | psql -U wazimap_np -W wazimap_np
```

Run migrations to keep Django happy:
```
python manage.py migrate
```

Start the server:
```
python manage.py runserver
```


## License

NepalMap code is licensed under the [MIT License](https://opensource.org/licenses/MIT).
