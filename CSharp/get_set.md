### GET and SET in property
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Test
{
	class Person
	{
		string _name = null;
		string _surname = null;

		public Person(string name, string surname) {
			this._name = name;
			this._surname = surname;
		}

		public string name
		{
			get
			{
				return _name;
			}

			set
			{
				_name = name;
			}
		}

		public string surname
		{
			get
			{
				return _surname;
			}

			set
			{
				_surname = surname;
			}
		}
	}
}
```

### Usage in other class
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Test
{
	class Program
	{
		static void Main(string[] args)
		{
			var p1 = new Test.Person("Jan", "Kowalski");

			Console.WriteLine(p1.name + " " + p1.surname);
		}
	}
}
```