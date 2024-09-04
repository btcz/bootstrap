# Bootstrap.dat


**bootstrap.dat** allows a new BitcoinZ client (not synced) to rapidly import the initial blocks from a local file instead of slowly downloading blocks from random peers. This significantly reduces the time it takes to get a client synced with the current blockchain.

Simply having bootstrap.dat in BitcoinZ's expected data directory will make your initial block sync much faster. The import process can be even faster if you use the -dbcache=1000 command line parameter which uses an additional 1GB of RAM for the database index cache. BitcoinZ v2.0.10+ with ZHash PoW validation can make import even faster if you have SSD drives.

## Overview
Regardless of your operating system use the following steps to make use of the bootstrap.dat file:

1. Download bootstrap.dat.7z from github.
2. Verify the integrity of bootstrap.dat.7z with the checksums.
3. Decompress to obtain bootstrap.dat.
4. Put it into the BitcoinZ datadir.  This is the same folder that contains wallet.dat and the blocks folder.
5. Delete bootstrap.dat.old if you want to recover some storage space.

## Download bootstrap.dat
You can download bootstrap.dat from the following location:

**github:**
[bootstrap.dat.7z.001](https://github.com/btcz/bootstrap/releases/download/2024-09-04/bootstrap.dat.7z.001)
[bootstrap.dat.7z.002](https://github.com/btcz/bootstrap/releases/download/2024-09-04/bootstrap.dat.7z.002)
[bootstrap.dat.7z.003](https://github.com/btcz/bootstrap/releases/download/2024-09-04/bootstrap.dat.7z.003)
[bootstrap.dat.7z.004](https://github.com/btcz/bootstrap/releases/download/2024-09-04/bootstrap.dat.7z.004)

## Verify integrity (SHA256)
- 7ccef0dd7d3090fd3424bad0cc368901a92217ad190eb81817686fae1bf6943f  bootstrap.dat.7z.001
- 4d04d24b02af9bec30f072bb845f21b1dc165387e0d365a76982104e61f89376  bootstrap.dat.7z.002
- 0db5bed761b9aa5f7c36f564395dcbc50d6dc6c839f367efc182d8f93df2e5a0  bootstrap.dat.7z.003
- 7c1d70908fbb063df2cc909e487cec2bba9b5eb9c767c92d2427abd897fd5bb5  bootstrap.dat.7z.004

## Extract bootstrap.dat
**Linux**: ```7z e bootstrap.dat.7z.001```

**Mac**: You can obtain xz from MacPorts or [http://macpkg.sourceforge.net/](http://macpkg.sourceforge.net/).

**Windows**: [7Zip](http://www.7-zip.org/) is a free utility that can decompress .7z files. The latest version of [WinRAR](http://www.rarlabs.com/download.htm) also supports .7z files.

## Copy bootstrap.dat to data directory
Copy **bootstrap.dat** to your data directory. After BitcoinZ has used bootstrap.dat, the file will be renamed to bootstrap.dat.old; at this point you can choose to delete it or keep it.

**Linux**: BitcoinZ's data directory is located in ```~/.bitcoinz/``` by default. You can run ```ls -a``` to see directories that start with a dot.
You can also search for the directory with the following command: ```find / -name wallet.dat -print 2>/dev/null```

**Mac**: BitcoinZ's data directory should be located in ```~/Library/Application Support/BitcoinZ/```.

**Windows**: Go to ```Start>Run``` (or press ```WinKey+R```) and run: ```explorer %APPDATA%\BitcoinZ```
BitcoinZ's data directory will open. "AppData" and "Application Data" are hidden by default in Windows.

## Data directory location
Operating system | Default data directory location | Typical path to configuration file
-----------------|---------------------------------|-----------------------------------
Linux | $HOME/.bitcoinz/ | /home/\<username\>/.bitcoinz/bitcoinz.conf
Mac | $HOME/Library/Application Support/BitcoinZ/ | /Users/\<username\>/Library/Application Support/BitcoinZ/bitcoinz.conf
Windows | %APPDATA%\\BitcoinZ\\ | C:\\Users\\\<username\>\\AppData\\Roaming\\BitcoinZ\\bitcoinz.conf
