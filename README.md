## 1. Get sources from
http://code.google.com/p/sqlite4java/source/checkout

## 2. Get sqlite_wrap.c file from
https://raw.github.com/SpatialInteractive/sqlite4java-custom/master/custom/swig/sqlite_wrap.c

## 3. Put sqlite_wrap.c to sources directory. You need native, sqlite directories and sqlite_wrap.c file there.

## 4. Create RELEASE file with content:
```
#gcc
gcc -O2 -DNDEBUG -fpic -DARM -DARCH="ARM" -DLINUX -D_LARGEFILE64_SOURCE -D_GNU_SOURCE -D_LITTLE_ENDIAN -fno-omit-frame-pointer -fno-strict-aliasing -static-libgcc -I./sqlite -I/usr/lib/jvm/jdk-7-oracle-armhf/include -I/usr/lib/jvm/jdk-7-oracle-armhf/include/linux -DSQLITE_ENABLE_COLUMN_METADATA -DSQLITE_ENABLE_FTS3 -DSQLITE_ENABLE_FTS3_PARENTHESIS -DSQLITE_ENABLE_MEMORY_MANAGEMENT -DSQLITE_ENABLE_STAT2 -DHAVE_READLINE=0 -DSQLITE_THREADSAFE=1 -DSQLITE_THREAD_OVERRIDE_LOCK=-1 -DTEMP_STORE=1 -DSQLITE_OMIT_LOAD_EXTENSION=1 -DSQLITE_OMIT_DEPRECATED -DSQLITE_OS_UNIX=1 -c ./sqlite/sqlite3.c -o sqlite3.o
gcc -O2 -DNDEBUG -fpic -DARM -DARCH="ARM" -DLINUX -D_LARGEFILE64_SOURCE -D_GNU_SOURCE -D_LITTLE_ENDIAN -fno-omit-frame-pointer -fno-strict-aliasing -static-libgcc -I./sqlite -I/usr/lib/jvm/jdk-7-oracle-armhf/include -I/usr/lib/jvm/jdk-7-oracle-armhf/include/linux -DSQLITE_ENABLE_COLUMN_METADATA -DSQLITE_ENABLE_FTS3 -DSQLITE_ENABLE_FTS3_PARENTHESIS -DSQLITE_ENABLE_MEMORY_MANAGEMENT -DSQLITE_ENABLE_STAT2 -DHAVE_READLINE=0 -DSQLITE_THREADSAFE=1 -DSQLITE_THREAD_OVERRIDE_LOCK=-1 -DTEMP_STORE=1 -DSQLITE_OMIT_LOAD_EXTENSION=1 -DSQLITE_OMIT_DEPRECATED -DSQLITE_OS_UNIX=1 -c sqlite_wrap.c -o sqlite_wrap.o
gcc -O2 -DNDEBUG -fpic -Di586 -DARCH="i586" -DLINUX -D_LARGEFILE64_SOURCE -D_GNU_SOURCE -D_LITTLE_ENDIAN -fno-omit-frame-pointer -fno-strict-aliasing -static-libgcc -I./sqlite -I./native -I/usr/lib/jvm/jdk-7-oracle-armhf/include -I/usr/lib/jvm/jdk-7-oracle-armhf/include/linux -DSQLITE_ENABLE_COLUMN_METADATA -DSQLITE_ENABLE_FTS3 -DSQLITE_ENABLE_FTS3_PARENTHESIS -DSQLITE_ENABLE_MEMORY_MANAGEMENT -DSQLITE_ENABLE_STAT2 -DHAVE_READLINE=0 -DSQLITE_THREADSAFE=1 -DSQLITE_THREAD_OVERRIDE_LOCK=-1 -DTEMP_STORE=1 -DSQLITE_OMIT_LOAD_EXTENSION=1 -DSQLITE_OMIT_DEPRECATED -DSQLITE_OS_UNIX=1 -c ./native/sqlite3_wrap_manual.c -o sqlite3_wrap_manual.o
gcc -O2 -DNDEBUG -fpic -Di586 -DARCH="i586" -DLINUX -D_LARGEFILE64_SOURCE -D_GNU_SOURCE -D_LITTLE_ENDIAN -fno-omit-frame-pointer -fno-strict-aliasing -static-libgcc -I./sqlite -I./native -I/usr/lib/jvm/jdk-7-oracle-armhf/include -I/usr/lib/jvm/jdk-7-oracle-armhf/include/linux -DSQLITE_ENABLE_COLUMN_METADATA -DSQLITE_ENABLE_FTS3 -DSQLITE_ENABLE_FTS3_PARENTHESIS -DSQLITE_ENABLE_MEMORY_MANAGEMENT -DSQLITE_ENABLE_STAT2 -DHAVE_READLINE=0 -DSQLITE_THREADSAFE=1 -DSQLITE_THREAD_OVERRIDE_LOCK=-1 -DTEMP_STORE=1 -DSQLITE_OMIT_LOAD_EXTENSION=1 -DSQLITE_OMIT_DEPRECATED -DSQLITE_OS_UNIX=1 -c ./native/intarray.c -o intarray.o
gcc -O2 -DNDEBUG -fpic -Di586 -DARCH="i586" -DLINUX -D_LARGEFILE64_SOURCE -D_GNU_SOURCE -D_LITTLE_ENDIAN -fno-omit-frame-pointer -fno-strict-aliasing -static-libgcc -shared -mno-cygwin -Wl,-soname=libsqlite4java-linux-arm.so -o libsqlite4java-linux-arm.so sqlite3.o sqlite_wrap.o sqlite3_wrap_manual.o intarray.o
```

## 5. chmod +x RELEASE and run it ./RELEASE.

## 6. libsqlite4java-linux-arm.so will be built, you need to copy it in proper path of your application.

Ref: https://stackoverflow.com/questions/21750601/sqlite4java-on-raspberry-pi
