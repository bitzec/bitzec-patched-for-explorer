BITZEC 1.1.1

===========
What are 
[Zero knowledge proofs](https://en.wikipedia.org/wiki/Zero-knowledge_proof) ?
[Zcash](https://z.cash/) is an implementation of the "Zerocash" protocol.
Based on Bitcoin's code.
What is [Bitcoin](https://en.wikipedia.org/wiki/Bitcoin) ?
--------------

[Zcash](https://z.cash/) is an implementation of the "Zerocash" protocol.
Based on Bitcoin's code, it intends to offer a far higher standard of privacy
through a sophisticated zero-knowledge proving scheme that preserves
confidentiality of transaction metadata. Technical details are available
in our [Protocol Specification](https://github.com/zcash/zips/raw/master/protocol/protocol.pdf).

This software is the Bitzec client. It downloads and stores the entire history
of Bitzec transactions; depending on the speed of your computer and network
connection, the synchronization process could take a day or more once the
blockchain has reached a significant size.


<p align="center">
  <img src="doc/imgs/zcashd_screen.gif" height="500">
</p>

#### :lock: Security Warnings

See important security warnings on the
[Security Information page](https://z.cash/support/security/).


```{r, engine='bash'}
Install dependencies:

sudo apt-get install \
build-essential pkg-config libc6-dev m4 g++-multilib \
autoconf libtool ncurses-dev unzip git python python-zmq \
zlib1g-dev wget curl bsdmainutils automake

Clone Bitzec Repository :

git clone https://github.com/bitzec/bitzec-patched-for-explorer

Build it :
cd bitzec/
./zcutil/build.sh -j$(nproc)
fetch key:
./zcutil/fetch-params.sh
mkdir -p ~/.bitzec
echo 'gen=1' >> ~/.bitzec/bitzec.conf
echo "genproclimit=1" >> ~/.bitzec/bitzec.conf
echo 'equihashsolver=tromp' >> ~/.bitzec/bitzec.conf

Run It
./src/bitzecd
./src/bitzec-cli getblockchaininfo


./bitzec-cli help      <--- for full command list 
open debug.log under ctrl+h hidden folder .bitzec/debug.log

windows crosscompile on Debian / Ubuntu: 
 sudo apt install mingw-w64
 sudo update-alternatives --config x86_64-w64-mingw32-gcc
     (configure 1 to use POSIX variant)
 sudo update-alternatives --config x86_64-w64-mingw32-g++
     (configure 1 to use POSIX variant)
 HOST=x86_64-w64-mingw32 ./zcutil/build.sh
 you will get src/bitzec-cli.exe src/bitzecd.exe src/zcash-gtest.exe src/bitzec-tx.exe
in case you compiled for ubuntu before on same folder bitzec   ( make clean && make -C src/univalue clean )
```
Installation video :https://youtu.be/5ahQZZYcntQ

![Screenshot](https://github.com/bitzec/bitzec-swing/blob/master/docs/zecmate.png "Main Window")


BLOCKREWARD DECREAS PLAN  every 20k blocks(34days)  after block 77777  . Slowstart 7 blocks
<p align="center">
  <img src="doc/imgs/blockreward .png" height="500">

### START TESTING:Testing

Add unit tests for Bitzec under Bitzec  ./src/gtest.

To list all tests, run ./src/zcash-gtest --gtest_list_tests.

To run a subset of tests, use a regular expression with the flag --gtest_filter. Example:

` ./src/zcash-gtest --gtest_filter=DeprecationTest.* `

For debugging: --gtest_break_on_failure.

To run a subset of BOOST tests: ` src/test/test_bitcoin -t TESTGROUP/TESTNAME


https://zcash.readthedocs.io/en/latest/rtd_pages/development_guidelines.html#development-guidelines


####  :ledger: Deprecation Policy

This release is considered deprecated 16 weeks after the release day. There
is an automatic deprecation shutdown feature which will halt the node some
time after this 16 week time period. The automatic feature is based on block
height.

## Getting Started

Please see our [user guide](https://zcash.readthedocs.io/en/latest/rtd_pages/rtd_docs/user_guide.html) for joining the main Zcash network.

### Need Help?

* :blue_book: See the documentation at the [ReadtheDocs](https://zcash.readthedocs.io)
  for help and more information.


### Building

Build Bitzec along with most dependencies from source by running:

```
./zcutil/build.sh -j$(nproc)
```



License
-------

For license information see the file [COPYING](COPYING).
