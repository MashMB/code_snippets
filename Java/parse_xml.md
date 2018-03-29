### XML file parsing example
```
package [package_name];

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.StringReader;
import java.net.URL;
import javax.xml.parsers.DocumentBuilder;
import javax.xml.parsers.DocumentBuilderFactory;
import javax.xml.parsers.ParserConfigurationException;
import org.w3c.dom.Document;
import org.xml.sax.InputSource;
import org.xml.sax.SAXException;

public class XMLParser {

	public static Document loadXML(String xmlContent) {
		Document xmlFile = null;
		
		try {
			DocumentBuilderFactory dbf = DocumentBuilderFactory.newInstance();
			DocumentBuilder db = dbf.newDocumentBuilder();
			InputSource is = new InputSource(new StringReader(xmlContent));
			xmlFile = db.parse(is);
			xmlFile.getDocumentElement().normalize();
		} catch(IOException | ParserConfigurationException | SAXException ex) {
			System.out.println(ex);
		}
		
		return xmlFile;
	}
	
	public static Document loadXMLfromURL(String urlAddress) {
		Document xmlFile = null;
		
		try {
			URL url = new URL(urlAddress);
			BufferedReader bf = new BufferedReader(new InputStreamReader(url.openStream()));
			StringBuilder xmlContent = new StringBuilder();
			String line = null;
			
			while((line = bf.readLine()) != null) {
				xmlContent.append(line);
			}
			
			bf.close();
			xmlFile = loadXML(xmlContent.toString());
		} catch(IOException ex) {
			System.out.println(ex);
		}
		
		return xmlFile;
	}
	
}

```