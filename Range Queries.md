# Range queries
Typeical range queries are:
* **sum(a,b)**: sum of values in range[a,b]
* **min(a,b)**: minimum value in range[a,b]
* **max(a,b)**: maximum value in range[a,b]

## Naive approach 
```c++
int sum(int a, int b){
    int sum = 0;
    for(int i=a; a<=b; a++){
        sum += arr[i];
    }
    return sum;
}
```
**Complexity: O(n)**
> However when a and b are large, this approach is slow.


## Sum Sub arrays
### Brute force
```c++
int largestSubarraySum(int arr[], int n)
    int largestSum = 0;
    for(int i=0; i<n; i++){
        for(int j=i; j<n;j++){

            int subarraySum = 0;
            for(int k=i; k<=j; k++){
                subarraySum += arr[k];
            }
            largestSum = max(largestSum, subarraySum)
        }
    }
    return largestSum;
}
```
**Complexity: O(n^3)**

### Prefix Sum

```c++
int largestSubarray(int arr[], int n){
    
    // Prefix Sums; 
    int prefix[n] = {0};
    prefix[0] = arr[0];
    for(int i=1; i<n; i++){
        prefix[i] = prefix[i-1] + arr[i];
    }

    // Count largest Sum
    int largestSum = 0;
    for(int i=0; i<n; i++){
        for(int j=i; j<n;j++){

            // If i = 0 answer = prefix[j];
            int subarraySum = i>0 ? prefix[j] - prefix[i-1] : prefix[j];
            largestSum = max(largestSum, subarraySum)
        }
    }
    return largestSum;
}
```
**Complexity: O(n^2)**
### Kadane algorithm
```c++
int maximum_subarray_sum(int arr[], int n){
    int currentSum = 0;
    int largest = 0;
    for(int i=0; i<n;i++){
        currentSum = currentSum + arr[i];
        if(currentSum < 0){
            currentSum = 0;
        }

        largest = max(largest, currentSum);
    }
    return largest;
}
```
**Complexity: O(n)**