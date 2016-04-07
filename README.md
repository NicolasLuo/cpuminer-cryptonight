cpuminer-cryptonight
==============

This is a multi-threaded CPU miner for cryptonight currencies.

#### Table of contents

* [Algorithms](#algorithms)
* [Dependencies](#dependencies)
* [Download](#download)
* [Build](#build)
* [Usage instructions](#usage-instructions)
* [License](#license)

Algorithms
==========

#### Currently supported

 * ✓ __cryptonight__ (Bytecoin [BCN], Monero)

Dependencies
============

* libcurl			http://curl.haxx.se/libcurl/
* jansson			http://www.digip.org/jansson/ (jansson is included in-tree)

Download
========

* Clone with `git clone https://github.com/bearbin/cpuminer-cryptonight`

Compiling
=========

#### Basic \*nix build instructions:

    ./autogen.sh
    CFLAGS="*-march=native*" ./configure
    make -j 2

#### Architecture-specific notes:

 * CryptoNight works only on x86 and x86-64.
 * If you want to mine a cryptonight currency on a processor that does not support the AES-NI instructions, you need to modify the compilation procedure. If your processor doesn't have AES-NI, mining is much slower, progressing at around 1/3rd the speed. This is the compilation procedure for CPUs that lack AES-NI:
 
    ./autogen.sh
    CFLAGS="*-march=native*" ./configure --disable-aes-ni
    make -j 2

Usage instructions
==================

Run "minerd --help" to see options.

### Connecting through a proxy

Use the --proxy option.

To use a SOCKS proxy, add a socks4:// or socks5:// prefix to the proxy host  
Protocols socks4a and socks5h, allowing remote name resolving, are also available since libcurl 7.18.0.

If no protocol is specified, the proxy is assumed to be a HTTP proxy.  
When the --proxy option is not used, the program honors the http_proxy and all_proxy environment variables.

License
=======

cpuminer-cryptonight is licensed under the GPLv2.  See LICENSE for details.
