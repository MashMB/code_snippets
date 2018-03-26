### HTTP GET request in Java
```
package [package_name];

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;

public class Request {
	
	private String userAgent = "Mozilla/5.0";
	private String urlAddress = null;

	public Request(String urlAddress) {
		this.urlAddress = urlAddress;
	}
	
	private String getResponse(InputStreamReader inputStream) {
		StringBuilder response = new StringBuilder();
		String line = null;
		
		try {
			BufferedReader input = new BufferedReader(inputStream);
			
			while((line = input.readLine()) != null) {
				response.append(line);
			}
			
			input.close();
		} catch(IOException ex) {
			System.out.println(ex);
		}
		
		return response.toString();
	}
	
	public String GETRequest() {		
		try {
			URL url = new URL(urlAddress);
			HttpURLConnection connection = (HttpURLConnection)url.openConnection();
			connection.setRequestMethod("GET");
			connection.setRequestProperty("User-Agent", userAgent);
			
			return getResponse(new InputStreamReader(connection.getInputStream()));
		} catch(IOException ex) {
			System.out.println(ex);
		}
		
		return null;
	}
}
```