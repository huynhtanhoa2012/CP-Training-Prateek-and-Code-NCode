# 1. Modular Arithmetic
When one number is divided by another, the modulo operation finds the remainder. It is denoted by the % symbol.

**Properties** 
>(x + y) mod m = (x mod m + y mod m) mod m
>
>(x - y) mod m = (x mod m - y mod m) mod m
>
>(x * y) mod m = (x mod m * y mod m) mod m
>
>x^n mod m = (x mod m)^n mod m

# 2. Modular exponentiation
Exponentiation is a mathematical operation that is expressed as `x^n` and computed as `x^n = x * x * x * x  n( times)`.

## Basic Method
the most basic solution is broken down into small problems.

```c++
int recursivePower(int x, int n){
    if (n==0) return 1;
    return x * recursivePower(x, n-1)
}

int iterativePower(int x, int n){
    int result =1;
    while(n>0){
        result = result * x;
        n--;
    }
    return result;
}
```
**Time Complexity: O(n)**


## Optimized Method - Binary Exponentiation
* **Complexity**: O(log n)
```c++
int binaryPower(int x, int n){
    if(n==0) return 1;
    else if (n%2==0){
        return binaryPower(x*x,n/2);
    }
    else 
        return x*binaryPower(x*x,(n-1)/2);
}
// Iterative approach
int binaryPower(int x, int n){
    int result=1;
    while(n>0)
    {
        if(n % 2 ==1)
            result=result * x;
        x=x*x;
        n=n/2;
    }
    return result;
}
```

## Optimized Method - Modular Exponentiation
> However storing answers that are too large for their respective datatypes is an issue with this method. In such instances, you must use modulus (%)

```c++
int modularPower(int x,int n,int M)
{
    if(n==0)
        return 1;
    else if(n%2 == 0)    
        return modularPower((x*x)%M,n/2,M);
    else                      
        return (x*modularPower((x*x)%M,(n-1)/2,M))%M;
}
// Iterative approach
int modularPower(int x,int n,int M)
{
    int result=1;
    while(n>0)
    {
        if(power % 2 ==1)
            result=(result * x)%M;
        x=(x*x)%M;
        n=n/2;
    }
    return result;
}
```

# Modular Exponentiation
It is a type of exponentiation perforemed over a modulus.

#### Example 1
```c++
23^3 mod 30 = -7^3 mod 30 || 23 mod 30 can be 23 or -7
            = -7^3 mod 30
            = -7^2 * (-7) mod 30
            = 49 * -7 mod 30
            = -133 mode 30
            = -13 mode 30
            = 17 mod 30
            = 17
```
#### Example 2
```c++
31^500 mod 30 = 1^500 mod 30
              = 1 mod 30
              = 1
```
#### Example 3
```c++
242^329 mod 243 = -1^329 mod 243
                = -1^329 mod 243 || -1^328 * -1^1
                = -1 mod 243
                = 242 mod 243
                = 242
```
#### Example 4
```c++
11^7 mod 13 = 11 mod 13 * 11 mod 13 * 11 mod 13...
            = -2 * -2 * -2 * -2 * -2 * -2 * -2
            = -128 mod 13
            = -11 mod 13
            = 2
```