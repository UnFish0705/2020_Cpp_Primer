# CH3 Strings, Vectors, and Arrays
## Strings
Initialize a string 
```=c++
string s1
string s2(s1)
string s2 = s1
string s3("value")
string s3 = "value"
string s4(n,'c')
```
## Exercise 3.7
```=c++
For code like is >> s, input is separated by whitespaces while reading into string s.  
For code like getline(is, s) input is separated by newline \n while reading into string s. Other whitespaces are ignored.  
For code like getline(is, s, delim)input is separated by delim while reading into string s. All whitespaces are ignored.  
```
## 標準 iterator
**No operator for iter1 + iter2
```=c++
*iter
iter->mem
++iter
--iter
iter1 == iter2
iter1 != iter2
```
## Excercise 3.27
```=c++
unsigned buf_size = 1024;
int ia[buf_size];   // illegal, The dimension value must be a constant expression.
int ia[4 * 7 - 14]; // legal
int ia[txt_size()]; // illegal, The dimension value must be a constant expression.
char st[11] = "fundamental";  // illegal, the string's size is 12.(NULL)
```
## Excercise 3.35
```=c++
#include<iostream>
#include<string>
using std::cout;
using std::endl;

int main()
{
	int ia[] = { 0,1,2,3,4,5,6,7,8,9,10 };
	auto beg = std::begin(ia);
	auto end = std::end(ia);
	for (auto& i : ia)
	{
		i = 0;
	}
	cout << *beg << *(end-1) << endl;
}
```





