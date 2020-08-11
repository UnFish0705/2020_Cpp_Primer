# Expressions
## Excercise 4.35
```=c++
char cval; int ival; unsigned int ui; float fval; double dval;
cval = 'a' + 3; // 'a' promoted to int, then the result of ('a' + 3)(int) converted to char.
fval = ui - ival * 1.0; // ival converted to double , ui also converted to double. then that double converted(by truncation) to float.
dval = ui * fval; // ui promoted to float. then that float converted to double.
cval = ival + fval + dval;  // ival converted to float, then that float and fval converted to double. At last, that double converted to char(by truncation).
```
## Named cast
cast-name<type>(expression)  
static_cast：用於較大的算術型別被指定給一個較小型別  
const_cast：從const強制轉離(casts away the const)  
reinterpret_cast：對其運算元bit pattern進行低階的重新解讀  
## Excercise 4.37
```=c++
int i; double d; const string *ps; char *pc; void *pv;
pv = (void*)ps; // pv = const_cast<string*>(ps); or pv = static_cast<void*>(const_cast<string*>(ps));
i = int(*pc);   // i = static_cast<int>(*pc);
pv = &d;        // pv = static_cast<void*>(&d);
pc = (char*)pv; // pc = static_cast<char*>(pv);
```

