### Declaration of static and media files (settings.py)
```
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(ENV_PATH, '../public/static/')
STATICFILES_DIRS = (
	os.path.join(BASE_DIR, 'static'),
)

MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(ENV_PATH, '../public/media')
```