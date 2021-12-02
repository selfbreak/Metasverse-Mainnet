# Metasverse-Mainnet 搭建步骤

## 1.根据自己服务器类型安装geth

https://geth.ethereum.org/docs/install-and-build/installing-geth

## 2.添加节点文件夹，确保空间足够（50G以上）

``
mkdir node && cd node
``

## 3.在node目录新增 genesis.json 创世区块文件，内容为 ：

```json
{
  "config": {
    "chainId": 348972,
    "homesteadBlock": 0,
    "eip150Block": 0,
    "eip150Hash": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "eip155Block": 0,
    "eip158Block": 0,
    "byzantiumBlock": 0,
    "constantinopleBlock": 0,
    "petersburgBlock": 0,
    "istanbulBlock": 0,
    "ethash": {}
  },
  "nonce": "0x0",
  "timestamp": "0x61a0c29b",
  "extraData": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "gasLimit": "0x47b760",
  "difficulty": "0x80000",
  "mixHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "coinbase": "0x0000000000000000000000000000000000000000",
  "alloc": {
    "0000000000000000000000000000000000000000": {
      "balance": "0x1"
    },       
    "2000000000000000000000000000000000000000": {
      "balance": "0x200000000000000000000000000000000000000000000000000000000000000"
    },
    "dd6280a1289797d426023d6ee45ed68bcb9623e7": {
      "balance": "0x200000000000000000000000000000000000000000000000000000000000000"
    }
  },
  "number": "0x0",
  "gasUsed": "0x0",
  "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "baseFeePerGas": null
}
```


## 4.创建一个初始挖矿账号


 ``
 geth --datadir ./node account new
 
 ``

## 5.初始化节点


 ``
 
 geth --datadir ./node init ./node/genesis.json
 
 ``
