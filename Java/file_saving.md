### Saving file with PrintWriter
```
package [name];

import java.io.FileNotFoundException;
import java.io.PrintWriter;

public class Main {

	public static void main(String[] args) {
		String str = "test";
		PrintWriter pw = null;

		try {
			pw = new PrintWriter("test.txt");
			pw.println(str);
			pw.close();
		} catch(FileNotFoundException ex) {
			System.out.println("File not found.");
		}

	}
	
}
```


### Saving file with Files
```
package [name];

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {

    public static void main(String[] args) {
        String str = "test";

        try {
            Files.write(Paths.get("test.txt"), content.getBytes());
        } catch(FileNotFoundException ex) {
            System.out.println("Problem with saving file.");
        }

    }
    
}
```