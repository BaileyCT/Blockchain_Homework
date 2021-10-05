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
