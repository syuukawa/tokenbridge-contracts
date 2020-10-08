
## 调用流程

contracts/upgradeable_contracts/amb_native_to_erc20/callflows.md

## 部署流程
1. 生成测试用以太地址并申请测试代币 ETH，ELA
2. AMB contracts deployment


## 1.AMB contracts deployment

https://docs.tokenbridge.net/amb-bridge/arbitrary-message-bridge-deployment/1-amb-contracts-deployment

1. 修改配置文件 amb3.config
   DEPLOYMENT_ACCOUNT_PRIVATE_KEY=<DEPLOYMENT_ACCOUNT_PRIVATE_KEY>

    HOME_RPC_URL=https://<url.to.homenet>
    HOME_BRIDGE_OWNER=<HOME_BRIDGE_OWNER>
    HOME_VALIDATORS_OWNER=<HOME_VALIDATORS_OWNER>
    HOME_UPGRADEABLE_ADMIN=<HOME_UPGRADEABLE_ADMIN>

    FOREIGN_RPC_URL=https://<url.to.foreignnet>
    FOREIGN_BRIDGE_OWNER=<FOREIGN_BRIDGE_OWNER>
    FOREIGN_VALIDATORS_OWNER=<FOREIGN_VALIDATORS_OWNER>
    FOREIGN_UPGRADEABLE_ADMIN=<FOREIGN_UPGRADEABLE_ADMIN>

    VALIDATORS=<address of validator>

2. 执行命令    
    docker run -it --env-file amb3.config poanetwork/tokenbridge-contracts deploy.sh


## 2.TokenBridge oracle instances 

https://docs.tokenbridge.net/amb-bridge/arbitrary-message-bridge-deployment/2-tokenbridge-oracle-instance


1. /Users/zhouhe/blockchain/tokenbridge/tokenbridge 

2. ssh root@47.104.94.253


ansible-playbook -e 'ansible_python_interpreter=/usr/bin/python3' -i hosts_ali3.yml site.yml


## 3.Deploy ERC20 to ERC677 AMB bridge extension - AMB_ERC_TO_ERC

https://docs.tokenbridge.net/eth-xdai-amb-bridge/erc20-to-erc20-extension-linked-with-a-particular-token/deploy-erc20-erc677-erc827-to-erc677-amb-bridge-extension


1. 修改配置文件 erc-to-erc3.config
    DEPLOYMENT_ACCOUNT_PRIVATE_KEY=abc0123...6789def

2. 执行命令
    docker run -ti --rm --env-file erc-to-erc3.config poanetwork/tokenbridge-contracts:latest deploy.sh


## 确认部署的Home和Bridge的合约地址，有时候一致，有时候不一致。

## wallet/.env

REACT_APP_INFURA_KEY=945c07d86744491cb15c4547227b2dfa
REACT_APP_PK=

##  wallet

1. token address
   address: '0xeE7fAf1227aFb0668f339A849dcf01648f41671f' //token contract address

2. sUSDBridge.ts
// Mediator contract address at the Sokol
const homeMediatorAddress = ''
// Mediator contract at the Ethereum Kovan
const foreignMediatorAddress = ''

3. node_modules/@burner-wallet/core/gateways/XDaiGateway.js
   
   Web3.providers.HttpProvider('https://rpc.elaeth.io')

   getNetworks ===> 3


yarn run start-wallet

## Logs

/var/log/docker/


sudo docker cp a7d78b68c697:/mono/oracle/src/events/processAMBAffirmationRequests/estimateGas.js /var/oracle/
sudo docker cp a7d78b68c697:/mono/oracle/src/events/processAMBAffirmationRequests/estimateGas.js /var/oracle/tmp/

sudo docker cp  /var/oracle/estimateGas.js  a7d78b68c697:/mono/oracle/src/events/processAMBAffirmationRequests/



