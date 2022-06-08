# sauron65's C++ styleguide

## file naming
name files the name of the main class/function/namespace/struct instance. otherwise name it something in lowerCamelCase.
file should end in `.cpp` or, if they just define things like macros, `.hpp`

## variable naming
```cpp
#define MACROS_LIKE_THIS
#define CONSTANTS_LIKE_THIS 0xA0F4
const unsigned short OR_THIS {512};

int variablesLikeThis {17};

void functionsLikeThisWithPrototypesOnlyWhenNessasary(int &value) {
  value *= 8;
}

class ClassesLikeThis {
  public:
    int a;
    int b;
    ClassesLikeThis(int a): a {a}, b {17} {}
};
/*
don't define methods and constructors after class definition except when needed.
*/
```
