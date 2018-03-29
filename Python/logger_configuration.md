### Logger configuration
```
logger_level = "INFO"
logger = logging.getLogger(__name__)

if logger_level == "DEBUG":
	logger.setLevel(logging.DEBUG)
	handler = logging.FileHandler("discord_ipc.log")
	handler.setLevel(logging.DEBUG)
	log_format = logging.Formatter("%(asctime)s: [%(levelname)s]: %(message)s", datefmt = "%d.%m.%Y (%H:%M:%S)")
	handler.setFormatter(log_format)
	logger.addHandler(handler)
else:
	logging.basicConfig(format = "%(asctime)s: [%(levelname)s]: %(message)s", datefmt = "%d.%m.%Y (%H:%M:%S)", level = logging.INFO)
```

### Available logger commands
```
# Seen in INFO mode
logger.info()
logger.warning()
logger.error()

# Seen in DEBUG mode
logger.info()
logger.warning()
logger.error()
logger.debug()
```