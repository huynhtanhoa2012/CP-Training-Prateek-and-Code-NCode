# Number theory


# 2. Greatest Common Divisor (GCD)
The GCD of two or more numbers is the largest positive number that divides all the numbers that are considered.

## Naive approach
Traverse all the numbers from min(A,B) to 1 and check whether the current divides both A and B. If yes, it is the GCD of A and B.

```c++
int GCD(int A, int B) {
    int m = min(A, B), gcd;
    for(int i = m; i > 0; --i)
        if(A % i == 0 && B % i == 0) {
            gcd = i;
            return gcd;
        }
}
```
**Time Complexity: O(min(A, B))**
## Euclid's algorithm
The idea behind this algorithm is GCD(A,B) = GCD(B, A%B). It will recurse until A%B = 0.
```c++
int GCD(int A, int B) {
    if(A<B) swap(A,B);
    if(B==0) return A;
    else
        return GCD(B, A % B);
}
```
**Time Complexity: O(log(max(A, B)))**



# 3. Primality - Prime number
Primality test is to determine whether the input integer is a prime number of not.

Example:
> Input: 5   output: true
>
> Input: 12  output: false


## Naive Approach
```c++
bool isPrime(int n){
    if(n==1){
        return false;
    }
       
    for(int i=2;i<n;i++){
        if(n%i == 0){
            return false;
        }
    }
    return true;
}
```
**Complexity: O(n)**

## Better Approach
All divisors of a number N occur in pairs of (a,b):   `a*b= N`

Example:
> 12 has the following divisors d = 1, 2, 3, 4, 6, 12
>
> Pairs are: (1, 12), (2, 6), (3, 4)

**Claim: for a divisor pair(a,b) one of them lies below sqrt(N) and other lies above**

Proof: There would be 3 cases:
* Case 1: both a and b are below sqrt(N)
* Case 2: both a and b are above sqrt(N)
* Case 3: one is below sqrt(N) and above sqrt(N)

#### Case 1: Both a and b are below sqrt(N)
> Let's assume that this statement is true, hence
>
> a<sqrt(N) and b<sqrt(N) but then a*b < N
>
> Which contracdicts the fact that a*b=N Hence, case 1 is not true
#### Case 2: Similar to case 1
#### Case 3: One is below sqrt(N) and above sqrt(N)

```c++
bool isPrime(int n){
    if(n==1){
        return false;
    }
    
    // i*i<=N  <=> i<=sqrt(N)
    for(int i=2;i*i<=n;i++){
        if(n%i == 0){
            return false;
        }
    }
    return true;
}
```
**Complexity: O(sqrt(N))**


# 4. Sieve of Eratosthenes

We can use the *Sieve of Eratosthenes* to find all the prime numbers that are less than or equal to a given number `N` or to find out whether a number is a prime number.

The basic idea is that at each iteration one prime number is picked up and **all its multiples are eliminated**. After the elimination process is complete, all the unmarked numbers that remain are prime.

### Pseudo code
1. Mark all the numbers as prime numbers except 1
2. Traverse over each prime numbers smaller than sqrt(N)
3. For each prime number, mark its multiples as composite numbers
4. Numbers, which are not the multiples of any number, will remain marked as prime number and others will change to composite numbers.

```c++
void sieve(int N) {
        bool isPrime[N+1];
        for(int i = 0; i <= N;++i) {
            isPrime[i] = true;
        }
        isPrime[0] = false;
        isPrime[1] = false;
        for(int i = 2; i * i <= N; ++i) {
            if(isPrime[i] == true) {     
                // Mark all the multiples of i as composite               
                for(int j = i * i; j <= N ;j += i)
                    isPrime[j] = false;
            }
        }
    }
```
**Complexity: O(NloglogN)**


## Fast Factorization
Modification of Sieve of Eratosthenes for fast factorization

```c++
vector<int> factorize(int n) {
    vector<int> res;
    for (int i = 2; i * i <= n; ++i) {
        while (n % i == 0) {
            res.push_back(i);
            n /= i;
        }
    }
    if (n != 1) {
        res.push_back(n);
    }
    return res;
}
```
## Sieve of Eratosthenes on the segment:
Sometimes you need to find all the primes that are in the range [L..R] and not in [1..N] , where R is a large number.

You are allowed to create an array of integers with size (R - L + 1)


## Euler’s totient function
Euler's Totient function is a function that is related to getting the number of numbers that are coprime to a certain number  that are less than or equal to it

Numbers `a` and `b` are coprime if gcd(a,b) = 1.

For example: 
> ϕ(12) = 4, because 1, 5, 7 and 11 are coprime to 12.

```c++
int findCoprime(int n)
{
    int result = 1;
    for (int i = 2; i < n; i++)
        if (gcd(i, n) == 1)
            result++;
    return result;
}
```


















