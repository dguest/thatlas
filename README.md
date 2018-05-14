Build Instructions
==================

Clone the repo and get a data file:

 - `git clone git@github.com:dguest/thatlas.git`
 - `cd thatlas`
 - run `./get-dataset.sh` or just find a DxAOD

Build:

```
mkdir build
cd build
cmake ../xaod_dumpinator
make
```

Run:

```
./x86_64-slc6-gcc62-*/bin/dump-xaod <path-to-data-file>
```

Different things go wrong depending on whether you include the line

```
set(CMAKE_BUILD_TYPE Debug)
```

in the outer `CMakeLists.txt` file.
