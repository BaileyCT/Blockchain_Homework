# README

<br/>

# Launching POA Blockchain 
<br/>

## Requirements 

<br/>

### To operate and set up the blockchain you will need to have the following downloaded.
- [Go Ethereum](https://geth.ethereum.org/)
- [MyCrypto Wallet](https://download.mycrypto.com/)
- [Test Ethereum](https://faucet.ropsten.be/)

<br/>

## Setup
Once you have downloaded and installed the following items you will need to start by setting up you nodes. Enter the following line of code to create your first node 
<br/>
```
./geth --datadir node1 account new
```
This will create the first node and give us the address of that node for us. Copy the address given then run the following 
```
./geth --datadir node1 account new
```
With addresses for both node 1 and 2 we can begin creating the genisis block for our new blockchain. To begin clear your terminal with 
```
clear
```
Navigate to the downloaded geth tools folder and run the following code 
```
./puppeth
```
this will open the creation tool where we can create the first block in our Proof of Authority blockchain. Once open you will use th numbers 1, 2, 3, 4 to select options when setting up this blockchain. Below is the exact steps used to set up the network. 

![puppeth setup](/Screenshots/Genisis.png)

 **Make sure** you add the node address you created in place of the ones I have. 

<br/>
With our genisis block created we can now launch our blockchain network by initalizing both nodes. we can exit the genisis creation by hiting control x if you are on a mac. 

<br/>
<br/>

to initalize node one please enter the following.
```
./geth --datadir node1 init networkname.json
```
Network name will refere to the name you gave when creating the block. please do the same with node 2 

```
./geth --datadir node2 init networkname.json
```

Once both are set up we can begin running the nodes. to do so we will need the address of the first node and to enter the following
```
./geth --datadir node1 --unlock "SEALER_ONE_ADDRESS" --mine --rpc --allow-insecure-unlock
```
where *Sealer_ONE_ADDRESS* referess to your node 1 address. you will then see the following 

```
enode://9fed5c60f80965ec8a3a62abac06580940694d296820a9b15810d0b710d83e92fa2782940451bd001db8b4e076ea64a50f15ecdaade8cb6aa1a3bd1625ff5c95@127.0.0.1:30303
```
Copy that enode address as it will be used to to connect node 2. Open a second tab on Gitbash or terminal and enter the following. 

```
./geth --datadir node2 --unlock "SEALER_TWO_ADDRESS" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock
```
Similarly the sealer two address refers to the node 2 address from earlier. Take the enode address we copied and enter that into the quoted section and **BOOM** you have started a blockchain network! 

<br/>

With our blockchain running we can open MyCrypto and begin setting up our two addresses and complete a transaction. Open MyCrypto and in the bottom right hand corner select change your network. Below is an example of this set up.

 **Ignore the warnings as I have already deployed**

![mycrypto Set up](/Screenshots/Mycrypto.png)
<br/>
Once the network is connected at the bottom of the window there is an option to connect to an address with a keystore file. Navigate to the folder housing your first node. open it and select the Keystore file. it will also ask you for the password you created when opening the node enter that. 

<br/>

We are now ready to send a transaction! You should have some funding availible from setting up the block, if not please copy your address and navigate to [Test Ethereum](https://faucet.ropsten.be/). This faucet will take your wallet address and deposit some test ETH. 

<br/> Now that we have ETH and a network set up we can now send a transaction. Copy your node 2 address into the "To Adress" section and enter the ammount you would like to send. hit send and you should be taken to a pending confirmation screen. When the transaction is sent it will change to confirm and look like this.
 
![Confirmation](/Screenshots/Transaction.png)
