### Installing Read the Docs theme
```
pip install sphinx-rtd-theme
```

### Custom settings in configuration file
```
html_theme = 'sphinx_rtd_theme'

html_theme_options = {
	'prev_next_buttons_location': 'bottom',
	'sticky_navigation': True,
	'collapse_navigation': False
}

# Hidding "Show Source" button
html_show_sourcelink = False
```