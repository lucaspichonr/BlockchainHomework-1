Steps

Installations:
Install Go Ethereum tools by going to https://geth.ethereum.org/downloads/ and scrolling down to stable releases. You should download and install the Geth & Tools package.
Additionally, make sure to have a wallet such as MyCrypto installed. 


1) Create directories for the nodes
mkdir node1
mkdir node2

2) Create account numbers for the nodes so they can be used as signers:
./geth account new --datadir node1
./geth account new --datadir node2

3) Save the passwords generated for each node (123 in this case)

4) Save the addressses of the nodes 
node1:
Public address of the key:   0xCBc6b01d693aB36c738bC0Aa229804De586775D9
Path of the secret key file: node1\keystore\UTC--2021-09-02T23-59-29.343561900Z--cbc6b01d693ab36c738bc0aa229804de586775d9

node2:
Public address of the key:   0xEE37b545B1AaC65026A1fAaACc81bf29fcfEa8c7
Path of the secret key file: node2\keystore\UTC--2021-09-03T00-00-47.496183200Z--ee37b545b1aac65026a1faaacc81bf29fcfea8c7

5) Run puppeth: ./puppeth
network name: hwlucas
chain ID: 555

What would you like to do?: Configure new genesis ---> Create new genesis from scratch ---> Clique - Proof of Authority

6) Input the addresses from the nodes shared above and pre-fund them.

7) Pre-compile addresses with wei ---> yes

8) Specify a network ID (555 in this case)

9) Initialize the nodes
./geth init hwlucas.json --datadir node1
./geth init hwlucas.json --datadir node2

10) Start the mining for node1
./geth --datadir node1 --unlock "CBc6b01d693aB36c738bC0Aa229804De586775D9" --mine --miner.threads 1
Use '123' as the password

11) Start the mining for node2
./geth --datadir node2 --unlock "EE37b545B1AaC65026A1fAaACc81bf29fcfEa8c7" --port 30304 --rpc --bootnodes "enode://e1db2bf36b53c122f3fd3a37d31daee980f347a995d7877df42248e4f4091f768ec8a2f45bd07cd152d69e681da104acd06ec8bb0c802120194efc0187f2444e@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

12) Log in to your wallet (i.e MyCrypto) using a mnemonic phrase.

13) Connect to the correct network by setting up a custom node.

14) When setting the custom node, use the below details:
	Node name: hwlucas
	Network: Custom
	Network name: hwlucas
	Currency: ETH
	Chain ID: 555
	URL: http://127.0.0.1:8545

15) Once connected to the network, you can proceed and send transactions within the PoA blockchain.


























