sudo docker cp  750cc20d8cc3:/mono/oracle/src/confirmRelay.js /var/oracle/
sudo docker cp  750cc20d8cc3:/mono/oracle/src/confirmRelay.js /var/oracle/tmp
sudo docker cp  /var/oracle/confirmRelay.js  750cc20d8cc3:/mono/oracle/src/


sudo docker cp  750cc20d8cc3:/mono/oracle/src/sender.js /var/oracle/
sudo docker cp  750cc20d8cc3:/mono/oracle/src/sender.js /var/oracle/tmp

sudo docker cp  /var/oracle/sender.js  750cc20d8cc3:/mono/oracle/src/

sudo docker cp  4fe5094e28e2:/mono/oracle/src/tx/sendTx.js /var/oracle/
sudo docker cp  4fe5094e28e2:/mono/oracle/src/tx/sendTx.js /var/oracle/tmp

sudo docker cp  /var/oracle/sendTx.js  4fe5094e28e2:/mono/oracle/src/tx/


## ERROR

1. estimateGas.js

{"level":50,"time":1601188803932,"msg":"Unknown error while processing transaction","validator":"0x4456D699Fb0b98350A910B912c6fA035148b1b6F","name":"watcher-amb-affirmation-request","eventTransactionHash":"0x0da41850f6c00306b4e0633213cf7020778810d2f011834dd9bdd922d3333738","eventMessageId":"0x00050000b685177733b285b2e6659dcc3e87c407abc151a10000000000000000","type":"Error","stack":"Error: Unknown error while processing message\n    at estimateGas (/mono/oracle/src/events/processAMBAffirmationRequests/estimateGas.js:56:11)\n    at process._tickCallback (internal/process/next_tick.js:68:7)","v":1}
Sep 27 14:40:03 alibridge oracle_bridge_affirmation_1/a7d78b68c697[12256]: {"level":50,"time":1601188803932,"msg":"Unknown error while processing message","validator":"0x4456D699Fb0b98350A910B912c6fA035148b1b6F","name":"watcher-amb-affirmation-request","type":"Error","stack":"Error: Unknown error while processing message\n    at estimateGas (/mono/oracle/src/events/processAMBAffirmationRequests/estimateGas.js:56:11)\n    at process._tickCallback (internal/process/next_tick.js:68:7)","v":1}


## mod
1. estimateGas

sudo docker cp 0bc85b4a37ff:/mono/oracle/src/events/processAMBAffirmationRequests/estimateGas.js /var/oracle/
sudo docker cp 0bc85b4a37ff:/mono/oracle/src/events/processAMBAffirmationRequests/estimateGas.js /var/oracle/tmp/

sudo docker cp  /var/oracle/estimateGas.js  0bc85b4a37ff:/mono/oracle/src/events/processAMBAffirmationRequests/




web3.sha3('transferProxyOwnership(address)')
"0xf1739caeec2558ea1e0b25390f37491d4c782f305ec643c3f9ef9ba4cd9e7dca"

web3.sha3('upgradeTo(uint256, address)')
0x3ad06d16


web3.sha3('upgradeTo(uint256, address)')

https://testnet.elaeth.io/tx/0xb87666305c34de57194c7a2aa1e7a9b88ef6aea5be961f57d6dd9ed7b8e174ce/internal_transactions 

