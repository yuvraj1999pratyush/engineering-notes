### User Input / Output

In C++, the `#include` directive is used to import libraries that provide predefined functions and classes.

```cpp
#include <iostream>
#include <math.h>
#include <string>
```

`cout` is used to print output in C++ and it comes under `std` library.

```cpp
#include<iostream>

int main(){
    std::cout << "Hey Yuvraj!" << std::endl << "Hey Pratyush!" << "/n";
    std::cout << "Wassup";
    return 0;
}
```

`endl` and `/n` takes the output to next line.

In the above code we can ignore writing std everytime instead we can just use it as import and then use its supporting functions normally. (Example code below)

```cpp
#include<iostream>
using namespace std;

int main(){
    cout << "Hey Yuvraj!" << endl << "Hey Pratyush!" << "/n";
    cout << "Wassup";
    return 0;
}
```

`cin` is used take user input, it also comes under `std` library

```cpp
#include<iostream>
using namespace std;

int main(){
    int x, y;
    cin >> x >> y;
    count<< "Value of x: " << x << "and y: "<< y;
    return 0;
}
```

`bits/stdc++.h` is used to import sall necessary libraries at once instead of importing them one.

Example: `#include<bits/stdc++.h>`

---

### Data Types

Common data types in C++:

- `int` : Have **4 byte** of memory and range is **-2147483648** to **2147483647**
- `long` : Have **4 byte** of memory and range is **-2147483648** to **2147483647**
- `long long` : Have **8 byte** of memory and range is **-9223372036854775808** to **9223372036854775807**
- `float` : Have **4 byte** of memory and range is **1.2E-38** to **3.4E+38**. Used to store decimal values.
- `double` : Have **10 byte** of memory and range is **2.3E-308** to **1.7E+308**. Used to store decimal values.
- `string`
- `bool`
- `char`

To print everyline in a string which is a whitespace separated sentence we can use `getLine()`. In this next line is not picked up. Only sentence in a single line is picked up.

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    string str;
    getline(cin, str); //prints whole line
    cout << str;
    return 0;
}
```

---

### Conditional Statements

#### if-else

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    int a = 3
    if(a > 0) {
        // do something 1
    }else if(a > 1) {
        // do something 2
    }else {
        // do something 3
    }
}
```

#### nested if-else

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    int a = 3
    if(a > 0) {
        // do something 1
    }else if(a > 1) {
        if (a < 10){
            //do something 2
        }else {
            // do something 3
        }
    }else {
        // do something 4
    }
}
```

#### switch statement

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    int day = 3;
    switch(day){
        case 1;
            // do somthing 1
            break;
        case 2:
            // do somthing 2
            break;
        case 3:
            // do somthing 3
            break;
        default:
            // do something 4
    }
}
```

---

### Arrays

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    // an array of length 5 (all elements will be of type int)
    int arrOne[5];

    // accessing array elements
    cin >> arrOne[0] >> arrOne[1] >> arrOne[2];
    cout << arrOne[1];

    for (int i = 0; i < arrOne.size(); i++){
        cout << arrOne[i] << " ";
    }

    // an array of length 20 (all elements will be of type long long)
    long long arrTwo[20];

    // initializing an array
    int arrThree[6] = {2, 4, 8, 12, 16, -9};


    // size can be skipped
    int arrFour[] = {2, 4, 8, 12, 16};

    // all the elements are initialized to -1
    int arrFive[100] = {-1};

    //2D arrays
    int matrix[8][10];

    matrix[1][3] = 24;
    cout<< matrix[1][3] << endl;

    return 0;
}
```

The entire array is stored in a memory location. The memory index its is stored at is pointed to 1st element of the array. Array elements from next indexes are stored in consecutive memory locations (not in random).

---

### Strings

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    String str = "abcde";
    int len = str.length();

    cout << str[0] << " " << len << endl;

    str[len-1] = 'z';

    cout << str[len-1];
}
```

---

### Loops

#### for loop

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    // print a number from 1 - 5
    for(int i = 0; i < 5 ; i++){
        cout << i+1 << endl;
    }
}
```

#### while loop

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    // print a number from 1 - 5
    int i = 0;
    while(i < 5){
        cout << i+1 << endl;
        i++;
    }
}
```

