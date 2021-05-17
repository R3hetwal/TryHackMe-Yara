# TryHackMe-Yara

Installation:

──(root💀kali)-[~]
└─# sudo apt-get install automake libtool make gcc pkg-config

Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
automake is already the newest version (1:1.16.3-2).
automake set to manually installed.
gcc is already the newest version (4:10.2.1-1).
gcc set to manually installed.
libtool is already the newest version (2.4.6-15).
libtool set to manually installed.
make is already the newest version (4.3-4.1).
make set to manually installed.
pkg-config is already the newest version (0.29.2-1).
pkg-config set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 2 not upgraded.
                                                                             
┌──(root💀kali)-[~]
└─# sudo apt-get install flex bison
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libfl-dev libfl2
Suggested packages:
  bison-doc flex-doc
The following NEW packages will be installed:
  bison flex libfl-dev libfl2
0 upgraded, 4 newly installed, 0 to remove and 2 not upgraded.
Need to get 1,752 kB of archives.
After this operation, 4,519 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://kali.cs.nctu.edu.tw/kali kali-rolling/main amd64 flex amd64 2.6.4-8 [440 kB]
Get:2 http://kali.cs.nctu.edu.tw/kali kali-rolling/main amd64 bison amd64 2:3.7.5+dfsg-1 [1,104 kB]
Get:3 http://kali.cs.nctu.edu.tw/kali kali-rolling/main amd64 libfl2 amd64 2.6.4-8 [103 kB]
Get:4 http://kali.cs.nctu.edu.tw/kali kali-rolling/main amd64 libfl-dev amd64 2.6.4-8 [104 kB]
Fetched 1,752 kB in 7s (264 kB/s)                                           
Selecting previously unselected package flex.
(Reading database ... 451176 files and directories currently installed.)
Preparing to unpack .../flex_2.6.4-8_amd64.deb ...
Unpacking flex (2.6.4-8) ...
Selecting previously unselected package bison.
Preparing to unpack .../bison_2%3a3.7.5+dfsg-1_amd64.deb ...
Unpacking bison (2:3.7.5+dfsg-1) ...
Selecting previously unselected package libfl2:amd64.
Preparing to unpack .../libfl2_2.6.4-8_amd64.deb ...
Unpacking libfl2:amd64 (2.6.4-8) ...
Selecting previously unselected package libfl-dev:amd64.
Preparing to unpack .../libfl-dev_2.6.4-8_amd64.deb ...
Unpacking libfl-dev:amd64 (2.6.4-8) ...
Setting up flex (2.6.4-8) ...
Setting up libfl2:amd64 (2.6.4-8) ...
Setting up bison (2:3.7.5+dfsg-1) ...
update-alternatives: using /usr/bin/bison.yacc to provide /usr/bin/yacc (yacc) in auto mode
Setting up libfl-dev:amd64 (2.6.4-8) ...
Processing triggers for doc-base (0.11.1) ...
Processing 1 added doc-base file...
Processing triggers for libc-bin (2.31-11) ...
Processing triggers for man-db (2.9.4-2) ...
Processing triggers for kali-menu (2021.2.1) ...
                                                                             

Then download zip from https://github.com/VirusTotal/yara/releases
┌──(root💀kali)-[~/Downloads]
└─# cd yara-4.1.0
                                                                              
┌──(root💀kali)-[~/Downloads/yara-4.1.0]
└─# ./bootstrap.sh           
libtoolize: putting auxiliary files in AC_CONFIG_AUX_DIR, 'build-aux'.
libtoolize: copying file 'build-aux/ltmain.sh'
libtoolize: putting macros in AC_CONFIG_MACRO_DIRS, 'm4'.
libtoolize: copying file 'm4/libtool.m4'
libtoolize: copying file 'm4/ltoptions.m4'
libtoolize: copying file 'm4/ltsugar.m4'
libtoolize: copying file 'm4/ltversion.m4'
libtoolize: copying file 'm4/lt~obsolete.m4'
configure.ac:20: installing 'build-aux/ar-lib'
configure.ac:20: installing 'build-aux/compile'
configure.ac:38: installing 'build-aux/config.guess'
configure.ac:38: installing 'build-aux/config.sub'
configure.ac:8: installing 'build-aux/install-sh'
configure.ac:8: installing 'build-aux/missing'
Makefile.am: installing 'build-aux/depcomp'
parallel-tests: installing 'build-aux/test-driver'
configure.ac: installing 'build-aux/ylwrap'
                                                                              
