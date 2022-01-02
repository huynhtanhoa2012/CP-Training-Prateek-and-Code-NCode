# Standard Library


## Containers
<img src="Photos/containers.png" width="500">

* Multiset: can contain duplicate values
* Multimap: can contain duplicate values
* Priority Queue:
    * get maximum elements
    * get minimum elements
    * remove maximum/minimum elements
    * insert elements

## Array (Classic Array)
* Pass an array into a function is **passed by reference**
* When working with array **need to pass the size of array**.
* Size of array in main function is differnt with size of array in function.
> int arr[] <=> int * arr

```c++
int arr[] = {1,5,4,3,2};
int n = sizeof(arr)/sizeof(int);
```

#### Array in STL
* All STL containers **pass by values**
* Hence, if we want to modify the array need to pass by reference.
* Using keyword `const` to pass array into function (good practice)

* Some methods:
    * `at(i)`: get ith element
    * `front()`: get front element
    * `back()`: get back element
```c++
void updateArray(array<int,6> &arr, int i, int val){
    arr[i] = val;
}
int main(){
    array<int,6> arr = {1,2,3,6,7,8};
    updateArray(arr, 0, 100);

    // Classic sorting
    int arr[] = {1,2,3,6,7,8};
    sort(arr, arr+n);

    //STL sorting
    sort(arr.begin, arr.end())

    // Fill.
    array<int, 10> fives;
    fives.fill(5);

    // For each loop
    for(auto x : fives)
}
```


## Vector
Some differences with array:

* Resize itself automatically when an element is inserted
* Contiguous store locations, reallocation happens when underlying array is full.
* Everytime doubling happens(when the capacity is full) it took linear time O(n) to double(`push_back()` function)
    * we can use `resever()` function to prevent doubling happens regularly.

Some methods:
* `pop_back()`, `push_back()`, `reserve()`, `size()`, `clear()`

```c++
//Empty constructor
vector<int> first;

// Fill constructor
vector<int> second(4,20);

// Range constructor
int numbers[] = {10,20,30,40};
vector<int> third(numbers, numbers+4);

// Copy constructor
vector<int> fourth(third);

// Another way 
vector<int> fifth = {1,2,3,4,5};

// Multimensional
vector<vector<int>> Matrix;

// Good practice pass vector as reference into function
void some_function(const vector<int> &v){...}

// If we want to change the content of vector
void some_function(vector<int> &v) {...}
```

## Deque
* Sequence container with dynamic sizes that can be expanded or contracted on both ends (front or back)
* It not guarantedd to store all its elements in contiguous storage locations: accessing elements in a deque by offsetting a pointer to another element causes undefined behavior
* Eleemnts of a deque can be scattered in different chunks of storage

Soem methods:
* pop_back(), pop_front()
* push_back(). push_front()
* back(), front()
* clear(), size()

```c++
deque<int> first;
deque<int> second(4,100);
deque<int> third(second.begin(), second.end());
deque<int> fourth(third);

deque<int> dq(10);

for(int i=0; i<10; i++){
    dq[i] = i*i;
}

for(auto x: dq) cout << x << " ";

for(int i=0; i<10; i++){
    cout << dq.at(i);
}
```

## Set
* add an element, but do not allow duples [duplicates?]
* remove elements
* get count of elements (distinct elements)
* check whether elements are present in set

Add, remove and check the presence of particular element in **O(log N)**. Count elements in the set **O(1)** 
```c++
set<int> s;
for(int i = 1; i <= 100; i++) {
    s.insert(i);
    s.erase(i);
}
if(s.find(42) != s.end()) {...}
```

* It’s impossible to take the element in set **by index**
* The only way to traverse the elements of set is to use iterators.

```c++
set< int > S;

int r = 0;
for(set<int>::const_iterator it = S.begin(); it != S.end(); it++) {
    r += *it;
}
```

## String
* Beware of **(s.length()-1)** on empty string because s.length() is `unsigned` and `unsigned(0) – 1` is definitely not what you are expecting!
```c++
string s = “hello”;
string
s1 = s.substr(0, 3), // “hel”
s2 = s.substr(1, 3), // “ell”
s3 = s.substr(0, s.length()-1), “hell”
s4 = s.substr(1); // “ello”
```
## Stack, Queue 
Done
## Map
Done

## Priority Queue

## Hash Table