# Prime Numbers
## Approach
All divisors of a number N occur in pairs of (a,b):  `a*b= N`

**Claim: for a divisor pair(a,b) one of them lies below sqrt(N) and other lies above**

Proof: There would be 3 cases:
* Case 1: both a and b are below sqrt(N)
* Case 2: both a and b are above sqrt(N)
* Case 3: one is below sqrt(N) and above sqrt(N)

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

# Prime Sieve

1. find all the prime numbers that are less than or equal to a given number `N`.
2. find out whether a number is a prime number.

The basic idea is that at each iteration one prime number is picked up and **all its multiples are eliminated**. After the elimination process is complete, all the unmarked numbers that remain are prime.

### Pseudo code
1. Mark all the numbers as prime numbers except 1
2. Traverse over each prime numbers smaller than sqrt(N)
3. For each prime number, mark its multiples as composite numbers
4. Numbers, which are not the multiples of any number, will remain marked as prime number and others will change to composite numbers.

```c++
void sieve(int N) {
        vector<bool> isPrime(N+1, true);
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

# Prime factorization
Breaking a number in terms of its prime factors

## Brute force O(n)
```c++
vector<int> factorize(int n) {
    for (int i = 2; i * i <= n; ++i) {
        if(n%i==0){
            int cnt = 0;
            while (n % i == 0) {
                cnt++;
                n /= i; 
            }
            cout <<i<<"^" <<cnt<<",";
        }
    }
}
```
## Optimised Approach O(sqrt(n))
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
# Segmented Sieve
* There is no need to keep the whole array `is_prime[1...n]` at all time
* It is enough to just keep the prime numbers until the root of n, i.e. `prime[1... sqrt(n)]`
```c++

int sieverArr[N+1] = {0};
vector<int> primes;
void sieve(){
    for(long long i=2; i<=N; i++){
        if(sieveArr[i]==0){
            primes.pushback(i);
            // mark the multiples of i as non-prime
            for(long long j=i*i; j<=N; j+=i){
                sieverArr[j] = 1;
            }
        }
    }

}





```