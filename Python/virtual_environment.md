### Creating virtual environment (Linux and Windows)
```
python -m venv [name]
```

### Activation of virtual environment (Linux)
```
source [name]/bin/activate
```

### Activation of virtual environment (Windows)
```
[name]\Scripts\activate
```

### Dactivation of virtual environment (Linux and Windows)
```
deactivate
```

### Saving actual used libraries in virtual environment
```
pip freeze > requirements.txt
```

### Installation of libraries from requirements.txt in virtual environment
```
pip install -r requirements.txt
```