┌──(root💀kali)-[~/Downloads/yara-4.1.0]
└─# ./configure   
checking whether make supports nested variables... yes
checking for a BSD-compatible install... /usr/bin/install -c
checking whether build environment is sane... yes
checking for a thread-safe mkdir -p... /usr/bin/mkdir -p
checking for gawk... gawk
checking whether make sets $(MAKE)... yes
checking whether make supports the include directive... yes (GNU style)
checking for gcc... gcc
checking whether the C compiler works... yes
checking for C compiler default output file name... a.out
checking for suffix of executables... 
checking whether we are cross compiling... no
checking for suffix of object files... o
checking whether we are using the GNU C compiler... yes
checking whether gcc accepts -g... yes
checking for gcc option to accept ISO C89... none needed
checking whether gcc understands -c and -o together... yes
checking dependency style of gcc... gcc3
checking for ar... ar
checking the archiver (ar) interface... ar
checking for gcc... (cached) gcc
checking whether we are using the GNU C compiler... (cached) yes
checking whether gcc accepts -g... (cached) yes
checking for gcc option to accept ISO C89... (cached) none needed
checking whether gcc understands -c and -o together... (cached) yes
checking dependency style of gcc... (cached) gcc3
checking for gcc option to accept ISO C99... none needed
checking for flex... flex
checking lex output file root... lex.yy
checking lex library... -lfl
checking whether yytext is a pointer... yes
checking for bison... bison -y
checking for inline... inline
checking how to run the C preprocessor... gcc -E
checking for grep that handles long lines and -e... /usr/bin/grep
checking for egrep... /usr/bin/grep -E
checking for ANSI C header files... yes
checking for sys/types.h... yes
checking for sys/stat.h... yes
checking for stdlib.h... yes
checking for string.h... yes
checking for memory.h... yes
checking for strings.h... yes
checking for inttypes.h... yes
checking for stdint.h... yes
checking for unistd.h... yes
checking whether byte ordering is bigendian... no
checking for special C compiler options needed for large files... no
checking for _FILE_OFFSET_BITS value needed for large files... no
checking build system type... x86_64-pc-linux-gnu
checking host system type... x86_64-pc-linux-gnu
checking how to print strings... printf
checking for a sed that does not truncate output... /usr/bin/sed
checking for fgrep... /usr/bin/grep -F
checking for ld used by gcc... /usr/bin/ld
checking if the linker (/usr/bin/ld) is GNU ld... yes
checking for BSD- or MS-compatible name lister (nm)... /usr/bin/nm -B
checking the name lister (/usr/bin/nm -B) interface... BSD nm
checking whether ln -s works... yes
checking the maximum length of command line arguments... 1572864
checking how to convert x86_64-pc-linux-gnu file names to x86_64-pc-linux-gnu format... func_convert_file_noop
checking how to convert x86_64-pc-linux-gnu file names to toolchain format... func_convert_file_noop
checking for /usr/bin/ld option to reload object files... -r
checking for objdump... objdump
checking how to recognize dependent libraries... pass_all
checking for dlltool... no
checking how to associate runtime and link libraries... printf %s\n
checking for archiver @FILE support... @
checking for strip... strip
checking for ranlib... ranlib
checking command to parse /usr/bin/nm -B output from gcc object... ok
checking for sysroot... no
checking for a working dd... /usr/bin/dd
checking how to truncate binary pipes... /usr/bin/dd bs=4096 count=1
checking for mt... mt
checking if mt is a manifest tool... no
checking for dlfcn.h... yes
checking for objdir... .libs
checking if gcc supports -fno-rtti -fno-exceptions... no
checking for gcc option to produce PIC... -fPIC -DPIC
checking if gcc PIC flag -fPIC -DPIC works... yes
checking if gcc static flag -static works... yes
checking if gcc supports -c -o file.o... yes
checking if gcc supports -c -o file.o... (cached) yes
checking whether the gcc linker (/usr/bin/ld -m elf_x86_64) supports shared libraries... yes
checking whether -lc should be explicitly linked in... no
checking dynamic linker characteristics... GNU/Linux ld.so
checking how to hardcode library paths into programs... immediate
checking whether stripping libraries is possible... yes
checking if libtool supports shared libraries... yes
checking whether to build shared libraries... yes
checking whether to build static libraries... yes
checking for the pthreads library -lpthreads... no
checking whether pthreads work without any flags... no
checking whether pthreads work with -Kthread... no
checking whether pthreads work with -kthread... no
checking for the pthreads library -llthread... no
checking whether pthreads work with -pthread... yes
checking for joinable pthread attribute... PTHREAD_CREATE_JOINABLE
checking if more special flags are required for pthreads... no
checking whether to check for GCC pthread/shared inconsistencies... yes
checking whether -pthread is sufficient with -shared... yes
checking for isnan in -lm... yes
checking for log2 in -lm... yes
checking for strlcpy... no
checking for strlcat... no
checking for memmem... yes
checking for timegm... yes
checking for _mkgmtime... no
checking for clock_gettime... yes
checking stdbool.h usability... yes
checking stdbool.h presence... yes
checking for stdbool.h... yes
checking for pkg-config... /usr/bin/pkg-config
checking pkg-config is at least version 0.9.0... yes
checking openssl/md5.h usability... yes
checking openssl/md5.h presence... yes
checking for openssl/md5.h... yes
checking openssl/sha.h usability... yes
checking openssl/sha.h presence... yes
checking for openssl/sha.h... yes
checking openssl/asn1.h usability... yes
checking openssl/asn1.h presence... yes
checking for openssl/asn1.h... yes
checking openssl/crypto.h usability... yes
checking openssl/crypto.h presence... yes
checking for openssl/crypto.h... yes
checking openssl/bio.h usability... yes
checking openssl/bio.h presence... yes
checking for openssl/bio.h... yes
checking openssl/pkcs7.h usability... yes
checking openssl/pkcs7.h presence... yes
checking for openssl/pkcs7.h... yes
checking openssl/x509.h usability... yes
checking openssl/x509.h presence... yes
checking for openssl/x509.h... yes
checking openssl/safestack.h usability... yes
checking openssl/safestack.h presence... yes
checking for openssl/safestack.h... yes
checking for MD5_Init in -lcrypto... yes
checking for MD5_Update in -lcrypto... yes
checking for MD5_Final in -lcrypto... yes
checking for SHA256_Init in -lcrypto... yes
checking for SHA256_Update in -lcrypto... yes
checking for SHA256_Final in -lcrypto... yes
checking that generated files are newer than configure... done
configure: creating ./config.status
config.status: creating Makefile
config.status: creating libyara/Makefile
config.status: creating libyara/yara.pc
config.status: executing depfiles commands
config.status: executing libtool commands
                                                                              
