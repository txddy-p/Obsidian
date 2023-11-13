Hello World in C
```C
#include <stdio.h>

int main(void){
	printf("hello, world\n");
}
```
1st line is importing the header file(in order to use `printf` in this case).

#### User Input
Similar to Java where there is a scanner class but I'm not necessarily interested in it right now.
[This is where to find user input stuff](https://www.w3schools.com/c/c_user_input.php). I think I might just download Havard CS50's class which deals with this as a stop gap

#### Format Code
`"%s"` for strings , `"%d"` for integers, `"%c"` for characters 

# Loops
#### if, else and else if
```C
#include <stdio.h>

int main(void){
	int a = 100;
	int b = 200;
	int avg = (a+b)/2;
	printf("The average is %d.\n",avg);
	if (a==avg)
	{
		printf("The return value is 0\n");
	}
	
	else if(a>avg)
	{
		printf("The return value is 1\n");
	}

	else
	{
		printf("The return value is -1\n");
	}
}
```

#### while
```C
#include <stdio.h>

int main(void)
{
	int counter;
	int setpoint
	while (counter > setpoint){
		//do something
		counter--;
	}
	while (counter < setpoint){
		//do something
		counter++;
	}
}
```
This is a pretty straightforward way of doing things, I'm just adding it here in case  I need to lok back at it

#### For
```C
#include <stdio.h>

int main(void)
{
	for (int i = 0; i < 3; i++){
		//do something
	}
}
```
This initialises i to zero and compare it to the next number (the boolean expression) and then do the increment


#### do-while
```C
#include <stdio.h>

int main(void)
{
	do{
		//do something
	}
	while(condition){
		//do something or something else
	}
}
```
first do something and then loop


## Functions
```C
#include <stdio.h>
int my_func(int i);
int main(void)
{
	//main function
}

// return type, function name, arguments
int my_func(int i){
	// do something to i
	return i // modifications to i
}
```
data type of void returns nothing


# Arrays


# Compiling

```bash
clang -o hello helloWorld.c -lcs50
gcc -o hello helloWorld.c -lcs50
# compiles the output to hello instead of a.out, the last flag links the cs50 library
```

### Preprocessing
Anything with a `#` needs to be analysed initially before anything happens. The directory `/usr/include` contains the header files.
When you use include for a header file it loads the entire thing

### Compiling
Going from C code to assembly

### Assembling
moving from assembly to machine language

### Linking
takes machine language from user code and links it with libraries used


# Debugging
get debugging via terminal here


# Strings
- have a null character whilst arrays don't have. There's no way to dynamically tell the length of an array

# [[Data Structures and Algorythims]]
