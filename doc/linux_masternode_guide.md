Basic Masternode guide Linux

first we will install Build dependencies:

Build requirements:

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git
sudo apt-get install libboost-all-dev
sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
sudo add-apt-repository ppa:bitcoin/bitcoin
sudo apt-get update
sudo apt-get install libdb4.8-dev libdb4.8++-dev
sudo apt-get install libminiupnpc-dev

ZMQ dependencies:

sudo apt-get install libzmq3-dev (provides ZMQ API 4.x)

Now lets start:

Download yotokens  github source:


git clone https://github.com/yotokens/yotokens.git

Now we are going to compile the Client:

chmod a+x+w -R yotokens/
cd yotokens
./autogen.sh
./configure
make
make install

Now lets run the yotokens daemon:

yotokensd &
press enter


We need to create our masternode Private Key.

yotokens-cli masternode genkey

copy the generated code to a text file

Now we need our yotokens address:

yotokens-cli getaccountaddress 0

copy the generated address to a text file

Send 50000 yotokens to "address 0"

go to yotokens.conf in

./root/.yotokens/

Paste this (dont forget to set rpcuser and password)


rpcuser=<anything>
rpcpassword=<anything>
maxconnections=256
listen=1
server=1
daemon=1
staking=1
masternode=1
masternodeprivkey=XXXXXXXXXXXXXXXXXX (paste the key you generated with the command masternode genkey)
masternodeaddr=xxx.xxx.xxx.xxx:55606



save and close config file.

Now open 

 /root/.yotokens/masternode.conf


---Format: alias IP:port masternodeprivkey collateral_output_txid collateral_output_index

Quote
mn1 127.0.0.1:16555 93HaYBVUCYjEMeeH1Y4sBGLALQZE1Yc1K64xiqgX37tGBDQL8Xg 2bcd3c84c84f87eaa86e4e56834c92927a07f9e18718810b92e0d0324456a67c 0

set up your ip, masternode privkey, and TXID (of the 50000 yotokens)


now shutdown yotokens process and restart it

lets list all proccesses:

ps ax

find the proccess number


kill (process number)

now restart yotokensd

and lets start it again:

yotokensd &


Now let check our masternode status:

yotokens-cli masternode status

it will display if your wallet is masternode capable. if it does, just use command:  

masternode start

wait 10 seconds and use the command : yotokens-cli masternode list  (it should display a list of masternodes, check that your masternode is on the list).
