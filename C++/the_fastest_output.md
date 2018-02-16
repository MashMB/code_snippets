### The fastest output for string
```
void fast_output(char* cString) {
	while(*cString) {
		putchar_unlocked(*cString);
		cString++;
	}
}
```

```
int main(int argc, char** argv) {
	char word[5] = {'t', 'e', 's', 't', '\0'};
	fast_output(word);

	return 0;
}
```

### The fastest output for numbers
```
void fast_output(int number) {
	if(number / 10 != 0) {
		fast_output(number / 10);
	}
	
	putchar_unlocked((number % 10) + '0');
}
```

```
int main(int argc, char** argv) {
	int counter = 100;
	fast_output(counter);

	return 0;
}
```