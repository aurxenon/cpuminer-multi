**THIS ONLY RUNS ON THE CPU**


Purpose
=======
This repo is a fork of [xbbricker's](cpuminer-multi-opencl) multi-threaded macOS OpenCL/CPU miner for Boolberry, with modifications to compile/run on computers that don't support OpenCL. 


Build
=====
```sh
git clone https://github.com/aurxenon/cpuminer-multi
cd cpuminer-multi-opencl
./autogen.sh
CFLAGS="-march=native" ./configure
make -j
```


Usage instructions
==================

Always specify local scratchpad file (ex. -l scratchpad.bin)!

To mine:
```
minerd -a wildkeccak -o stratum+tcp://url_to_server:7777 -u boolberry wallet address -p X -l scratchpad.bin -k http://url_to_server/download/scratchpad.bin
```

Run "minerd --help" to see all options.

### Connecting through a proxy


Use the --proxy option.


To use a SOCKS proxy, add a socks4:// or socks5:// prefix to the proxy host  
Protocols socks4a and socks5h, allowing remote name resolving, are also available since libcurl 7.18.0.


If no protocol is specified, the proxy is assumed to be a HTTP proxy.  
When the --proxy option is not used, the program honors the http_proxy and all_proxy environment variables.


Donations
=========
Donations for the work done in this fork by mbk are accepted at
* BBR: `@mbk`
* BTC: `1Lns6UjL3sw77DJ5z1EKJZy6SnqriqvVGK`


aurxenon accepts donations at
* BBR: `1Gb8Hqg7VLWb5CTCynp258V2TpwQZAwZGZaxW3EoJ6aYSf5WVwCTtNeAWQ4cAgkaGnCujWs7b7Pin6kfHsXNkkWYUqJ8H7g`


Credits
=======
cpuminer-multi was forked from xbbricker's cpuminer-multi-opencl, and has been developed by aurxenon.

License
=======
GPLv2.  See COPYING for details.
