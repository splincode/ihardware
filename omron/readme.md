== Оригинальная документация ==

[https://github.com/openyou/libomron/edit/master/README.asciidoc](https://github.com/openyou/libomron/edit/master/README.asciidoc)


== Supported ==

_Blood Pressure Monitors_
* HEM-790-IT
* BP-791-IT
* M10-IT

_Pedometers_
* HJ-720-IT

== Library Requirements (For Compilation linux) ==

* CMake (Required on all platforms) - http://www.cmake.org
* SWIG (For non-C libraries) - http://www.swig.org
* libusb-1.0 - http://www.libusb.org

To build on Ubuntu, you can pull the following packages to build the
project from source.

* libusb-1.0-0-dev
* cmake
* cmake-data

 - git clone to ~/git/libomron # основной пакет
 - build area in ~/opt/omron-build # собранный пакет
 - install area in ~/opt/omron # файлы для установки

1) Клонируем себе репозиторий https://github.com/openyou/libomron/

 cd ~/Develop/omron/c++_modules
 git clone https://github.com/openyou/libomron/
 cd libomron

2) Подтягиваем подмодули

```bash
 git submodule update --init
```

3) Создаем директорию с установкой софта

```bash
 mkdir -p omron-build
 cd omron-build
```

4) Запускаем сборку программы

```bash
cmake ~/Develop/omron/c++_modules/libomron
```

Результат:

```bash
-- The C compiler identification is GNU 5.2.1
-- The CXX compiler identification is GNU 5.2.1
-- Check for working C compiler: /usr/bin/cc
-- Check for working C compiler: /usr/bin/cc -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /usr/bin/c++
-- Check for working CXX compiler: /usr/bin/c++ -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Installation Prefix: /usr/local
-- Building Static Libraries for LIBOMRON
-- Building Shared Libraries for LIBOMRON
-- Setting build RPATH for LIBOMRON
-- Found libusb-1.0:
--  - Includes: /usr/include
--  - Libraries: /usr/lib/x86_64-linux-gnu/libusb-1.0.so
-- Found SWIG: /usr/bin/swig2.0 (found version "2.0.12") 
-- Using SWIG!
-- Found PythonLibs: /usr/lib/x86_64-linux-gnu/libpython2.7.so (found version "2.7.10") 
-- Configuring done
-- Generating done
-- Build files have been written to: /home/splincode/Develop/omron/c++_modules/libomron/omron-build
```