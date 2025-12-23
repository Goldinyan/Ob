Date: 2025-12-20
Tags: {
#W
[[%C]]
[[%Basics]]
[[%Computer Science]]
}


# Basic Types - C

### Basic Types


The actual size of these can vary between different computers, (32-Bit, 64-Bit, etc) , but can be determinted using *sizeof()* in C.

```c
printf("sizeof(char) = %zu\n", sizeof(char));
```

- **int**  
  Integer type. Size depends on the platform (commonly 4 bytes).

  ```c
int a = 42;
  ```

- **float**  
  Single‑precision floating point number (commonly 4 bytes).  

  ```c
float b = 3.14f;
  ```

- **char**  
  Single character, stored internally as an integer (1 byte).  (Single Qoutes 'A')

  ```c
char c = 'A';
  ```

- **char\***  
  Pointer to a character, often used for strings (arrays of characters).  (Double Qoutes "")

  ```c
char *str = "Hello";
  ```

- **double**
	Double-Precision floating point number (8 bytes)
```c
double d = 2.31233;
```


## Arrays

```c
int arr[3] = {1, 2, 3};
```
- Access with indices: `arr[0]`.  
- `char[]` is often used for strings.


### constants

```c 
int main(){
	int x = 5;
	x = 10; // this is OK
}
```

```c
int main(){
	const int x = 5;
	x = 10; // ERROR
}
```


# References