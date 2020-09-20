
## Refer


## 1) AMB contracts deployment
https://docs.tokenbridge.net/amb-bridge/arbitrary-message-bridge-deployment/1-amb-contracts-deployment

### amb.config

#### deploy Home bridge and Forgin bridge

docker run -it --env-file amb.config poanetwork/tokenbridge-contracts deploy.sh


## 2) Deploy ERC20 to ERC677 AMB bridge extension

https://docs.tokenbridge.net/eth-xdai-amb-bridge/erc20-to-erc20-extension-linked-with-a-particular-token/deploy-erc20-erc677-erc827-to-erc677-amb-bridge-extension

erc-to-erc.config

  ERC20_TOKEN_ADDRESS=0x41c16473b12211892c813f52815f700440471aa0

  HOME_AMB_BRIDGE=0x57337AD2A20E9f6c291B0f6dd082d6f5508e29ee

  FOREIGN_AMB_BRIDGE=0x91042E6DDc04D02a6216476c233AA036eb59916F

docker run -ti --rm --env-file erc-to-erc.config poanetwork/tokenbridge-contracts:latest deploy.sh