# First Truffle Project

https://blog.ippon.tech/creating-your-first-truffle-project-part-1-of-2/

Modifications

- Specifies MNEMONIC in package.json
- ganache-cli -h 0.0.0.0


## Install packages

Assume ganache-cli and truffle installed globally

```
yarn install
```

## Test Ganache

Run ganache-cli

```bash
MNEMONIC='kitten warrior chaos sight wedding rhythm repair dawn also obvious novel oppose'
ganache-cli -m $MNEMONIC -h 0.0.0.0
```

In separate terminal window:

```bash
curl http://127.0.0.1:8545 \
    -X POST \
    -H "Content-Type: application/json" \
    -d '{"jsonrpc": "2.0", "method": "web3_clientVersion"}'
```

## Truffle Init and Compile Contract

`truffle init` already done and files part of repo

```bash
truffle compile
```

## Run Ganache and Truffle

Run and deploy smart contract

```bash
npm run start
```

Look up transaction based off transactionHash


```bash
curl -X POST --data '{"jsonrpc":"2.0","method":"eth_getCode","params":["0x28207143bE38F223088268D21c721A3E49A3d967", "latest"],"id":1}' localhost:8545

{"id":1,"jsonrpc":"2.0","result":"0x608060405234801561001057600080fd5b50600436106100415760003560e01c8063445df0ac146100465780638da5cb5b14610064578063fdacd576146100ae575b600080fd5b61004e6100dc565b6040518082815260200191505060405180910390f35b61006c6100e2565b604051808273ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200191505060405180910390f35b6100da600480360360208110156100c457600080fd5b8101908080359060200190929190505050610107565b005b60015481565b6000809054906101000a900473ffffffffffffffffffffffffffffffffffffffff1681565b6000809054906101000a900473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff163373ffffffffffffffffffffffffffffffffffffffff16146101ac576040517f08c379a00000000000000000000000000000000000000000000000000000000081526004018080602001828103825260338152602001806101b76033913960400191505060405180910390fd5b806001819055505056fe546869732066756e6374696f6e206973207265737472696374656420746f2074686520636f6e74726163742773206f776e6572a265627a7a72315820ea444141d6a776ead153a112336a3aeae9934d9175884755fcef09babccb19bf64736f6c63430005100032"}%  
```

