# Dynamic Programming

* For problems with **optimal substructure** and **overlapping subproblems**.
* DP is an optimization technique

## Top Down DP - Recursive approach
We start building the big solution right way by build it from smaller solutions

```c++
int fib(int n, int dp[]){
    // Base case
    if(n==0 or n==1){
        return n;
    }

    // Check if the starte already computed
    if(dp[n] != 0){
        return dp[n];
    }

    // If not yet store it
    return dp[n] = fib(n-1, dp) + fib(n-2, dp);
}
```


## Bottom Up DP - Iterative approach
We start with small solutions and then use the small solutions to build larger solutions

```c++
int fib2(int n){
    int dp[n+1] = {0};

    // base case => assignment
    dp[0] = 0;
    dp[1] = 1;

    // bottom up
    for(int i=2; i<=n; i++){
        dp[i] = dp[i-1] + dp[i-2];
    }

    return dp[n];
}
```