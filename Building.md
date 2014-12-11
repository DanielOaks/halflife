Building Half Life libraries
============================

Mac
---
To build the Half Life libraries under OS X, you must go to the `linux/` directory – because of the similar Unixy backends, OS X uses the Linux makefiles.

After that, you simply run `make` and it builds the required libraries in `../game`.

**Note:** Perforce is enabled by default, and `PERFORCE=false` must be passed as an environment variable if you wish to disable this or if you are not running the right sort of Perforce server.

An example build is shown here:

```
$ cd linux/
$ PERFORCE=false make
mkdir release;
mkdir: release: File exists
make: [build_dir] Error 1 (ignored)
cd release
mkdir -p ../../game/mod/dlls/
mkdir -p ../../game/mod/cl_dlls/

... lots of lines of making the libraries

cp release/client_ricochet.dylib  ../../game/mod/cl_dlls/client.dylib
./gendbg.sh ../../game/mod/cl_dlls/client.dylib

$ ls ../../game/mod/cl_dlls
client.dylib   client.dylib.dSYM
$ ls ../../game/mod/dlls
dmc.dylib   dmc.dylib.dSYM   hl.dylib   hl.dylib.dSYM   ricochet.dylib   ricochet.dylib.dSYM
```
