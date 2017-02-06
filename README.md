Purpose
=======
This repo is a fork of [mbkuperman's](cpuminer-multi-opencl) multi-threaded OpenCL/CPU miner for Boolberry, with modifications to compile/run on macOS. 


Build (macOS)
=====
```sh
git clone https://github.com/xbbricker/cpuminer-multi-opencl
cd cpuminer-multi-opencl
./autogen.sh
CFLAGS="-march=native" ./configure
make -j
```

Usage instructions
==================

Copy *.cl kernel files to executable's directory.
Always specify local scratchpad file (ex. -l scratchpad.bin)!

To mine on all available GPUs:
```
minerd -a wildkeccak_ocl -o stratum+tcp://url_to_server:7777 -u 1EmWGnwhydr3S2vRWQbbefh1hgDKgMjdMGe43ZgdPhdARhNBRkUMuD4YzLA2nyYG8tg2HKCCBg4aDamJKypRQWW1Ca2kSV8 -p X -l scratchpad.bin -k http://url_to_server/download/scratchpad.bin
```

OpenCL specific options:
```
-d N - start OpenCL device to use (default: 0)
-i N - OpenCL work intensity (default: 18)
```

To mine on 2nd GPU only more intensive:
```
minerd -a wildkeccak_ocl -d 1 -t 1 -i 22 ...
```

To mine on CPU (algorithm from original fork):
```
minerd -a wildkeccak ... 
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

Credits
=======
CPUMiner-Multi-OpenCL was forked from Cryptozoidberg's cpuminer-multi, and has been developed by Mikhail Kuperman (mbk.git@gmail.com).

License
=======
GPLv2.  See COPYING for details.
