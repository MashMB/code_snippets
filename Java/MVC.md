### MVC structure (Model - View - Controller) and GUI activate
```
package [name];

import javax.swing.SwingUtilities;

public class Main {

	public static void main(String[] args) {
		
		SwingUtilities.invokeLater(() -> {
			Model model = new Model();
			View view = new View(model);
			Controller controller = new Controller(model, view);
			controller.init();
		});
		
	}
	
}
```

In **Model** we store data, in **View** we store GUI components, in **Controller** we are linking GUI components with actions and data.