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
 
 ## 6. 开启挖矿

 ``
 geth  --mine --miner.threads=2 --datadir ./node3 --identity "Metasverse Chain" --networkid 348972 --bootnodes "enode://cb1e85fa581c7bb4ac6606e3f5eb51f8231c859444a8b393f2f4b8e9b1533abf9c0bf5b2bb2c9bc78468aac855718f9faab81ea8fe6ea0112bf2aa81021d2f63@106.52.241.128:8087" console
 ``
 ### 后台运行
 
 ``
 nohup geth  --mine --miner.threads=2 --datadir ./node3 --identity "Metasverse Chain" --networkid 348972 --bootnodes "enode://cb1e85fa581c7bb4ac6606e3f5eb51f8231c859444a8b393f2f4b8e9b1533abf9c0bf5b2bb2c9bc78468aac855718f9faab81ea8fe6ea0112bf2aa81021d2f63@106.52.241.128:8087" >> logs.out &
 ``