┌──(root💀kali)-[~/Downloads/yara-4.1.0]
└─# make                                        
Making all in libyara
make[1]: Entering directory '/root/Downloads/yara-4.1.0/libyara'
make  all-am
make[2]: Entering directory '/root/Downloads/yara-4.1.0/libyara'
  CC       modules/tests/tests.lo
  CC       modules/elf/elf.lo
  CC       modules/math/math.lo
  CC       modules/time/time.lo
  CC       modules/pe/pe.lo
  CC       modules/pe/pe_utils.lo
  CC       modules/hash/hash.lo
  CC       grammar.lo
  CC       ahocorasick.lo
  CC       arena.lo
  CC       atoms.lo
  CC       base64.lo
  CC       bitmask.lo
  CC       compiler.lo
  CC       endian.lo
  CC       exec.lo
  CC       exefiles.lo
  CC       filemap.lo
  CC       hash.lo
  CC       hex_grammar.lo
  CC       hex_lexer.lo
  CC       lexer.lo
  CC       libyara.lo
  CC       mem.lo
  CC       modules.lo
  CC       notebook.lo
  CC       object.lo
  CC       parser.lo
  CC       proc.lo
  CC       re.lo
  CC       re_grammar.lo
  CC       re_lexer.lo
  CC       rules.lo
  CC       scan.lo
  CC       scanner.lo
  CC       sizedstr.lo
  CC       stack.lo
  CC       stopwatch.lo
  CC       strutils.lo
  CC       stream.lo
  CC       threading.lo
  CC       proc/linux.lo
  CCLD     libyara.la
