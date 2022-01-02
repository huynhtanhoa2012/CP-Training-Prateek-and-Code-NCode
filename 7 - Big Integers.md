# Big Integer

Big Integer is used for mathematical operation which involves very big integer calculations that are outside the limit of all available primitive data types.


## Large Addition
Given 2 large numbers. The numbers may not fit into long long int, the task is to add these two numbers.
> Input: 
>
> str1 = "3333111111111111",
>
> str2 = "444222222211111"
> 
> Output: "337773333332222"

```c++

int digitToChar(int digit){
    return digit + '0';
}

int charToDigit(char ch){
    return ch - '0';
}

string addNumbers(string n1, string n2){
    //Make sure N2 is larger
    if(n1.length() > n2.length()){
        swap(n1, n2);
    }

    string result = "";
    // Reverse
    reverse(n1.begin(), n1.end());
    reverse(n2.begin(), n2.end());

    // Add digit upto a n1.length()
    int carry = 0;
    for(int i=0; i<n1.length(); i++){
        int d1 = charToDigit(n1[i]);
        int d2 = charToDigit(n2[i]);
        int sum = d1 + d2 + carry;

        int output_digit = sum % 10;
        carry = sum/10;

        result.push_back(digitToChar(output_digit));
    }
    
    for(int i=n1.length(); i<n2.length(); i++){
        int d2 = charToDigit(n2[i]);
        int sum = d2 + carry;
        int output_digit = sum%10;
        carry = sum/10;

        result.push_back(digitToChar(output_digit));
    }

    // IF a carry is generated
    if(carry){
        result.push_back('1');
    }

    // Reverse the final result
    reverse(result.begin(), result.end());
    return result;

}

int main(){
    string s1, s2;
    cin >> s1 >> s2;
    string result = addNumbers(s1, s2);
}
```

## Large Fatorial
Given a integer, find its factorial which may be large and may not fit into integer
* Input: 100
* Output: 932131232103981583758502342304932487234237482374082304923047378437824723483402387423084723808324

```c++

void multiply(vector<int> &a, int no, int &size){
    itn carry = 0;
    for(int i=0; i<size; i++){
        int product = a[i] * no + carry;
        a[i] = product%10;
        carry = product/10;
    }

    // Handling the carry
    while(carry){
        a[size] = carry%10;
        carry = carry/10;
        size++;
    }
}

void bigFactorial(int n){

    vector<int> a(1000,0);
    a[0] = 1;
    int size = 1;

    for(int i=2; i<=n; i++){
        multiply(a, i, size);
    }
    //Print result in the reverse order
    // size-1 to 0
    for(int i=size-1; i>=0; i--){
        cout << a[i];
    }
}

int main(){
    int n;
    cin >> n;
    bigFactorial(n);

    return 0;
}
```