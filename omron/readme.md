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

```bash
 cd ~/Develop/omron/c++_modules
 git clone https://github.com/openyou/libomron/
 cd libomron
```

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

5) Комплилируем программу

```bash
make DESTDIR=~/Develop/omron/ install
```

Результат

```bash
Scanning dependencies of target omron_SHARED
[  6%] Building C object src/CMakeFiles/omron_SHARED.dir/omron.c.o
[ 12%] Building C object src/CMakeFiles/omron_SHARED.dir/omron_libusb.c.o
[ 18%] Linking C shared library ../lib/libomron.so
[ 18%] Built target omron_SHARED
Scanning dependencies of target omron_STATIC
[ 25%] Building C object src/CMakeFiles/omron_STATIC.dir/omron.c.o
[ 31%] Building C object src/CMakeFiles/omron_STATIC.dir/omron_libusb.c.o
[ 37%] Linking C static library ../lib/libomron.a
[ 37%] Built target omron_STATIC
Scanning dependencies of target omron_DEPEND
[ 37%] Built target omron_DEPEND
Scanning dependencies of target omron_720IT_csv_dump
[ 43%] Building C object examples/CMakeFiles/omron_720IT_csv_dump.dir/omron_720IT_test/omron_720IT_csv_dump.c.o
[ 50%] Linking C executable ../bin/omron_720IT_csv_dump
[ 50%] Built target omron_720IT_csv_dump
Scanning dependencies of target omron_720IT_test
[ 56%] Building C object examples/CMakeFiles/omron_720IT_test.dir/omron_720IT_test/omron_720IT_test.c.o
[ 62%] Linking C executable ../bin/omron_720IT_test
[ 62%] Built target omron_720IT_test
Scanning dependencies of target omron_790IT_test
[ 68%] Building C object examples/CMakeFiles/omron_790IT_test.dir/omron_790IT_test/omron_790IT_test.c.o
/home/splincode/Develop/omron/c++_modules/libomron/examples/omron_790IT_test/omron_790IT_test.c: In function ‘main’:
/home/splincode/Develop/omron/c++_modules/libomron/examples/omron_790IT_test/omron_790IT_test.c:34:9: warning: too many arguments for format [-Wformat-extra-args]
  printf("Opened omron 790IT\n", ret);
         ^
/home/splincode/Develop/omron/c++_modules/libomron/examples/omron_790IT_test/omron_790IT_test.c:56:15: warning: implicit declaration of function ‘omron_get_daily_data_count’ [-Wimplicit-function-declaration]
  data_count = omron_get_daily_data_count(test, bank);
               ^
[ 75%] Linking C executable ../bin/omron_790IT_test
[ 75%] Built target omron_790IT_test
[ 81%] Swig source
Scanning dependencies of target _omron
[ 87%] Building CXX object swig/CMakeFiles/_omron.dir/omronPYTHON_wrap.cxx.o
[ 93%] Building CXX object swig/CMakeFiles/_omron.dir/Omron.cxx.o
[100%] Linking CXX shared module ../lib/_omron.so
[100%] Built target _omron
Install the project...
-- Install configuration: ""
-- Installing: /home/splincode/Develop/omron/usr/local/include/libomron/libomron
-- Installing: /home/splincode/Develop/omron/usr/local/include/libomron/libomron/omron.h
-- Installing: /home/splincode/Develop/omron/usr/local/lib/libomron.a
-- Installing: /home/splincode/Develop/omron/usr/local/lib/libomron.so.0.9.0
-- Installing: /home/splincode/Develop/omron/usr/local/lib/libomron.so
-- Set runtime path of "/home/splincode/Develop/omron//usr/local/lib/libomron.so.0.9.0" to "/usr/local/lib"
-- Installing: /home/splincode/Develop/omron/usr/local/bin/omron_720IT_test
-- Set runtime path of "/home/splincode/Develop/omron//usr/local/bin/omron_720IT_test" to "/usr/local/lib"
-- Installing: /home/splincode/Develop/omron/usr/local/bin/omron_790IT_test
-- Set runtime path of "/home/splincode/Develop/omron//usr/local/bin/omron_790IT_test" to "/usr/local/lib"
-- Installing: /home/splincode/Develop/omron/usr/local/bin/omron_720IT_csv_dump
-- Set runtime path of "/home/splincode/Develop/omron//usr/local/bin/omron_720IT_csv_dump" to "/usr/local/lib"
-- Installing: /home/splincode/Develop/omron/usr/local/python/omron/omron.py
-- Installing: /home/splincode/Develop/omron/usr/local/python/omron/_omron.so
-- Installing: /home/splincode/Develop/omron/usr/local/python/omron/gui.py
-- Installing: /home/splincode/Develop/omron/usr/local/python/omron/store.py
-- Installing: /home/splincode/Develop/omron/usr/local/python/omron/__init__.py
-- Installing: /home/splincode/Develop/omron/usr/local/python/omron/plot.py
-- Installing: /home/splincode/Develop/omron/usr/local/python/omron/device.py
-- Installing: /home/splincode/Develop/omron/usr/local/python/omron/omron_790IT_test.py

```