# Running GCN on Ubuntu 20.04

## Server Requirements:

- Operating System: Ubuntu 20.04
- Type: Secured VPS 
- RAM: 8 Gigs RAM
- Cores: 4 Processing Core
- Disk: 100 GB SSD

## 1. Downloading and installing geth:

```sh
wget https://github.com/greatcryptonetwork/greatcryptonetwork/releases/download/v1.0/geth-alltools-linux-amd64.tar.xz && tar -xvf geth-alltools-linux-amd64.tar.xz && cd geth-alltools-linux-amd64 && cp * /usr/local/bin && cd ../ && rm -rf geth-alltools-linux-amd64 && rm geth-alltools-linux-amd64.tar.xz
```



## 2.1 Download MainNet Genesis File:
```sh
wget https://github.com/greatcryptonetwork/greatcryptonetwork/releases/download/v1.0/greatcryptonetwork.json
```


or (if running testnet)


## 2.2 Download TestNet Genesis File:
```sh
wget https://github.com/greatcryptonetwork/greatcryptonetwork/releases/download/v1.0/tngreatcryptonetwork.json
```



## 3.1 Initialising Data Directory for MainNet:
```sh
geth --datadir "/root/.greatcryptonetwork" init greatcryptonetwork.json
```


or (if running testnet)


## 3.2 Initialising Data Directory for TestNet:
```sh
geth --datadir "/root/.greatcryptonetworkTN" init tngreatcryptonetwork.json
```



## 4.1 Running GCN MainNet:
```sh
screen geth --datadir "/root/.greatcryptonetwork" --networkid 33619 --port 19204 --syncmode 'full' --bootnodes enode://39639ba1718c3af275709e78d26d68eb705b30ac97c3402a9368a7bd4c3a0c4077c4a364d9b779d9da90129a36f83e479fdafb4e9807910795e0ad495aeb4734@54.227.155.236:19204 2>>/home/ubuntu/.greatcryptonetwork/chain.log &
```

or (if running testnet)


## 4.2 Running GCN TestNet:
```sh
screen geth --datadir "/root/.greatcryptonetworkTN" --networkid 65527  --port 17898 --syncmode 'full' --bootnodes enode://cab0c3e4823be049d105ab435ea453ce321156672edfb3cca8601dec142b4a6822891b66bc3d2deedc4e3bf03eecbf26a24b87c0d7f93faeedcc820a3630ad48@44.218.36.31:17898 2>>/home/ubuntu/.greatcryptonetworkTN/chain.log &

```




### Web3 Documentation:

https://web3js.readthedocs.io/en/v1.2.2/getting-started.html#adding-web3-js


### RPC Documentation:

https://ethereum.github.io/execution-apis/api-documentation
