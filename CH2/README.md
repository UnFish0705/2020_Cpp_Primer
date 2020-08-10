# CH2 Variable and Basic data types
## Excercise 2.10
global v.s. local
```=c++
std::string global_str; // empty string
int global_int; // 0
int main()
{
    int local_int; // undefined
    std::string local_str; //undefined
}
```
## Excercise 2.11
宣告 v.s. 定義  
宣告：讓程式得知某個名稱  
定義：創建關聯的實體  
```=c++
extern int ix = 1051; //定義
int iy; //定義
extern int iz; //宣告
```
## Statically typed
compile time 進行型別(type)檢查  
## Excercise 2.15
```=c++
int ival = 1.01;
int &rval2 = ival;
int &rval1 = 1.01; //invalid, & needs to "bind" an object
```
## NULL & nullptr
```=c++
void func(int x);  // 1
void func(int* x); // 2
//如果 x = NULL會call到 1
//如果 x = nullptr會call到 2
```
## Excercise 2.27
```=c++
int i = -1, &r = 0;         // illegal, r must refer to an object.
int *const p2 = &i2;        // legal.
const int i = -1, &r = 0;   // legal.  //const可以bind到字面值!!!!
const int *const p3 = &i2;  // legal.
const int *p1 = &i2;        // legal
const int &const r2;        // illegal, r2 is a reference that cannot be const.
const int i2 = i, &r = i;   // legal.
```
## top-level const & low-level const
**在複製時top-level const會被忽略, 有相同low-level才能進行轉換**   
top-level const: pointer本身是一個const(自身是const)  
low-level const: 當pointer能夠指向一個const object.就稱為low-level(所指對象是const)  
## Excercise 2.30
**const int ci = 42; //const 屬於top-level!!**
```=c++
const int v2 = 0; int v1 = v2;      //v2 top-level
int *p1 = &v1, &r1 = v1;            
const int *p2 = &v2, *const p3 = &i, &r2 = v2;  //p2 is low-level const. p3 is both low-level and top-level const. r2 is low-level const.
```
## Excercise 2.31
```=c++
r1 = v2; // legal, top-level const in v2 is ignored.
p1 = p2; // illegal, p2 has a low-level const but p1 doesn't.
p2 = p1; // legal, we can convert int* to const int*.
p1 = p3; // illegal, p3 has a low-level const but p1 doesn't.
p2 = p3; // legal, p2 has the same low-level const qualification as p3.
```
## Using
namespace 使用  
alias declaration  
在child class使用parent class的function(or value)  
## type alias
```=c++
typedef char *pstring;
const pstring cstr = 0; //cstr is a const pointer points to char 
const pstring *ps; // ps指標指向對char的一個常數指標
```
## auto
通常忽略 top-level const  
## decltype
不忽略 top-level const
dereference 過後推導出的型別是int&  
```=c++
decltype((i)) d; //錯誤, d是int&
decltype(i) e; //e是int
```

