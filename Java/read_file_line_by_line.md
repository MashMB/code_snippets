### Reading line by line with BufferedReader
```
package [name];

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class Main {

	public static void main(String[] args) {
		String fileName = "text.txt";
		BufferedReader br = null;
		FileReader fr = null;
		Strnig oneLine = null;

		try {
			fr = new FileReader(fileName);
			br = new BufferedReader(fr);

			while((oneLine = br.readLine()) != null) {
				System.out.println(oneLine);
			}
			br.close();

		} catch(IOException ex) {
			System.out.println("Problem with reading file.");
		}

	}
	
}
```

### Reading file line by line with Stream
```
package [name];

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.stream.Stream;

public class Main {

	public static void main(String[] args) {
		String fileName = "test.txt";

		try(Stream<String> stream = Files.lines(Paths.get(fileName))) {
			stream.forEach(System.out::println);
		} catch(IOExcepion ex) {
			System.out.println("Problem with reading file.");
		}

	}
	
}
```