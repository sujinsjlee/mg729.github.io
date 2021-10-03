---
layout: post
title: OS - process and thread
description: "Understanding concept of process and thread"
modified: 2021-09-30
tags: [OperatingSystem]
categories: [OperatingSystem]
---


## Process
> **Process** : A program in execution


- A process includes
    - text section (program code itself)
    - stack/data/heap
    - prgram counter (PC)
    - CPU register contents
    - PCB(Process Control Block)


<!--  “컴퓨터에서 연속적으로 실행되고 있는 컴퓨터 프로그램”
메모리에 올라와 실행되고 있는 프로그램의 인스턴스(독립적인 개체)

운영체제로부터 시스템 자원을 할당받는 작업의 단위
즉, 동적인 개념으로는 실행된 프로그램을 의미한다.
참고 할당받는 시스템 자원의 예
CPU 시간
운영되기 위해 필요한 주소 공간
Code, Data, Stack, Heap의 구조로 되어 있는 독립된 메모리 영역
프로세스는 각각 독립된 메모리 영역(Code, Data, Stack, Heap의 구조)을 할당받는다.
기본적으로 프로세스당 최소 1개의 스레드(메인 스레드)를 가지고 있다.
각 프로세스는 별도의 주소 공간에서 실행되며, 한 프로세스는 다른 프로세스의 변수나 자료구조에 접근할 수 없다.
한 프로세스가 다른 프로세스의 자원에 접근하려면 프로세스 간의 통신(IPC, inter-process communication)을 사용해야 한다.
Ex. 파이프, 파일, 소켓 등을 이용한 통신 방법 이용  -->



- An instance of a program that is loaded into memory and running (independent object)

- A unit of work in which system resources are allocated from the operating system.
    - That is, as a dynamic concept, it means an executed program.
    - Examples of allocated system resources
        - CPU time
        - Address space required to operate
        - Independent memory area in the structure of Code, Data, Stack, and Heap
- Each process is allocated an independent memory area (structure of Code, Data, Stack, and Heap).
- By default, each process has at least one thread (the main thread).
- Each process runs in a separate address space, and one process cannot access the variables or data structures of another process.
- In order for one process to access the resources of another process, inter-process communication (IPC) must be used.
    - Ex. Using communication methods using pipes, files, sockets, etc.

## Thread

<!-- **Thread** : 프로세스 내에서 실행되는 여러 흐름의 단위
스레드는 프로세스 내에서 각각 Stack만 따로 할당받고 Code, Data, Heap 영역은 공유한다.
스레드는 한 프로세스 내에서 동작되는 여러 실행의 흐름으로, 프로세스 내의 주소 공간이나 자원들(힙 공간 등)을 같은 프로세스 내에 스레드끼리 공유하면서 실행된다.
같은 프로세스 안에 있는 여러 스레드들은 같은 힙 공간을 공유한다. 반면에 프로세스는 다른 프로세스의 메모리에 직접 접근할 수 없다.
각각의 스레드는 별도의 레지스터와 스택을 갖고 있지만, 힙 메모리는 서로 읽고 쓸 수 있다.
한 스레드가 프로세스 자원을 변경하면, 다른 이웃 스레드(sibling thread)도 그 변경 결과를 즉시 볼 수 있다.-->

> **Thread** : A unit of multiple flows running within a process.


- Threads are allocated a separate stack within each process, and the code, data, and heap areas are shared.
- A thread is a flow of execution that operates within one process, and is executed while sharing the address space or resources (heap space, etc.) within the process among the threads within the same process.
- Multiple threads in the same process share the same heap space. On the other hand, a process cannot directly access the memory of another process.
- Each thread has its own registers and stack, but the heap memory can be read from and written to each other.
- When one thread changes a process resource, other sibling threads can see the change immediately.