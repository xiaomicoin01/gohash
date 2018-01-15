gohash [GHC] CORE
================================

Specifications:
--------------

* PoW (proof of work) / PoS (proof of stake)
* Algorithms: Skein
* Blocktime: 60 seconds
* RPC port: 11446
* P2P port: 11445
* Blockreward (PoW):
  * Block 71 to 100 : 1 GHC
  * 100 to 10,000 : 10 GHC
  * 10,001 to 20,000: 8 GHC
  * 20,001 to 30,000: 6 GHC
  * 30,001 to 40,000: 4 GHC
  * 40,001 to 50,000: 2 GHC
  * Total PoW: 50,000 Blocks

* Blockreward (PoS):
  * Block 101 to 10,000 : 10 GHC
  * 10,001 to 20,000: 12 GHC
  * 20,001 to 30,000: 13 GHC
  * 30,001 to 40,000: 14 GHC
  * 40,001 to 50,000: 15 GHC
  * 50,001 to 100,000: 10 GHC
  * After 100,001: 8 GHC  

* Masternode Collaterial - 5 000 GHC.
* Masternodes Rewards - 75% of PoS Blocks.
* Diff Retarget: 5 Blocks
* Maturity: 30 Blocks
* Stake Minimum Age: 24 Hours
* 40 MegaByte Maximum Block Size (40X Bitcoin Core)


gohash includes an Address Index feature, based on the address index API (searchrawtransactions RPC command) implemented in Bitcoin Core but modified implementation to work with the GHC codebase (PoS coins maintain a txindex by default for instance).

Initialize the Address Index By Running with -reindexaddr Command Line Argument.  It may take 10-15 minutes to build the initial index.


Linux Build Instructions and Notes
==================================

Dependencies
----------------------
1.  Update packages

        sudo apt-get update

2.  Install required packagages

        sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
        sudo apt-get install libboost-all-dev git
        sudo apt-get install libminiupnpc-dev libgmp3-dev

3.  Install Berkeley DB 4.8

        sudo apt-get install software-properties-common
        sudo add-apt-repository ppa:bitcoin/bitcoin
        sudo apt-get update
        sudo apt-get install libdb4.8-dev libdb4.8++-dev


Build
----------------------
1.  Clone the source:

        git clone https://github.com/gohashcrypto/gohash/

2.  Build gohash:

    Configure and build.

        cd gohash
        cd src/
        make -f makefile.unix   



Masternode configuration is very similiar to other Masternodes coins.
----------------------

edit gohash.conf

      rpcuser=gohash
      rpcpassword=putyourpasswordhere
      rpcallowip=127.0.0.1
      rpcport=11446
      masternode=1
      masternodeaddr=192.168.0.1:11445
      port=11445
      masternodeprivkey=putyourkeyhere
      daemon=1

