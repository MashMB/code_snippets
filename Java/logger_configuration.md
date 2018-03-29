### Custom messages of logger appearance
```
package [package_name];

import java.text.DateFormat;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.logging.Formatter;
import java.util.logging.LogRecord;

public class LogFormat extends Formatter {

	private DateFormat df = new SimpleDateFormat("HH:mm:ss");
	
	@Override
	public String format(LogRecord lr) {
		StringBuilder sb = new StringBuilder();
		sb.append(df.format(new Date(lr.getMillis())));
		sb.append(" - ");
		sb.append("(").append(lr.getLoggerName()).append(")");
		sb.append(" ");
		sb.append("[").append(lr.getLevel()).append("]");
		sb.append(":").append(" ");
		sb.append(formatMessage(lr));
		sb.append("\n");
		
		return sb.toString();
	}
	
}
```

### Create custom logger
```
package [package_name];

import java.util.logging.ConsoleHandler;
import java.util.logging.Level;
import java.util.logging.Logger;

public class CustomLogger {
	
	private String className = null;
	private LogFormat formatter = null;
	private ConsoleHandler handler = null;
	
	public CustomLogger(String className) {
		this.className = className;
		this.formatter = new LogFormat();
		this.handler = new ConsoleHandler();
	}
	
	public Logger getLogger() {
		Logger logger = Logger.getLogger(className);
		logger.setUseParentHandlers(false);
		logger.setLevel(Level.ALL);
		handler.setLevel(Level.ALL);
		handler.setFormatter(formatter);
		logger.addHandler(handler);
		
		return logger;
	}
	
}
```

### Custom logger usage
```
package [package_name];

import java.util.logging.Logger;

public class Main {
	
	private static CustomLogger cl = new CustomLogger(Main.class.getName());
	private static Logger logger = cl.getLogger();
	
	public static void main(String[] args) {
		logger.info("Info message");
	}
	
}
```

### Default Java logger levels
```
FINE - success level
CONFIG - configuration level
INFO - info level
WARNING - warning level
SEVERE - error level
```