# sqlite-amalgamation

This repository contains an intact copy of the [SQLite](http://www.sqlite.org/download.html) amalgamation, provided in order to be included in `git submodule` and other `git` based, custom dependency managers.

SQLite includes more than 100 files in `*.c` / `*.h`, but
> The [amalgamation](http://www.sqlite.org/amalgamation.html) contains everything you need to integrate SQLite into a larger project. Just copy the amalgamation into your source directory and compile it along with the other C code files in your project. ([A more detailed discussion](http://www.sqlite.org/howtocompile.html) of the compilation process is available.) You may also want to make use of the "sqlite3.h" header file that defines the programming API for SQLite. The sqlite3.h header file is available separately. The sqlite3.h file is also contained within the amalgamation, in the first few thousand lines. So if you have a copy of sqlite3.c but cannot seem to locate sqlite3.h, you can always regenerate the sqlite3.h by copying and pasting from the amalgamation.



![SQLite3](http://www.sqlite.org/images/sqlite370_banner.gif)

## build
This repository ships with two build generators (`cmake`, `premake5`). An static lib (`libsqlite3`) and the sqlite3 shell will be generated by build system.

### cmake
to build by `cmake` in project source tree:
```bash

# under Linux / OS X
$> mkdir xbin
$> cd xbin
$> cmake ..
$> make

# under Windows
$> mkdir xbin
$> cd xbin
$> cmake ..
$> cmake --build . --config Release
```

by `gcc` and `clang` it's also possilbe to build `sqlite3` as a shared library by `cmake`:
```bash
# on gcc or clang (Linux or OS X)
$> mkdir xbin
$> cd xbin
$> cmake .. -DBUILD_SHARED_LIBS=ON
$> make
```

### premake5
to build by `premake5` in project source tree:
```bash
# on Linux / OS X
$> premake5 gmake
$> make

# on Windows
$> premake5.exe vs2015 # or other installed toolset
$> msbuild.exe sqlite.sln /p:Configuration=Release
```

