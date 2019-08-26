# deepstream-server
DSS is an Embedded REST Services Application for the NVIDA Jetson Platform. DSS is written in C++ 11 and built on the following SDK's.

* [DeepStream](https://developer.nvidia.com/deepstream-sdk)
* [NVIDIA Container Runtime]
* [Pistache](https://github.com/oktal/pistache) - A high-performance REST Toolkit written in C++

    <iframe width="560" height="315"
src="https://www.youtube.com/embed/MUQfKFzIOeU" 
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>


## Installing Dependencies

### Documentation Dependecies
Doxygen is used/required for source documentation and is generated by invoking `make` with the `dox` opetion
```
$ make dox
```
#### Installing dot by graphviz;
Doxygen requires **dot** to convert calling graphs to .png files
```
sudo apt-get install graphviz imagemagick
```
#### Installing Doxygen
To install Doxygen on Ubuntu
```
$ sudo apt-get install doxygen
```

### Logging Dependencies
The active Logging implementation is controlled by the `-DDSS_LOG_IMP` define, set in the `\on-target\MakeFile`. With the current setting of `DDSS_LOG_IMP=dss_log4cxx.h` you will need to install the below Apache packages. 

Libs`-llog4cxx -laprutil-1 -lapr-1`are required to build with `dss_log4cxx.h/cpp`

#### Installing the Apache Portable Runtime (APR)
Installing APR and APR util
```
sudo apt-get install apache2-dev libapr1-dev libaprutil1-dev
```
#### Installing Apache log4cxx
Clone or download the (TBD)
Source pulled from log4cxx-0.10.0 [trunk]( http://svn.apache.org/repos/asf/incubator/log4cxx/trunk)
```
$ cd apache-log4cxx-0.10.0
$ ./configure --build=x86_64-unknown-linux-gnu
$ make
$ make check
$ sudo make install
```
