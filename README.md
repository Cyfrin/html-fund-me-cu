# html-fund-me-cu

*[⭐️ (2:37:02) | Lesson 8: HTML Fund Me](https://www.youtube.com/watch?v=sas02qSFZ74&t=9422s)*

This is a minimalistic example what you can find in the [metamask docs](https://docs.metamask.io/guide/create-dapp.html#basic-action-part-1).

- [html-fund-me-cu](#html-fund-me-cu)
- [Requirements](#requirements)
    - [Optional Gitpod](#optional-gitpod)
- [Quickstart](#quickstart)
  - [Execute a transaction - Local EVM](#execute-a-transaction---local-evm)
  - [Execute a transaction - zkSync](#execute-a-transaction---zksync)
- [Thank you!](#thank-you)


# Requirements

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  - You'll know you've installed it right if you can run:
    - `git --version`
- [Metamask](https://metamask.io/)
  - This is a browser extension that lets you interact with the blockchain.

### Optional Gitpod

If you can't or don't want to run and install locally, you can work with this repo in Gitpod. If you do this, you can skip the `clone this repo` part.

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#github.com/PatrickAlphaC/html-fund-me-cu)

# Quickstart 

1. Clone the repo

```
git clone https://github.com/Cyfrin/html-fund-me-cu
cd html-fund-me-cu
```

2. Run the `index.html` file

You can usually just double click the file to "run it in the browser". Or you can right click the file in your VSCode and run "open with live server" if you have the live server VSCode extension (ritwickdey.LiveServer).

And you should see a small button that says "connect".

![Connect](connect.png)

Hit it, and you should see metamask pop up.

## Execute a transaction - Local EVM

If you want to execute a transaction follow this, you'll need to setup a chain. We have support for both foundry and moccasin. 

> Foundry

1. You'll need to open up a second terminal and run:

```
git clone https://github.com/Cyfrin/foundry-fund-me-cu
cd foundry-fund-me-cu
make build
make anvil
```

Then, in a second terminal
```
make deploy
```

> Moccasin

Or, if you use [moccasin](https://github.com/Cyfrin/moccasin), you can run 
```
git clone https://github.com/Cyfrin/buy-me-a-coffee-cu
cd buy-me-a-coffee-cu
anvil
```

Then, in a second terminal
```
mox run deploy --network anvil
```

This will deploy a sample contract and start a local hardhat blockchain. 

After you've deployed with either foundry or moccasin, you can should then:

2. Update your `constants.js` with the new contract address.

In your `constants.js` file, update the variable `contractAddress` with the address of the deployed "FundMe" contract. You'll see it near the top of the hardhat output.

3. Connect your [metamask](https://metamask.io/) to your local hardhat blockchain.

> **PLEASE USE A METAMASK ACCOUNT THAT ISNT ASSOCIATED WITH ANY REAL MONEY.**
> I usually use a few different browser profiles to separate my metamasks easily.

In the output of the above command, take one of the private key accounts and [import it into your metamask.](https://metamask.zendesk.com/hc/en-us/articles/360015489331-How-to-import-an-Account)

Additionally, add your localhost with chainid 31337 to your metamask.

4. Refresh the front end, input an amount in the text box, and hit `fund` button after connecting

## Execute a transaction - zkSync

If you want to execute a transaction follow this:

> Foundry

1. Open up the `foundry-fund-me-f23` repo, and run a local zkSync node.

> [!IMPORTANT]  
> Be sure to go to the repo and follow the install/requirements instructions. The zkSync environment has different requirements to deploy/setup/etc.

```
git clone https://github.com/Cyfrin/foundry-fund-me-f23
cd foundry-fund-me-f23
make zkbuild
npx zksync-cli dev start
```

This will setup a docker instance of a local zkSync node. 

Then, run:
```
make deploy-zk
```

This will deploy a sample contract and start a local zkSync node.

> Moccasin

Or, if you use [moccasin](https://github.com/Cyfrin/moccasin), you can run 
```
git clone https://github.com/Cyfrin/buy-me-a-coffee-cu
cd buy-me-a-coffee-cu
anvil-zksync
```

Then, in a second terminal
```
just deploy-zk
```

1. Update your `constants.js` with the new contract address.

In your `constants.js` file, update the variable `contractAddress` with the address of the deployed "FundMe" contract. You'll see it after you run `make deploy-zk`.

2. Connect your [metamask](https://metamask.io/) to your local zkSync blockchain.

> [IMPORTANT] **PLEASE USE A METAMASK ACCOUNT THAT ISNT ASSOCIATED WITH ANY REAL MONEY.**
> I usually use a few different browser profiles to separate my Metamasks easily.

Import the `DEFAULT_ZKSYNC_LOCAL_KEY` from the `Makefile` of the `foundry-fund-me-f23` repo and [import it into your metamask.](https://metamask.zendesk.com/hc/en-us/articles/360015489331-How-to-import-an-Account)

Additionally, add your zkSync node with chainid `260` to your metamask.

3. Refresh the front end, input an amount in the text box, and hit `fund` button after connecting

# Thank you!

If you appreciated this, feel free to follow me or donate!

ETH/Arbitrum/Optimism/Polygon/etc Address: 0x9680201d9c93d65a3603d2088d125e955c73BD65

[![Patrick Collins Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/PatrickAlphaC)
[![Patrick Collins YouTube](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/channel/UCn-3f8tw_E1jZvhuHatROwA)
[![Patrick Collins Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/patrickalphac/)
[![Patrick Collins Medium](https://img.shields.io/badge/Medium-000000?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@patrick.collins_58673/)
