### Redirect logging messages to JTextArea
```
package [package_name]

import java.util.logging.Level;
import java.util.logging.LogRecord;
import java.util.logging.StreamHandler;
import javax.swing.JTextArea;

public class TextAreaHandler extends StreamHandler {

	private LogFormat formatter = null;
	private JTextArea loggingArea = null;

	public TextAreaHandler() {
		this.formatter = new LogFormat();
		this.setLevel(Level.ALL);
		this.setFormatter(this.formatter);
	}

	public void publish(LogRecord record) {
		super.publish(record);
		flush();

		if(loggingArea != null) {
			loggingArea.append(getFormatter().format(record));
		}
	}

	public void setLoggingArea(JTextArea textArea) {
		loggingArea = textArea;
	}

}
```

### Custom logs format
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

### Usage
```
package [package_name];

import java.util.logging.Logger;

public class Main {

	private TextAreaHandler tah = new TextAreaHandler();
	private static Logger logger = Logger.getLogger(Main.class.getName());
	
	public static void main(String[] args) {
		logger.addHandler(tah);
		logger.info("Info message");
	}
	
}
```