copying selected object files to avoid basename conflicts...
make[2]: Leaving directory '/root/Downloads/yara-4.1.0/libyara'
make[1]: Leaving directory '/root/Downloads/yara-4.1.0/libyara'
make[1]: Entering directory '/root/Downloads/yara-4.1.0'
  CC       cli/args.o
  CC       cli/threading.o
  CC       cli/yara.o
  CCLD     yara
  CC       cli/yarac.o
  CCLD     yarac
make[1]: Leaving directory '/root/Downloads/yara-4.1.0'
                                                                              
┌──(root💀kali)-[~/Downloads/yara-4.1.0]
└─# sudo make install              
Making install in libyara
make[1]: Entering directory '/root/Downloads/yara-4.1.0/libyara'
make  install-am
make[2]: Entering directory '/root/Downloads/yara-4.1.0/libyara'
make[3]: Entering directory '/root/Downloads/yara-4.1.0/libyara'
 /usr/bin/mkdir -p '/usr/local/lib'
 /bin/bash ../libtool   --mode=install /usr/bin/install -c   libyara.la '/usr/local/lib'
libtool: install: /usr/bin/install -c .libs/libyara.so.8.0.0 /usr/local/lib/libyara.so.8.0.0
libtool: install: (cd /usr/local/lib && { ln -s -f libyara.so.8.0.0 libyara.so.8 || { rm -f libyara.so.8 && ln -s libyara.so.8.0.0 libyara.so.8; }; })
libtool: install: (cd /usr/local/lib && { ln -s -f libyara.so.8.0.0 libyara.so || { rm -f libyara.so && ln -s libyara.so.8.0.0 libyara.so; }; })
libtool: install: /usr/bin/install -c .libs/libyara.lai /usr/local/lib/libyara.la
libtool: install: /usr/bin/install -c .libs/libyara.a /usr/local/lib/libyara.a
libtool: install: chmod 644 /usr/local/lib/libyara.a
libtool: install: ranlib /usr/local/lib/libyara.a
libtool: finish: PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/sbin" ldconfig -n /usr/local/lib
----------------------------------------------------------------------
Libraries have been installed in:
   /usr/local/lib

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the '-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the 'LD_LIBRARY_PATH' environment variable
     during execution
   - add LIBDIR to the 'LD_RUN_PATH' environment variable
     during linking
   - use the '-Wl,-rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to '/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
----------------------------------------------------------------------
 /usr/bin/mkdir -p '/usr/local/include'
 /usr/bin/install -c -m 644 include/yara.h '/usr/local/include'
 /usr/bin/mkdir -p '/usr/local/lib/pkgconfig'
 /usr/bin/install -c -m 644 yara.pc '/usr/local/lib/pkgconfig'
 /usr/bin/mkdir -p '/usr/local/include/yara'
 /usr/bin/install -c -m 644 include/yara/ahocorasick.h include/yara/arena.h include/yara/atoms.h include/yara/base64.h include/yara/bitmask.h include/yara/compiler.h include/yara/error.h include/yara/exec.h include/yara/exefiles.h include/yara/filemap.h include/yara/hash.h include/yara/integers.h include/yara/libyara.h include/yara/limits.h include/yara/mem.h include/yara/modules.h include/yara/notebook.h include/yara/object.h include/yara/parser.h include/yara/proc.h include/yara/re.h include/yara/rules.h include/yara/scan.h include/yara/scanner.h include/yara/sizedstr.h include/yara/stack.h include/yara/stopwatch.h include/yara/stream.h include/yara/strutils.h include/yara/threading.h include/yara/types.h include/yara/utils.h '/usr/local/include/yara'