#### do-while loop

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    // print a number from 1 - 5

    /* this loop is used if we want to run the
    loop minimum of one time because it runs
    first and then checks the condition */

    int i = 0;
    do {
        cout << i+1 << endl;
        i++;
    }while(i < 4);
}
```

---

### Functions

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    printName();

    string name;
    cin >> name;
    printCustomName(name);

    int a = 5;
    int b = 6;
    int res = sum(a, b);
    cout << res << "/n";
}

//non-parameterised
//void function
void printName(){
    cout << "Hey Yuvraj" << endl;
}

//parameterised
//void function
void printCustomName(string name){
    cout << "Hey " << name << endl;
}

//parameterised
//a function having a return type: int
int sum(int a, int b){
    return a+b;
}
```

`pass by value`: It means if we define a variable and pass it to a function then the `copy` of the variable is passed and not the origianl variable or its memory address itself.

`pass by reference`: It means that instead of a copy we pass the original variable and its memory address to a function. If the function manipulates the variable the the variable defined will be manipulated as well;

#### example

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
   String str = "taj";
   cout << str << endl; //output: taj

   //pass by value
   manipulateName1(str);
   cout << str << endl; //output: taj

   //pass by reference
   manipulateName2(str)
   cout << str << endl; //output: zaj
}

void manipulateName1(String str){
    str[0]="z";
    str[1]="a";
}

void manipulateName2(String &str){
    str[0]="z";
    str[1]="a";
}
```

Arrays is by **default pass by reference**, i.e. if we pass array to a function and manipulate its element the original array will get manipulate too. No need to use `&` sign inside function call.

---

### Standard Template Library (STL) in C++

STL is a collection of pre-built classes and functions that make it easy to manage data using common data structures like vectors, stacks, and maps. It saves time and effort by providing ready-to-use, efficient algorithms and containers.

Containers are the data structures used to store objects and data according to the requirement. Containers can be further classified into 4 types:

- Sequence Containers : Vector, Deque, List, Forward List, Array
- Container Adaptors : Stack, Queue, Priority Queue
- Associative Containers : Set, Multiset, Map, Multimap
- Unordered Associated Containers : Unordered Set, Unordered Multiset, Unordered Map, Unordered Multimap

#### Pair

`Pair` is a simple container that holds two values together. It lies in the `utility` library. These two values can be of different types, and they are stored as a single unit.

```cpp
#include <iostream>
#include <utility>
using namespace std;

int main()
{

    // Creating a pair of int and string
    pair<int, string> p1 = {1, "Geeks"};

    cout << p1.first << ": " << p1.second;
    return 0;
}
```

#### Vectors

A vector represents a dynamic sized array in the Standard Template Library(STL) that automatically grows when elements are added beyond current capacity.

```cpp
#include <iostream>
#include <utility>
using namespace std;

