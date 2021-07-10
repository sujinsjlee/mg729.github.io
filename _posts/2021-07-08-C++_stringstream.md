---
title: "C++ - stringstream"
categories:
  - C++
tags:
  - C++
---

## std::basic_stringstream

> [std::basic_stringstream](https://en.cppreference.com/w/cpp/io/basic_stringstream)


- The class template **std::basic_stringstream** implements input and output operations on string based streams. It effectively stores an instance of std::basic_string and performs the input and output operations on it.

- In C++, **stringstream** is useful when retrieving suitable information for the required data type from a given string. Extracts information of data types that match a string except for spaces and '\n' from stringstream.



- Example

```c++
#include <iostream>
#include <iomanip>
#include <sstream>
 
int main()
{
    std::string input = "41 3.14 false hello world";
    std::istringstream stream(input);
    int n;
    double f;
    bool b;
 
    stream >> n >> f >> std::boolalpha >> b;
    std::cout << "n = " << n << '\n'
              << "f = " << f << '\n'
              << "b = " << std::boolalpha << b << '\n';
 
    // extract the rest using the streambuf overload
    stream >> std::cout.rdbuf();
    std::cout << '\n';
}
```

- Output
n = 41  
f = 3.14  
b = false  
hello world  