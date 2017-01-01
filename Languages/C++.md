# C++
### Structs and Classes
```C++
struct Coord {
    int x,y;
};
Coord a; // struct is allocated on the run-time STACK
a.x = 3; 
Coord* p; // dynamic instantiation of struct through pointer, on the HEAP.
p->x = 4; // pointer attribute
delete p; // will persist until explicitly deleted
```
### Templates
C++ *templates* are the C++ language mechanism that can be used to implement *generic* functions and classes. Templates are expanded at compile-time. Vector<int> is an example where vector the defined container for any generic type. The Standard Template Library (STL) provides containers, algorithms, iterators and enables functional programming.

#### Function Template
```C++
template<class type> ret-type func-name(parameter list){
    //body
}
```

Type generic swap function:

```C++
template <typename T>
void mySwap(T &x, T &y){
    const T temp = x;
    x=y;
    y=temp;
}
```

#### Class Template
```C++
template<typename type> 
class class-name {
    // class content
};
```

### Vectors
```C++
string v;
vector<string> s1;
s1.push_back("alpha"); // puts element at the end
s1.pop_back(v); // deletes last element, assigns to string v (optional)
s1.insert("beta"); // inserts element
```

### C++ map
`map` data type implements the idea of a dictionary. `map`, `multipmap`, `set`, `multiset` are ordered containers. 

`map<T1, T2> m;`, 
- where T1 is the *key field* which must support the `<` operator (therefore it must be a *strict weak ordering*, anti-reflexive, anti-symmetric, transitive) 
- T2 is the *value field*, can be anything

```C++
//records number of times each word appears
map<string, int> m;
string token;
while(cin >> token){
    m[token]++;
}
m.erase("the"); // deletes a key
```

C++11 added unsorted versions, `unordered_map, unordered_multimap`...

### Iterators
A fundamental design pattern, for iterating through a data structure. 

If `c` is a `vector, deque, list, set, etc...` then 
- `c.begin` returns ptr to first
- `c.end` returns ptr to *one beyond the last element*
    - so that you can say `while(i != c.end)`
- `++` is defined to iterate to next element, given a ptr
- `c.rbegin` returns ptr to last
- `c.rend` returns ptr to *one before the first element*

```C++
vector<string>::const_iterator   vi = v.begin;
map<int, string>::iterator       mi = mymap.begin();
list<Figure*>::reverse_iterator  li = scene.rbegin();
\  This is the type, iterator /
```

Application using for loop:

```C++
for(map<string, int>::const_iterator i = m.begin(); i != m.end(); i++) {
    cout << i->first << i->second << endl; // first is key, second is val
}
```

### Algorithms
`f(iter1, iter2, arg1, arg2)`
- `find`
- `count`
- `for_each`
- `next_permutation`

### Reference parameters
Regular parameter passing is call-by-value. C++ can pass a reference without passing a pointer itself:
```C++
void swap(int& x, int& y);
```
Reference Parameters vs. Pointers
```C++
// Common usage
void GiveRaise1 (Employee e, int raise) {} // created on stack
void GiveRaise3 (Employee &e, int &raise) {} // references to objects, changes propagate back
void GiveRaise4 (const Employee &e) {} // e references a constant object

// Uncommon
void GiveRaise2 (const Employee e, const int raise) {} // created on stack, may not be changed
void GiveRaise5 (Employee *e) {} // pointer to employee obj, copy of a pointer on the stack
void GiveRaise6 (const Employee *e) {} // pointer to const Employee
void GiveRaise7 (Employee *const e) {} // pointer can't point to new obj, Employee can be changed
void GiveRaise8 (const Employee *const e) {} // const pointer to const obj
```

### Dynamic Arrays, `new`
Statically

```C++
const int N = 5;
int A[N]; // legal
int m; cin >> m;
int B[m]; // illegal, size is not known at compile time
```
    
Dynamically (C++ Only) using `new`

```C++
cin >> N;
int * A = new int[N];
```

### Object-Oriented Programming
```C++
Balloon b;
Balloon *pb = new Balloon;
class Balloon : public ParentClass{     // class declaration, with parent, in .h file
    public:
        Balloon(); // constructor
        Balloon(string colour); // constructor with parameter
        Balloon(const Balloon & b); // Copy constructor, overrides how obj is copied
        virtual ~Balloon();     // allows for redefinition in derived classes
        virtual speak() const = 0;
        string getColour() const ; // constant method, cannot change object
        void setColour(string c);
        static balloon_counter; // class variable
    private:
        string colour;
};
// Method definitions, in .cc file
Balloon::Balloon () {
    this->colour = “clear”;
}
Balloon::Balloon (string colour){
    this->colour = colour;
}
Balloon::Balloon(string colour) : ParentClass(), colour(colour) {}     
// shorthand syntax, stops double instantiation of object parameters, calls parent constructor

Balloon::~Balloon (){
    cerr << "Deleted!";
}     // destructor
```

**Rule of 3** states that for the copy ctor, dtor, or `=` operator, if any need to be manually implemented, then all 3 should be overridden.

