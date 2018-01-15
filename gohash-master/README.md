gohash [GHC] CORE
================================

Specifications:
--------------

* PoW (proof of work) / PoS (proof of stake)
* Algorithms: Script
* Blocktime: 60 seconds
* RPC port: 11111
* P2P port: 11112
* Blockreward (PoW):
	101 - 500 Block - 1 GHC per Block
	501 - 10 000 Block - 8 GHC per Block
	10 001 - 30 000 Block - 7 GHC per Block
	30 001 - 60 000 Block - 6 GHC per Block
	60 001 - 80 000 Block - 5 GHC per Block
	80 001 - 120 000 Block - 2 GHC per Block
	After 240 001 - 8 GHC per Block
* Blockreward (PoS):
	501 - 10 000 Block - 8 GHC per Block
	10 001 - 30 000 Block - 9 GHC per Block
	30 001 - 60 000 Block - 10 GHC per Block
	60 001 - 80 000 Block - 11 GHC per Block
	80 001 - 120 000 Block - 12 GHC per Block
	120 001- 240 000 Block – 10 GHC per Block

* Masternode Collaterial - 5 000 GHC.
* Masternodes Rewards - 80% of PoS Blocks.
* Masternodes Activation: since block 500.
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

        git clone https://github.com/xiaomicoin01/gohash.git/gohash-master/

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

