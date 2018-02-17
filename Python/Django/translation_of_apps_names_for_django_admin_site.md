### Translating app name in apps.py
```
from django.apps import AppConfig

class [application_name]Config(AppConfig):
	name = '[orginal_name]'
	verbose_name = "[translated_name]"
```

### Indication to configuration in init.py
```
default_app_config = '[orginal_app_name].apps.[name_of_configuration_from_apps_py]'
```

### Translating model name in models.py
```
from django.db import models

class [model_name](models.Model):
	class Meta:
		verbose_name = "[translated_name_in_singular]"
		verbose_name_plural = "[translated_name_in_plural]"
```