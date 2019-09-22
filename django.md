# Django Notes
## Adding a new App 
python manage.py startapp appname
* In settings.py add appname
```
INSTALLED_APPS = [..., "appname"]
```

## Model Classes
Automatically mapped to database table using models.
```
from djang.db import models
class Move(models.Model):
	x = models.IntegerField()
	y = models.IntegerField()
 ```

[Field](https://docs.djangoproject.com/en/1.11/ref/models/fields/) classes determine how the data is stored in the database.
	Tips:
		Models.IntegerField(null = True) - Make Field Nullable
		Models.IntegerField(blank = True) - Allow empty fields from user
		Models.IntegerField(default = "F") - Setting a default value
		Models.DateTimeField(auto_now = True) - Auto timestamps
		
* Migration workflow
	1. Generate migration script - python manage.py makemigrations (check this)
	2. Show overview of migrations - python manage.py showmigrations
	3. Show SQL for specific migrations - python manage.py sqlmigrate appname migrationname
	4. Run migrations - python manage.py migrate

* django-admin shows all subcommands
* python manage.py startapp <appname> - Used to create new apps or "components"
* Running the python shell - python manage.py shell
* Settings should look like: 'DIRS': [os.path.join(BASE_DIR, "templates")]
* Always add apps into installed apps in settings
