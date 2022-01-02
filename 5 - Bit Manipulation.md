# Bit manipulation

## 1. Operators
Most signicant big store signbit (decide whether it is positive or negative)
### AND &
```c++
0 & 0 = 0
1 & 0 = 0
0 & 1 = 0
1 & 1 = 1

5 & 7 
101 & 111 = 101
```
### OR |
```c++
1 | 0 = 1
0 | 1 = 1
1 | 1 = 1
0 | 0 = 0

5 | 8
0101 | 1000 = 1101
```
### XOR ^
```c++
0 ^ 0 = 0
1 ^ 1 = 0
1 ^ 0 = 1
0 ^ 1 = 1

5 ^ 7
101 | 111 = 10
```
### Not ~
```c++
~0 = 1
~1 = 0

~000101 = 111010
```
### Left Shift <<
> a << b = a*(2^b)
```c++
5 << 2    // shift 2 bits

0000101 << 2
= 0010100  (20)
```
### Right Shift >>
> a << b = a/(2^b)
```c++
10 >> 1    // shift 2 bits

0001010 >> 1
= 0000101 (5)
```

## Odd Even

```c++
int x;
cin >> x;
if(x&1) cout << "Odd";
else cout << "Even";
```

## Bit Maniputation
1. Get i-th Bit
2. Set i-th Bit
3. Clear i-th Bit

```c++
int getIthBit(int n, int i){
    int mask = (1<<i);
    return (n & mask) > 0 ? 1 : 0;
} 

void setIthbit(int &n, int i){
    int mask = (1<<i);
    n = (n|mask);
}

void clearIthBit(int n, int i){
    int mask = ~(1<<i);
    n = n&mask;
}

void updateIthBit(int n, int i, int v){

    clearIthBit(n,i);
    int mask = (v<<i);
    n = n|mask;
}

void clearLastIbits(int &n, int i){
    int mask = (-1 << i);
    n = n&mask;
}

void clearBitsInRange(int &n, int i, int j){
    int a = (~0) << (j+1);
    int b = (1<<i) -1;
    int mask = a|b;
    n = n&mask;
}

int main(){
    int n = 5;
    int i;
    cin >> i;
    cout<< getIthBit(n, i) << endl;
}
```

## Replace Bits