[{"type":"function","stateMutability":"nonpayable","payable":false,"outputs":[],"name":"upgradeTo","inputs":[{"type":"uint256","name":"version"},{"type":"address","name":"implementation"}],"constant":false},

web3.sha3('upgradeTo(uint256,address)')
"0x3ad06d16a939048cae4c581e2ca020e8cc88731d059c2d51de2eb2df3dc0d9c4"


https://blockscout.com/poa/sokol/tx/0xbbb5651725db2428949038c40e3fd327d414064dbd103396e796e2b320a1fa6b/token-transfers

Method Id 0xe7a2c01f
Call      executeAffirmation(bytes message)

https://testnet.elaeth.io/tx/0x7359bb619d1056c6aec5e6d27a77e8965925af0d6438d51b700529171efb5695/internal_transactions

0xe7a2c01f0000000000000000000000000000000000000000000000000000000000000020000000000000000000000000000000000000000000000000000000000000009500050000b47b921f0ad0436a429993cdc56b46c441d7ac5700000000000000026307e265f22f6916492824c8cc963404debdbb73f35bec0416f261d4acdbbe6f8f65ee708ec1f2600007a1200101002a038b6c0354000000000000000000000000b3a0dd42d027623b0ad2ebba2300a2ffd69ec1780000000000000000000000000000000000000000000000000de0b6b3a76400000000000000000000000000


web3.sha3('executeAffirmation(bytes)')
"0xe7a2c01f4442851c685b263904e2d6e0a2757fb7f7af0cae0dc6ce3e601aa8b8"


0x3ad06d16
0000000000000000000000000000000000000000000000000000000000000001
0000000000000000000000007b0957f2f288af1b26e500c6995e13870deb5c6f

0xe7a2c01f
0000000000000000000000000000000000000000000000000000000000000020
0000000000000000000000000000000000000000000000000000000000000095
00050000b47b921f0ad0436a429993cdc56b46c441d7ac5700000000000000026307e265f22f6916492824c8cc963404debdbb73f35bec0416f261d4acdbbe6f8f65ee708ec1f2600007a1200101002a038b6c0354000000000000000000000000b3a0dd42d027623b0ad2ebba2300a2ffd69ec1780000000000000000000000000000000000000000000000000de0b6b3a76400000000000000000000000000

0xe7a2c01f
0000000000000000000000000000000000000000000000000000000000000020
0000000000000000000000000000000000000000000000000000000000000095
00050000594dc5ccfc633c6c1b4e6801bd87cb05b675235a000000000000000a9952b09216320f85aecc0caaf48fee4705f423c7f5975aace8673ee3a303eb585733d9bdcf9ed6d70007a1200101002a4d8b6c0354000000000000000000000000e0106c5a09e74646c744fcfe309fcddbc39804a300000000000000000000000000000000000000000000000029a2241af62c00000000000000000000000000

0xe7a2c01f
0000000000000000000000000000000000000000000000000000000000000020
0000000000000000000000000000000000000000000000000000000000000095
00050000b47b921f0ad0436a429993cdc56b46c441d7ac5700000000000000026307e265f22f6916492824c8cc963404debdbb73f35bec0416f261d4acdbbe6f8f65ee708ec1f2600007a1200101002a038b6c0354000000000000000000000000b3a0dd42d027623b0ad2ebba2300a2ffd69ec1780000000000000000000000000000000000000000000000000de0b6b3a76400000000000000000000000000




nohup ./geth --datadir /root/eth/data \
            —lightserv 1 \
            --rpc --rpcvhosts '*' --rpcaddr "0.0.0.0" \
            --rpcapi "eth,web3,admin,txpool" \
            >>/root/eth/logs/geth.log 2>&1 &


/root/ela/elastos-eth-v0.1.0



curl -X POST --data '{"jsonrpc":"2.0","method":"eth_blockNumber","params":[],"id":67}' http://118.190.57.207:8545 -H "content-type: application/json" 


curl -X POST --data '{"jsonrpc":"2.0","method":"eth_blockNumber","params":[],"id":67}' http://118.190.57.207:8545 -H "content-type: application/json"


pm2 start --name testnet-geth -x ./geth -- --syncmode "full" --gcmode "archive" --rpc --rpcaddr "0.0.0.0" --rpcport "8545" --rpcapi "eth,admin,web3,net,debug,personal,txpool" --rpccorsdomain "*" -rpcvhosts="*" --nousb --ws --wsaddr "0.0.0.0" --wsport "8546" --wsorigins "*" --testnet --datadir "./data"



wget -r -p -np -k https://download.elastos.org/elastos-eth/elastos-eth-v0.1.1/elastos-eth-v0.1.1-linux-x86_64.tgz


tar -zxvf 