make[3]: Leaving directory '/root/Downloads/yara-4.1.0/libyara'
make[2]: Leaving directory '/root/Downloads/yara-4.1.0/libyara'
make[1]: Leaving directory '/root/Downloads/yara-4.1.0/libyara'
make[1]: Entering directory '/root/Downloads/yara-4.1.0'
make[2]: Entering directory '/root/Downloads/yara-4.1.0'
 /usr/bin/mkdir -p '/usr/local/bin'
  /bin/bash ./libtool   --mode=install /usr/bin/install -c yara yarac '/usr/local/bin'
libtool: install: /usr/bin/install -c .libs/yara /usr/local/bin/yara
libtool: install: /usr/bin/install -c .libs/yarac /usr/local/bin/yarac
 /usr/bin/mkdir -p '/usr/local/share/man/man1'
 /usr/bin/install -c -m 644 'yara.man' '/usr/local/share/man/man1/yara.1'
 /usr/bin/install -c -m 644 'yarac.man' '/usr/local/share/man/man1/yarac.1'
make[2]: Leaving directory '/root/Downloads/yara-4.1.0'
make[1]: Leaving directory '/root/Downloads/yara-4.1.0'
                                                                              
┌──(root💀kali)-[~/Downloads/yara-4.1.0]
└─# make check
Making check in libyara
make[1]: Entering directory '/root/Downloads/yara-4.1.0/libyara'
make  check-am
make[2]: Entering directory '/root/Downloads/yara-4.1.0/libyara'
make[2]: Nothing to be done for 'check-am'.
make[2]: Leaving directory '/root/Downloads/yara-4.1.0/libyara'
make[1]: Leaving directory '/root/Downloads/yara-4.1.0/libyara'
make[1]: Entering directory '/root/Downloads/yara-4.1.0'
make  test-arena test-alignment test-atoms test-api test-rules test-pe test-elf test-version test-bitmask test-math test-stack test-re-split test-async test-exception    
make[2]: Entering directory '/root/Downloads/yara-4.1.0'
  CC       tests/test-arena.o
  CC       tests/util.o
  CCLD     test-arena
  CC       tests/test-alignment.o
  CCLD     test-alignment
  CC       tests/test-atoms.o
  CCLD     test-atoms
  CC       tests/test-api.o
  CCLD     test-api
  CC       tests/test-rules.o
  CCLD     test-rules
  CC       tests/test-pe.o
  CCLD     test-pe
  CC       tests/test-elf.o
  CCLD     test-elf
  CC       tests/test-version.o
  CCLD     test-version
  CC       tests/test-bitmask.o
  CCLD     test-bitmask
  CC       tests/test-math.o
  CCLD     test-math
  CC       tests/test-stack.o
  CCLD     test-stack
  CC       tests/test-re-split.o
  CCLD     test-re-split
  CC       tests/test-async.o
  CCLD     test-async
  CC       tests/test-exception.o
  CCLD     test-exception
make[2]: Leaving directory '/root/Downloads/yara-4.1.0'
make  check-TESTS
make[2]: Entering directory '/root/Downloads/yara-4.1.0'
make[3]: Entering directory '/root/Downloads/yara-4.1.0'
PASS: test-arena
PASS: test-alignment
PASS: test-atoms
PASS: test-api
PASS: test-rules
PASS: test-pe
PASS: test-elf
PASS: test-version
PASS: test-bitmask
PASS: test-math
PASS: test-stack
PASS: test-re-split
PASS: test-async
PASS: test-exception
============================================================================
Testsuite summary for yara 4.1.0
============================================================================
# TOTAL: 14
# PASS:  14
# SKIP:  0
# XFAIL: 0
# FAIL:  0
# XPASS: 0
# ERROR: 0
============================================================================
make[3]: Leaving directory '/root/Downloads/yara-4.1.0'
make[2]: Leaving directory '/root/Downloads/yara-4.1.0'
make[1]: Leaving directory '/root/Downloads/yara-4.1.0'
                                                                              
