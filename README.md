
Tiny Web Server
====
[English](./README-EN.md) [简体中文](./README-CN.md)

Overview
----
A tiny multithreaded web server using C++ in Linux.

Features
----
- Threadpool + epoll + Reactor
- Realize basic function like register, login, etc when access the server.
- Accept HTTP requests including GET and POST.
- Timer to provide a connection close on inactivity timeout. 
- Database Connection Pool.

Requirements
----
- Linux for server
- Linux or Windows for client
- g++
- mysql
- Browser like Chrome, Firefox, etc.

Quick Start
----
- All my test is based on g++ (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.0 and mysql Ver 14.14 Distrib 5.7.30. 
- Create your database
    ```C++
    create database yourdb;
    USE yourdb;
    CREATE TABLE user(
        username char(50) NULL,
        passwd char(50) NULL
    )ENGINE=InnoDB;

    INSERT INTO user(username, passwd) VALUES('name', 'passwd');
    ```
- Change the info in `main.cpp`
    ```C++
    string user = "root";
    string passwd = "root";
    string databasename = "yourdb";
    ```
- Build projects

    ```C++
    sh ./build.sh
    ```
- Start the server

    ```C++
    ./server
    ```
- Direct your favorite browser to for instance http://localhost:9006/

- More options

```C++
./server [-p port] [-v SQLVerify] [-l LOGWrite] [-m TRIGMode] [-o OPT_LINGER] [-s sql_num] [-t thread_num] [-c close_log] [-a actor_model]
```


References
----
Refer to Shuang You, High Performance Linux Server Programming.
