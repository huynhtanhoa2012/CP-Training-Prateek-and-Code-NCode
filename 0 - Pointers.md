# Pointers

Pointers - variables that store address of another varibale
* p -> address of a
* *p -> value at address
* p = &a -> point to a
* *p = 20 -> change value at the address pointer point to, not change the value of p.
```c++
int a;
int *p;
p = &a;   // &a = address of a
a = 5;

print p  // 204
print &a // 204
print &p // 64
print *p // 5  => deferencing

// modify value a using pointer p
*p = 8
print a // 8
```

## Working with pointers

```c++
int a;   // integer
int *p;  // pointers to integer
char c;  // character
char *po // pointer to character
double d // double
double *p1 // pointer to double

p = &a;  // p points to a
a = 8;
print *p // 8
```

```c++
// Pointer arithmetic
int a = 10;
int *p;
p = &a;

print p;    // p is 2002
print *p;   // 10
print p+1;  // 2006
print *(p+1)  // garbage value
```

## Pointer types, void pointer, pointer arithmetic
* int* -> int -> 4 bytes
* char* -> char -> 1 bytes
* user defined* -> user defined
```c++
int a = 1025;
int *p;
p = &a;

print sizeof(int)  // 4 bytes
print p   // address 4192228
print *p  // value = 1025

char *p0;
p0 = (char*)p;   // typecasting
print p0   // address 4192228
print *p0  // value = 1
// 1025  = 00000000 00000000 00000100 00000001
```

## Pointer to pointer
<img src="Photos/pointer.png" width="600">




