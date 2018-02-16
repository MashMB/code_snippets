### The fastest input for characters
```
#include <iostream>

using namespace std;

int main(int argc, char** argv) {
	char character = ' ';

	while(character != EOF) {
		character = getchar_unlocked();
	}

	return 0;
}
```

### The fastest input for positive numbers
```
#include <cstdio>
#define MAXIMUM_BUFFER_SIZE 16000000

char buffer[MAXIMUM_BUFFER_SIZE];
char* buffer_indicator = buffer;

int get_number() {
	int tmp = 0;
	
	while(*buffer_indicator < 33) {
		buffer_indicator++;
	}
	
	do {
		tmp = tmp * 10 + *buffer_indicator++ - '0';
	} while(*buffer_indicator > 32);
	
	return tmp;
}

int main(int argc, char** argv) {
	fread(buffer, 1, MAXIMUM_BUFFER_SIZE, stdin);
	int number = get_number();

	return 0;
}
```

### The fastest input for negative numbers
```
#include <cstdio>
#define MAXIMUM_BUFFER_SIZE 16000000

char buffer[MAXIMUM_BUFFER_SIZE];
char* buffer_indicator = buffer;

int get_number() {
	bool negative = false;
	int tmp = 0;
	
	while(*buffer_indicator < 33) {
		buffer_indicator++;
	}
	
	do {
		if(*buffer_indicator == '-') {
			negative = true;
			*buffer_indicator++;
		} else {
			tmp = tmp * 10 + *buffer_indicator++ - '0';
		}
	} while(*buffer_indicator > 32);
	
	if(negative) {
		tmp = -tmp;
	}

	return tmp;
}

int main(int argc, char** argv) {
	fread(buffer, 1, MAXIMUM_BUFFER_SIZE, stdin);
	int number = get_number();

	return 0;
}
```