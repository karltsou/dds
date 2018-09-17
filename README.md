# DDS for Linux
Migrate windows base DDS utility port to linux

### Build setups
  - Ubuntu 14.04 above
  - GNU make, gcc compiler ie. `gcc version 4.8.5 (Ubuntu 4.8.5-4ubuntu8~14.04.2)`

### Make static libs
| `static_library` | Path |
| ------ | ------ | 
| app_sup | src\app_sup |
| cm | src\cm |
| cstk | src\ctsk |
| dds | src\dds |
| interp | src\interp |
| pc | src\pc |
| common | common |

build ./src/`static_library`
```sh
$ cd src/static_library
$ make
```

build ./common
```sh
$ cd common
$ make
```

### Make sample

copy all the static libs to sample then make
```sh
$ cp -p src/static_library/.a src/sample
$ cp -p common/.a src/sample
$ cd src/sample
make
```

### Install samplexxx

```sh
$ cd sample
$ make install
```

### Clean the build
```sh
$ cd src/app_sub
$ make clean
```

### Changes list
  - added Makefile for src/`static_library`
  - added Makefile for common
  - added Makefile for sample
  - modified original dds source that can be compiled for gcc on linux
  
### Bug list
unknow define `yylex ()`
