# gr-lfast - Timed, tuned, and accelerated GNURadio blocks

gr-lfast builds on gr-clenabled by focusing on CPU-only blocks and looking for optimizations.  For instance the Costas Loop module clocked at about 24 MSPS
throughput.  However to process wider signals, this block would need to process more data.  Optimizations were identified in the code that increased 
block throughput to 38 MSPS (almost 58% speed improvement).  The AGC block was given the same optimizations for about a 10% speed increase from 79 MSPS 
to about 87 MSPS.  The block Complex->Real->Char->Vector combines Complex->Real, Float->char, and stream->Vector in a single block, saving on buffer copies and multiple threads.  Overall speedup on that block was nominal, 5-9%.  More blocks will be added as they are tested.


After building, in the build directory's lib subdirectory will be a file called test-lfast that will display metrics for before and after tuning on your system.  The following shows the throughput on an i7-6700 CPU @ 3.40GHz:

----------------------------------------------------------

Testing Costas Loop with 8192 samples...

Original Code Run Time:      0.000339 s  (24134816.000000 sps)

LFAST Code Run Time:      0.000215 s  (38078292.000000 sps)

Speedup:         57.77% faster

----------------------------------------------------------

Testing AGC with 8192 samples...

Original Code Run Time:      0.000103 s  (79309376.000000 sps)

LFAST Code Run Time:      0.000094 s  (87053392.000000 sps)

Speedup:          9.76% faster

----------------------------------------------------------
Testing Complex->Real->Char->Vector with 8192 samples...

Original Code Run Time:      0.000003 s  (3049752064.000000 sps)

LFAST Code Run Time:      0.000003 s  (3263588864.000000 sps)

Speedup:          7.01% faster


To build gr-lfast, simply follow the standard module build process.  Git clone it to a directory, close GNURadio if you have it open, then use the following build steps:

cd <clone directory>

mkdir build

cd build

cmake ..

make

sudo make install

sudo ldconfig

If each step was successful (don�t overlook the �sudo ldconfig� step).

