# New_ethereum_private_chain
* initialize -讀取genesis.json並初始化私有鏈
```shell=
geth --datadir ./data/ init genesis.json
```

* with web socket(新版本 ～for 1.19)

```shell=
geth --datadir data --networkid 33 --ws --ws.addr "0.0.0.0" --ws.api "eth,web3,personal,debug,admin,miner,net,shh,txpool" --ws.port 8546 --ws.origins "*" --http --shh --http.port 8545 --http.corsdomain "*" --http.api  "eth,web3,personal,debug,admin,miner,net,shh,txpool" --allow-insecure-unlock  --nodiscover console
```


* 輕節點with web socket(新版本 ～for 1.19)

```shell=
geth --datadir data --networkid 33 --ws --ws.addr "0.0.0.0" --ws.api "eth,web3,personal,debug,admin,miner,net,shh,txpool" --syncmode="light" --ws.port 8546 --ws.origins "*" --http --shh --http.port 8545 --http.corsdomain "*" --http.api  "eth,web3,personal,debug,admin,miner,net,shh,txpool" --allow-insecure-unlock --nodiscover console
```

* 另一個終端機連綫至geth
```
 geth attach http://localhost:8545
```

* 新增account(EoA) - 同時設定密碼
```
personal.newAccount("password")

```


* 以靜態方式新增聯盟鏈
1. 在geth資料所在資料夾.data/geth内新增`static-nodes.json`檔案，檔案内容如下
```
[
"enode://980c65fc0e907e55aa1b206986b6b4988894e2a811f9f6b844e0eefbdf8e713d3c0243ebe910ca71a1d6441ecf660558913688b28ab4095e5aaccf23c2664e03@140.119.163.196:30303?discport=0"
]
```


