### Configuration of main urls.py
```
from django.conf.urls import include
from django.conf.urls import url
from django.contrib import admin
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
	url(r'^admin/', admin.site.urls),
	url(r'', include('[application_name].urls')),
] + static(settings.MEDIA_URL, document_root = settings.MEDIA_ROOT)
```

### Configuration of urls.py in concrete application in Django project
```
from django.conf.urls import url
from . import views

urlpatterns = [
	url(r'^tekst_url/$', views.[name_of_view], name='[useful_name]'),
	url(r'^tekst_url/(?P<slug>[-\w]+)/$', views.[name_of_view], name='[useful_name]'),
]
```

### Automatic view build for subpage (views.py)
```
def [view_name](request, slug):    
	[variable_name] = get_object_or_404([model_name], customURL=slug)
		
	return render(request, '[template.html]', {'[variable_name]': [variable_name]})
```