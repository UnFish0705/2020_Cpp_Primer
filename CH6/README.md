# Functions
## Exercise 6.1
Arguments:Local variable declared inside the function parameter list. they are initialized by the arguments provided in the each function call.  
Parameters:Values supplied in a function call that are used to initialize the function's parameters.  
## Excercise 6.13
void f(T) pass the argument by value. nothing the function does to the parameter can affect the argument.   
void f(T&) pass a reference, will be bound to whatever T object we pass.  
## Excercise 6.16
```=c++
bool is_empty(const string& s) { return s.empty(); }
```
## Excercise 6.27
```=c++
#include<iostream>
#include<string>
#include<initializer_list>
using namespace std;

int sum(initializer_list<int> const &list)
{
	auto sum = 0;
	for (auto i : list)
	{
		sum += i;
	}
	return sum;
}
int main()
{
	auto ia = { 0,1,2,3,4,5,6,7,8,9,10 };
	auto result = sum(ia);
	cout << result << endl;
}
```
## Excercise 6.32
```=c++
int &get(int *arry, int index) {return arry[index];}
int main()
{
  int ia[10];
  for(int i = 0; i != 10; ++i)
    get(ia, i) = i;
}
```
## Excercise 6.36 ~ 6.38
```=c++
// Re-check, P.228~
```
## Excercise 6.54