int main()
{
    // different tways to initialize a vector
    vector<int> v;
    vector<int> v2 = {10, 20, 30, 40};

    // inserting at back
    v.push_back(1);

    // inserting at the back
    v.emblace_back(2);

    // deleting element from the back
    v.pop_back();

    // inserting at given index
  	v.insert(v.begin() + 1, 3);

    vector<pair<int,int>> vec;
    vec.push_back({1,2});
    vec.emblace_back({2,5});

    // initialize a vector of size 5
    vector<int> v3(5);

    // initialize a vector of size 5 all having 100 as default values
    vector<int> v4(5,20);

    // accessing of elements
    cout << "Element at index 2 using []: " << v4[2] << endl;

    // copying a vectore
    vector<int> v5(v4);
}
```

#### Iterators

An iterator is an object that behaves like a pointer to traverse and access elements of a container.

```cpp
#include<bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> v  = {10, 20, 30, 40, 80, 100};

    //points to memory address of first element of vector
    vector<int>::iterator it = v.begin();

    it++;
    //* will access element at that memory location directly
    cout<< *(it) << endl;

    it = it + 2;
    cout<< *(it) << endl;

    //iterating through vectors
    for(vector<int>::iterator it = v.begin(); i!=v.end(); i++){
        cout << *(it) << " ";
    }

    for(auto it = v.begin(); i!=v.end(); i++){
        cout << *(it) << " ";
    }

    for(auto ele: v){
        cout << ele << " ";
    }

    return 0;
}
```

`v.end()` doesn't point to last element but a memory location just after last pointer. To access last element we will use have to decrement iterator by 1, `it--`.

In C++ if we don't know the data type or want ot assign a variable to a data type we can just use `auto` keyword.

**Example**:
`auto a = "abc";`

#### Other useful vector operations

```cpp
#include<bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> v  = {10, 20, 30, 40};

    //deleting from a vector
    v.erase(v.begin()+1); // {10, 30, 40}
    v.erase(v.begin()+1, v.begin()+3); // {10}


    //inserting to a vector
    // {10}
    v.insert(v.begin(), 300); // {300, 10}
    v.insert(v.begin() + 1, 3, 20); // {300, 20, 20, 20, 10}

    vector<int> copy(2, 50); // {50, 50}
    v.insert(v.begin(), copy.begin(), copy.end()); // {50, 50, 300, 20, 20, 20, 10}

    // v1 = {10, 30};
    // v2 = {40, 50};
    // swaps v1 and v2
    v1.swap(v2);

    // erases the entire vector
    v.clear();

    // checks if vector is empty
    cout << v.empty();

    return 0;
}
```

#### Lists

A list in C++ is a sequence container that allows you to store elements one after another.

- Implemented as a doubly linked list and maintains both front and back for fast operations on both the ends.
- Data is stored in non-contiguous memory, allowing fast insertion and deletion anywhere in the list (beginning, middle, or end).

```cpp
#include<bits/stdc++.h>
using namespace std;

int main()
{
    list<int> ls;

    //add element at the end of the list
    ls.push_back(3); // {3}
    ls.emblace_back(4); // {3, 4}

    //add element at the beginning of the list
    ls.push_front(11); // {11, 3, 4}
    ls.emblace_front(12); // {12, 11, 3, 4}

    //rest functions are same as vector
    //begin, end, clear, ebegin, rend, insert, size, swap

    return 0;
}
```

#### Deque

```cpp
#include<bits/stdc++.h>
using namespace std;

int main()
{
    deque<int> dq;

    //add element at the end of the deque
    dq.push_back(3); // {3}
    dq.emblace_back(4); // {3, 4}

    //add element at the beginning of the deque
    dq.push_front(11); // {11, 3, 4}
    dq.emblace_front(12); // {12, 11, 3, 4}

    dq.pop_back(); // {12, 11, 3}
    dq.pop_front(); // {11, 3}

    dq.back();
    dq.front();

    //rest functions are same as list and vector
    //begin, end, clear, ebegin, rend, insert, size, swap

    return 0;
}
```

#### Stack

Stack container follows LIFO (Last In First Out) order of insertion and deletion. It means that most recently inserted element is removed first and the first inserted element will be removed last.
Stack is defined as **std::stack** class template inside the `<stack>` header file.

```cpp
#include <iostream>
#include <stack>
using namespace std;
int main()
{
    stack<int> st;
    st.push(10);
    st.push(5);

    // Accessing top element
    cout << "Top element: " << st.top() << endl;

    // Popping an element
    st.pop();
    cout << "Top element after pop: " << st.top() << endl;
    return 0;

    cout << st.size();
    cout << st.empty();

    return 0;
}
```

#### Queue

A queue is a container adapter that stores elements in FIFO (First In, First Out) order.

- The elements that are inserted first should be removed first.
- This is possible by inserting elements at one end (called back) and deleting them from the other end (called front) of the data structure.

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    queue<int> q;
    q.push(10);
    q.push(5);

    // Accessing the front and back elements
    cout << "Front element: " << q.front() << endl;
    cout << "Back element: " << q.back() << endl;

    // Removing an element from the front
    q.pop();

    cout << "Front element after pop: " << q.front() << endl;
    return 0;
}
```

#### Priority Queue

A Priority Queue adds and removes elements according to priority.

