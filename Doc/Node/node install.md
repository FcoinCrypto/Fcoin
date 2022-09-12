Tutorial - Install a node on Ubuntu Server 18.04
Install a node on Ubuntu Server 18.04 with the following tutorial.

Update your Ubuntu server with the following command:

sudo apt-get update && sudo apt-get upgrade -y

Install the required dependencies with the following command:

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3 libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-test-dev libboost-thread-dev libboost-all-dev libboost-program-options-dev -y

Install the additional dependencies with the following command:

sudo apt-get install libminiupnpc-dev libzmq3-dev libprotobuf-dev protobuf-compiler unzip software-properties-common libkrb5-dev mongodb nodejs npm git nano cmake screen -y

Install the repository ppa:bitcoin/bitcoin with the following command:

sudo add-apt-repository ppa:bitcoin/bitcoin

Confirm the installation of the repository by pressing on the enter key. enter

Install Berkeley DB with the following command:

sudo apt-get update && sudo apt-get install libdb4.8-dev libdb4.8++-dev -y

Download the Linux daemon for your wallet with the following command:


wget https://fcoincrypto.com/download/linux/fcoin-daemon-linux.tar.gz

Extract the tar file with the following command:

tar -xzvf fcoin-daemon-linux.tar.gz

Download the Linux tools for your wallet with the following command:

wget https://fcoincrypto.com/download/linux/fcoin-qt-linux.tar.gz

Extract the tar file with the following command:

tar -xzvf fcoin-qt-linux.tar.gz

Type the following command to install the daemon and tools for your wallet:

sudo mv fcoind fcoin-cli fcoin-tx /usr/bin/

Type the following command to open your home directory:

cd $HOME

Create the data directory for your coin with the following command:

mkdir $HOME/.fcoin

Open nano.

nano $HOME/.fcoin/fcoin.conf -t

Paste the following text into nano.

rpcuser=rpc_fcoin
rpcpassword=dR2oBQ3K1zYMZQtJFZeAerhWxaJ5Lqeq9J2
rpcbind=0.0.0.0
rpcallowip=127.0.0.1
listen=1
server=1
txindex=1
daemon=1
addnode=dns1.fcoincrypto.com
addnode=dns2.fcoincrypto.com

Save the file with the keyboard shortcut ctrl + x.

Type the following command to start your daemon:

fcoind