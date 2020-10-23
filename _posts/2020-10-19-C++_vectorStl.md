---
layout: post
title: C++ STL - vector - modifying data by operator[], erase(), insert() 
description: "C++ STL for sorting"
modified: 2020-03-30
tags: [C++]
categories: [C++]
---

# ABOUT Vector index

## vector - modify data
> **at** : access specified element with bounds checking  
> **operator[]** :  access specified element  



```c++
vector <int> v;
for(int i=1;i<=10;i++){
   v.push_back(i);
}

v.at(4) = -1;
v[4] = 77;
```
- `at` and `operator[]` both return a reference to the indexed element

-  you'd better take the habit to use `at`, less idiomatic, but bound-checking is priceless

- A much better way is to use `at(...)`. This will automatically check for out of bounds behaviour and break throwing an **std::out_of_range**.  

```c++
v.at(10) = 9;
```
- We will get:  
terminate called after throwing an instance of 'std::out_of_range'
what(): vector::_M_range_check: __n (which is 10) >= this->size() (which is 4)

<!--
- `at()` 을 쓰는게 좋겠네요. code test 에서 vector로 컨테이너 구현하고 [] 인덱스 접근했더니 시간초과 에러났었음. 앞으로 `at()`을 쓰도록 합시다  
-->

## vector - erase : erase data

```c++
vector <int> v;
for(int i=1;i<=10;i++){
   v.push_back(i);
}

int count = 0;
for(vector<int>::iterator it = v.begin(); it != v.end(); it++){
    if(count == 5){ // in case of the index is 5 --> data will be erased
        it = v.erase(it);
        break;
    }else{
        count++;
    }
}
```


## vector - insert : insert data

```c++
vector <int> v;
for(int i=1;i<=10;i++){
   v.push_back(i);
}

int count = 0;
for(std::vector<int>::iterator it = v.begin(); it != v.end(); it++){
    if(count == 5){// in case of the index is 5 --> data will be inserted
        v.insert(it,6);
        break;
    }else{
        count++;
    }
}
```