- Internally uses heap data structure.
- Uses a max heap by default, higher its value, higher its priority. But this can be changed to any desired priority scheme by providing a custom comparison.

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    // Create a max-heap priority queue (default) (descending order)
    priority_queue<int> pq;

    // Insert elements
    pq.push(30);
    pq.push(10);
    pq.push(20);
    pq.push(40);

    // Accessing top (which is also largest) element
    cout << pq.top();

    cout << "Elements removed from priority queue in order:\n";

    // Remove elements (largest element comes out first)
    while (!pq.empty())
    {
        cout << pq.top() << " ";
        pq.pop();
    }

    // minimum heap
    // this priority queue stores smallest element at top (ascending order)
    priority_queue<int,vector<int>,greater<int>> pq2;

    return 0;
}
```

#### Set

A Set is a container which stores unique elements in some sorted order. It is an implementation of a Self-Balancing Binary Search Tree, specifically a Red-Black Tree which ensures, Search, insert, and delete in `O(log n)` time.

- Does not allow duplicates.
- Elements are always sorted in ascending order by default. You can also choose your own way of ordering them using a custom rule (comparator).

**Multiset**: Multiset is an associative container similar to the set, but it can store multiple elements with same value. It is sorted in increasing order by default, but it can be changed to any desired order using custom comparator. Eg: `multiset<int> ms;`

**Unordered Set**: In C++, unordered_set is an unordered associative container that stores unique elements. Internally uses a hashing to store elements which provides average constant time O(1) for insert, search and delete operations. Elements have no particular order and are best used when fast access is more important than sorted order. Eg: `unordered_set<int> us;`

```cpp
#include <iostream>
#include <set>
using namespace std;

int main() {
    set<int> st;
    st.insert(1); // {1}
    st.insert(2); // {1, 2}
    st.insert(2); // {1, 2}
    st.insert(3); // {1, 2, 3}

    auto it = st.find(3);

    //takes logarithmic time
    st.erase(2);

    return 0;
}
```

#### Map

Maps are associative containers that store data as sorted pairs of keys and values. It is an implementation of Self-Balancing Binary Search Tree, specifically a Red-Black Tree Which ensures,

- Maps allow searching, insertion, and deletion and take O(log n) time.
- Maps automatically avoid duplicate keys.
- Keys are stored in ascending order.

**Multimap**: Multimap is an associative container similar to map, but it can have multiple elements with same keys. It stores all the elements in increasing order based on their keys by default but can be changed if required. Eg: `multimap<key_type, value_type, comp> mm;`

**Unordered Map**: `unordered_map` is an unordered associative container that stores data in the form of unique key-value pairs. But unlike map, unordered map stores its elements using hashing. This provides average constant-time complexity `O(1)` for search, insert, and delete operations but the elements are not sorted in any particular order. Eg: `unordered_map<key_type, value_type> um;`

```cpp
#include <iostream>
#include <set>
using namespace std;

int main() {
    //definition
    map<int, string> mp1;
    map<int, pair<int, int>> mp2;

    //insertion
    mp1[1]="abc";
    mp2[3]={1,1};

    mp1.emblace({2, "def"});
    mp2.insert({3, {8,9}});

    //looping
    for(auto it : mp1){
        cout << it.first << " " << it.second << endl;
    }

    return 0;
}
```

---

### Common STL Algorithms

- sort
-

```cpp
#include <iostream>
#include <set>
using namespace std;

int main() {
   //common use of sort
   // a is array, v is vector
   sort(a, a + n);
   sort(v.begin(), v.end());
   sort(a+2, a+4);

   // sorting with a comparator  (sorting in descending order)
   // we can write a self written comparator as well its just that comparator's return type is always boolean
   sort(v.begin(), v.end(), greater<int>)

   /*
    Q.Write a custom comprarator function which sort a vector of pairs such that
    sort according to second element
    if second element is same then sort according to first element but in descending
   */
   vector<pair<int, int>> vec = {{1,2}, {2,1}, {4,1}};
   sort(vec.begin(), vec.end(), comp)
   // output: {{4,1}, {2,1}, {1,2}}

   return 0;
}

bool comp(pair<int, int> p1, pair<int, int> p2){
    if(p1.second < p2.second){
        return true;
    }else if(p1.second > p2.second){
        return false;
    }else{
        if(p1.first > p2.first){
            return true;
        }else{
            return false;
        }
    }
}
```
