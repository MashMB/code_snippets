### Simple trick to detect IP address of proper network interface for communication
```
public static String detectInterface() {
	String ip = null;

	try {
		Socket validator = new Socket();
		validator.connect(new InetSocketAddress("google.com", 80));
		ip = validator.getLocalAddress().getHostAddress();
		validator.close();
	} catch (IOException ex) {
		ex.printStackTrace();
	}

	return ip;
}
```