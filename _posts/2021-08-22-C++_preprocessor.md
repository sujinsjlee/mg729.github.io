---
layout: post
title: C++ preprocessor
description: "C++ preprocessor"
modified: 2021-08-22
tags: [C++]
categories: [C++]
---


## preprocessor 

```c++
#include<bits/stdc++.h>
using namespace std;

#define NUM 10
#define STR "String"
#define SUM(x,y) ((x) + (y)) // macro definition by #define

//#undef NUM --> you can undef preprocessor

void main()
{
  
  cout << NUM;
  cout << STR;
  cout << SUM(2,4);
  
#if NUM <40
  cout << "under 40" <<endl;
#elif NUM > 40
  cout << "exceed 40" << endl;
#else
  cout << NUM << endl;
#endif

}
```

- Code Execution
    - **Preprocessor** > Compiler > Linker > Generate Executable file
    - the preprocessor is executed before compiling

- Preprocessing statements are defined by **#**.
- Do not add a **;** semicolon at the end of the preprocessing statement.

### define
- `#define` keyword : Declare content to be used as a keyword
- Used for macro
   - When declaring macro, parentheses are processed considering operator precedence

### undef
- `#undef` : delete keywords declared with #define



```c++
#include<bits/stdc++.h>
using namespace std;

#define NUM 40

void main()
{
#ifdef NUM
  cout << NUM << "is exist" << endl;
#else 
  cout << NUM << "is not exist" << endl;
#endif
}
```

### ifdef
- `#ifdef` : if keyword is defined with `#define`, it is true


```c++
// header.h

#ifndef _TEST_H_
#define _TEST_H_
/// test code
#endif
```


### ifndef
- `#ifndef`: true if the keyword is not declared with a #define statement
   - Prevents duplicate definitions
    - avoid redefinition
    - avoid predefinition
   - EXAMPLE
    - **#ifndef _TEST_H_** : Check if the `_TEST_H_` keyword is declared
    - **#define _TEST_H_** : If there is no `_TEST_H_` keyword, define `_TEST_H_` 
    - `/// test code`
    - #endif

    - When accessing the `///test code` again later
    - Because `_TEST_H_` is already defined by the condition(**#ifndef _TEST_H_**), the define statement below is not processed.

```c++
// header.h

#pragma once
```


### pragma once
- `#pragma` command: It performs a special function according to the command.
- **Compiler dependent**
- **#pragma once** : Include this header file only once

