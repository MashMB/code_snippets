### Declaration of new texts on Django admin site (settings.py)
```
ADMIN_SITE_HEADER = "Text that will be shown on login page and Django admin site"
ADMIN_SITE_TITLE = "Text that will be shown on browser tab"
ADMIN_SITE_INDEX_TITLE = "Text that will be shown on Django admin site"
```

### Usage of variables for new texts from settings.py (urls.py)
```
from django.conf import settings

admin.site.site_header = settings.ADMIN_SITE_HEADER
admin.site.site_title = settings.ADMIN_SITE_TITLE
admin.site.index_title = settings.ADMIN_SITE_INDEX_TITLE
```

### Model and modified view registration in Django admin site
```
from django.contrib import admin
from .models import [model_name]

@admin.register([model_name])
class [model_name](admin.ModelAdmin):
	list_display = ('[column_one]', '[column_two]')
	list_display_links = ('[column_one]', '[column_two]')
	list_per_page = [quantity_of_records_on_one_site]
	ordering = ('[column_two]',)
	exclude = ('[first_column_to_hide]', '[second_column_to_hide]') 
```