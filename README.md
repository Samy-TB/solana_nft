
In this readme, 2 methods will be presented for you to be able to mint NFTs on Solana's blockchain.

<details><summary>METAPLEX STOREFRONT</summary>

<br>

# Metaplex Storefront
### This document will guide you on how to create your own storefront for you to mint your own NFTs
<br>

## Create your wallet
- First thing first, you will need to create a wallet. For this guide, we will use the Phantom Wallet. You can download the Phantom Wallet through this link : 


- https://phantom.app/download


- You can either have the web extension, the mobile application or both. All you need to do is download accordingly to your system. 

<br>

Once you have created your wallet, it is important to add some funds. Everything can be done with [Solfaucet](https://solfaucet.com/). A total of 10 SOL should be enough.

***Be careful, the maximum you can send to your wallet is 2 SOL per transaction and not 10 as mentionned on Solfaucet***

<br>

### The next steps can be directly found on the official Metaplex documentation : https://docs.metaplex.com/storefront/installation or you can follow this guide.

<br>

# Installation
## Requirements
- Make sure that your [Node.js](https://nodejs.org/en/download/) version is >= 14.17.0. You can check the version by executing `node -v`
- You will need [Yarn](https://classic.yarnpkg.com/en/). Yarn is a package manager for JavaScript and replaces `npm` client.

<br>


## Apple M1 Chip
#### If you have Mac OS with the Apple M1 Chip, you'll need to install some additional dependencies.
<br>

- [brew](https://brew.sh/)

<br>
After installing brew, run the following:

<br>

```bash
brew install pkg-config cairo pango libpng jpeg giflib librsvg
```
See additional information: https://github.com/Automattic/node-canvas/wiki/Installation%3A-Mac-OS-X
<br>
<br>

## Local setup
Clone the repo and install its dependencies.
```bash
git clone https://github.com/metaplex-foundation/metaplex.git
cd metaplex/js && yarn install && yarn bootstrap
```
Now run your store web server locally.
```bash
yarn start
```
After that you can open http://localhost:3000/ in your browser to see a storefront (it may take a minute to load the first time).

<br>

# Init store
## Setting up the Store ID
When opening a store for the first time you will be asked to connect your wallet. Click the Connect button and follow the steps to get connected.

![Connect your wallet](https://github.com/Samy-TB/storefront/blob/master/readme%20assets/Screen%20Shot%202022-06-23%20at%202.09.13%20PM.png?raw=true)

<br>

Once connected, the store will first run some checks to see if you've already set up a store. After a minute or so, a welcome screen is presented with an Init Store button.

![Setting up store ID](https://github.com/Samy-TB/storefront/blob/master/readme%20assets/init-store-81f85d48f20fbd8de51823fa57c58bc7.png?raw=true)

<br>

From the wallet dropdown (Phantom pictured below), select a network (mainnet for production, testnet or devnet for practice). In this case, chose the devnet.

![Chose devnet](https://github.com/Samy-TB/storefront/blob/master/readme%20assets/init_store_2.png?raw=true)

<br>

Click the Init Store button. This starts the store initialization process by prompting you to approve a transaction from your wallet. After approval, your store initialization begins which may take 1-2 minutes.

![Init store](https://github.com/Samy-TB/storefront/blob/master/readme%20assets/init_store_3.png?raw=true)

<br>

After store initialization completes, you must save your new store addresses. In the Store configuration section on the store page click on the Copy button and paste in the .env file in js/packages/web.

![Save new store address](https://github.com/Samy-TB/storefront/blob/master/readme%20assets/init_store_4.png?raw=true)


![Save new store address](https://github.com/Samy-TB/storefront/blob/master/readme%20assets/init_store_5.png?raw=true)

Now restart your webserver (Ctrl + C + yarn start) for the .env changes to take affect.

<br>

### Great, now your storefront should be up and running :)

<br>
<br>

# Create an NFTs

Once you have finished with a store configuration, you will be able to Create and Sell NFTs.

Click on your wallet and then click on create. You should land on a page that looks like the gif bellow.

# INSERT CREATE HERE

![Create new item](https://docs.metaplex.com/assets/images/intro-554377abde29ddfc864118f55312e960.gif)

<br>

After clicking on the Create button, you will be redirected to the Create section, intended for minting NFT assets. Metaplex supports a wide variety of NFT types. In this article, we'll be focusing on image assets.

![Create NFT](https://docs.metaplex.com/assets/images/create-welcome-024dffff6d76fc52d399097a3cc58f92.png)

## Upload

First, you'll need to upload your image to Arweave. Depending on file type, this can take up to 1 minute.

<br>

> Arweave is a decentralized storage service that backs data with sustainable and perpetual endowments, allowing users and developers to truly store data forever.

<br>

Upload an image directly or provide an absolute url to your file on the internet to use as your NFT image.

After you have finished uploading, you'll see the image name listed below the "Upload" section. Click on Continue to Mint

![Continue to mint](https://docs.metaplex.com/assets/images/upload-96cc791e06e0c8f602f239c79e118ce8.png)


## Describe your item

Next you'll add your image Title, Description, Maximum Supply and Attributes.

![Describe your item](https://docs.metaplex.com/assets/images/describe-asset-03803d4c14fee33b19c3f0f59fcebd3b.png)

Maximum Supply allows you to choose between having a single NFT or multiple copies (prints) from this master edition asset. The main difference between Master Edition and prints is that each print is a numbered edition created from a master edition.

<br>

**Attributes** allow you to define custom properties (key/value pairs) that describe your asset. These attributes are later displayed when viewing the NFT in your wallet or marketplace of choice. For display_type, the default is string but you can also set this to date to hint to downstream tools to format this approprately.

<br>

When you are finished describing your item, click on Continue to royalties.

<br>

## Royalties
Royalties declare how you and/or your creators are compensated for your work.

<br>

### Royalty Percentage
This option specifies, as a percentage, how much of each secondary sale (all sales after the initial sale) will be paid out to the creators. For example, 1%.

<br>

### Creators Split
This option allows you to split proceeds from the initial sale between creators. To do this, you first need to add other creators to your store on the admin page.

After you have finished defining royalties, click on Continue to review.

![Continue to review](https://docs.metaplex.com/assets/images/royalties-aca414f31d08cfa7c9709db88028705a.png)

## Launch

We're on the final stage of minting a new NFT asset. Click on **PAY WITH SOL** to start minting, it will deduct the cost of the transaction from your wallet. Throughout the process of creation, it may ask you to approve transactions in the wallet. After the upload is finished, you will see it in your collection.

![Launch](https://docs.metaplex.com/assets/images/launch-966b68c62bdc9abd3416e7d3ffb643d6.png)

![Launc gif](https://docs.metaplex.com/assets/images/upload-20e0c2d856c6350fa1be5d6c3cf37f27.gif)

![Congratulations](https://docs.metaplex.com/assets/images/finish-961f11d7e2fe41f0e769d76264d9217d.png)

![NFT created](https://docs.metaplex.com/assets/images/item-4993764767d507d7e53960fef2e25f8a.png)

<br>

# Sell NFTs

Once you have finished minting NFT assets, you will be able to sell them. Click on the Sale button in the header. After clicking on the Sale button, you will be redirected to a Sell section. It's intended for selling NFT assets. Here you can select the desired sale type, it may be an instant sale or an auction.

# INSERT SELL NFT IMAGE HERE

![Sell NFT](https://docs.metaplex.com/assets/images/select-type-eed0362a681bc3b398586d72a849c40c.png)

<br>

## Instant Sale

The instant sale allows you to sell a single Master NFT or copies of it at a single price. Other sale types are pretty identical, so you can follow up on this section.

<br>

## Select which item to sell

Create copies of a Master Edition NFT? option allows you to sell copies of a single Master NFT.

![Select item to sell](https://docs.metaplex.com/assets/images/select-item-b57579dbd79bb17863f7bbafd9133c44.gif)

<br>

## Review and list

![Review and list](https://docs.metaplex.com/assets/images/process-5a16297d1f2f01e291a8688080db736b.gif)

<br>

After a successful publish you should see your item listed on the home page under **Live Auctions** or in the block below the header.

![Go to auction](https://docs.metaplex.com/assets/images/instant-sale-explore-15ae11526aa535a8329c6d82c4fae68e.png)

<br>

# Auction Sale

<br>

Metaplex currently supports four types of auctions that are all derived from English auctions. English auction, sometimes referred to an open auction, is the same type of auction that eBay uses. Participants of the auction can see the Price Floor (ie, the minimum bid that you are willing to sell your NFT).

<br>
Basic parameters include:

<br>

- Auction start time
- Auction end time
- Reservation price

<br>

Additionally, Metaplex includes a novel concept of the participation NFT, which you can use for your own auction. Each bidding participant can be rewarded a unique NFT for participating in the auction. Keep in mind that there are costs (ie, minting of participation NFTs) associated with using this feature.

The creator of an auction also has the ability to configure a minimal price that should be charged for redemption, with the option to set it as "free". As mentioned before, participants of your auction are able to see this price.

![List an item](https://docs.metaplex.com/assets/images/select-type-eed0362a681bc3b398586d72a849c40c.png)

## Open Edition

Print as many as you want!

<br>

An open edition auction requires the offering of a Master Edition NFT that specifically has no set supply. The auction will only create Prints of this item for bidders: each bidder is guaranteed to get a print, as there are no true "winners" of this auction type.

<br>

An open edition auction can either have a set fixed price (equivalent to a Buy Now sale), can be set to the bid price (Pay what you want), or can be free (Make any bid to get it for free).

<br>

**Select which item to sell**

![Select item to sell](https://docs.metaplex.com/assets/images/select-item-1a73007675ee3aeef6b6879b49efb2db.png)

<br>

**Set the price**

Set the price floor and bid tick. Bid tick is the amount of price increment for each bid.

![Set the price](https://docs.metaplex.com/assets/images/choose-price-ab44e5fe45821cbf859fb5cbefa6cdf4.png)

<br>

**Initial phase**

The initial phase setting allows you to delay the start of the auction. If you are launching multiple NFTs or an NFT collection, setting a specific date is recommended.

![Initial phase](https://docs.metaplex.com/assets/images/initial-phase-34bc93464f066f9a8135d5794aaf1919.png)

<br>

**Ending phase**

When would you like your auction to end? We’ve seen projects that set their auction duration from anywhere from a few hours (ie, 3 hours) to a few days (no more than 3 days) have the most success.

![Ending phase](https://docs.metaplex.com/assets/images/ending-phase-292783eb479781ee16395422cf934f15.png)

<br>

**Gap Time**

Gap Time is a more advanced feature and most auctions don’t use it. If you anticipate that your community will have lots of competitive bids at the very end, you can use the Gap Time feature. Each new higher bid resets the countdown clock for when the auction ends. Based on feedback from recent projects, we recommend setting Gap Time to a few minutes and no more than 5 or 10 minutes.

<br>

**Tick Size**

Tick Size for Ending Phase is another more advanced feature and most auctions don’t use it. Tick Size dictates how much higher the next bid must be to beat out the previous bid. Outside of Ending Phase, Tick Size is an amount of Sol. In Ending Phase, it’s defined as a percentage higher.

<br>

**Publish**

Publish the auction and observe it under **Explore** section.

You will be asked to approve a transaction, so it will reduce a transaction fee in SOL from your wallet.

![Approve transaction](https://docs.metaplex.com/assets/images/publish-e42deb1f4ce69dee0e0ffb7359ff87ee.png)

![Approve 2nd time](https://docs.metaplex.com/assets/images/auction-page-394fa3a1625acf0d464f50e12a41d7a2.png)

<br>

## Limited Edition

Keep your NFTs rare! For a limited edition auction, a Master Edition NFT (of limited or unlimited supply) may be provided to the auction with a number of copies as the set amount of winning places.

For each prize place, a Print will be minted in order of prize place, and awarded to the winning bidder of that place.

For example, the first place winner will win Print #1; the second place winner Print #2; and so on.

It is required for limited supply NFTs that there is at least as much supply remaining as there are desired winners in the auction.

Flow is identical to the Open Edition auction, with only a difference in the item selection screen. There you can provide the number of copies to sell.

![Limited edition](https://docs.metaplex.com/assets/images/limited-edition-39418997c59b007e55a6910730e86a13.png)

<br>

## Single Item

This type of auction can be used to sell normal NFTs and re-sell Prints, as well as the sale of Master Edition themselves (and the associated printing rights) if the artist so wishes.

![Single item](https://docs.metaplex.com/assets/images/sell-item-22a7dbfac222f829bae36d7574fdbdf8.png)

<br>

On the **Participation NFT** each bidding participant can be rewarded a unique Open Edition NFT for participating in the auction.

![Participation NFT](https://docs.metaplex.com/assets/images/participation-ef071b36def553d1743fe4fd3d5e6e3b.png)

<br>

## Tired Auction

Tiered Auctions is a useful tool for awarding multiple winners (ie, first, second, third place) with NFTs. This can be editions of the same NFTs or different NFTs as runner up prizes.

A tiered auction can contain a mix of the other three auction types as winning placements. For instance, the first place winner could win a Print of Limited Edition NFT A, while the second-place winner could win Normal NFT, and so on. Additionally, all participants who did not win any place could get a Participation NFT Print from a Master Edition (if the Master Edition had no supply limit).

<br>

**Select the number of winners**

![Tired auction](https://docs.metaplex.com/assets/images/tiered-select-count-9a495e8ac7d950df5900dd30bfa4665c.png)

<br>

**Select tiers**

On this screen, you can create several tiers to put winners in them. In our example, the first winner will get Full Rights transfer for an NFT. The second and third winners will get a Print of other NFT.

![Select tiers](https://docs.metaplex.com/assets/images/tiered-select-tiers-1-6d4f0182017f3b48193c1dc7ef0d6e98.png)

![Select tiers part 2](https://docs.metaplex.com/assets/images/tiered-select-tiers-2-a4d4e257db2ad2cc059143a2ef59e948.png)

<br>
<br>

# Deploy

## GitHub Pages

Primarily you need to specify your repo in `js/packages/web/package.json `file

Pay Attention to these two lines:

```json
"deploy:gh": "yarn export && gh-pages -d ../../build/web --repo https://github.com/metaplex-foundation/metaplex -t true",

"deploy": "ASSET_PREFIX=/metaplex/ yarn build && yarn deploy:gh",
```
<br>

There are 2 things to change:

- specify your repo URL instead of `https://github.com/metaplex-foundation/metaplex` (for example, `https://github.com/my-name/my-metaplex`)
- set ASSET_PREFIX to repo name (for example, `ASSET_PREFIX=/my-metaplex/`)
After that, the lines will look like this:

<br>

```json
"deploy:gh": "yarn export && gh-pages -d ../../build/web --repo https://github.com/my-name/my-metaplex -t true",

"deploy": "ASSET_PREFIX=/my-metaplex/ yarn build && yarn deploy:gh",
```

Add the file _config.yml to the root directory add to this file:
```yml
lsi: false
safe: true
source: js/packages/web
incremental: false
highlighter: rouge
gist:
  noscript: false
kramdown:
  math_engine: mathjax
  syntax_highlighter: rouge
```
<br>

Please check that you select gh-pages branch in source on the GitHub Pages tab (current repository)

And after that, you can publish the Metaplex app to GitHub Pages by the following commands:

```bash
cd js/packages/web
yarn deploy
```

<br>

## GitHub Pages with a custom domain

If you have a custom domain linked to the GitHub Pages in your repo, then the instructions are the same as above, but your need to remove `ASSET_PREFIX` from the deploy script:

```json
"deploy:gh": "yarn export && gh-pages -d ../../build/web --repo https://github.com/my-name/my-metaplex -t true",

"deploy": "yarn build && yarn deploy:gh",
```

<br>

Prepare github pages for deploying - select branch in repository then continue:

![custom domain](https://docs.metaplex.com/assets/images/github-pages-selecting-9146b152accb178af1f6980c3e7bae14.png)

<br>

The publishing commands are the same:

```bash
cd js/packages/web
yarn deploy
```

<br>

</details>


<br>

<details><summary>Candy Machine V2 (CLI)</summary>

<br>

The official documentation can also be found here : https://docs.metaplex.com/candy-machine-v2/introduction

# Getting started

Before we can create a Candy Machine, you will need to install and operate a handful of developer tools.

## Tooling required 

You will need recent version of the following tools :

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git): to clone the repository
- [node](https://nodejs.org/en/download/): JavaScript runtime
- [yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable): Package manager to install required dependencies
- [ts-node](https://www.npmjs.com/package/ts-node#installation): TypeScript execution environment

```bash
git version
```
> **output** : *git version 2.35.1*

<br>

The latest LTS version of node is recommended:

```bash
node --version
```

>**output**: *v16.14.2*

<br>

```bash
yarn --version
```

> **output**: 1.22.18

<br>

```bash
ts-node --version
```

> **output**: v10.4.0

<br>

## Apple M1 Chip

If you have Mac OS with the Apple M1 Chip, you'll need to install some additional dependencies.
- [brew](https://brew.sh/)

After installing brew, run the following

```bash
brew install pkg-config cairo pango libpng jpeg giflib librsvg
```

See additional information: https://github.com/Automattic/node-canvas/wiki/Installation%3A-Mac-OS-X

<br>

## Clone and Install Metaplex

Creating and controlling a Candy Machine is done through the Metaplex command line tool, currently distributed in the Metaplex GitHub repository. For now, recommend pulling the latest code from the [master branch](https://github.com/metaplex-foundation/metaplex/tree/master):

```bash
git clone https://github.com/metaplex-foundation/metaplex.git ~/metaplex
```

> *You can modify* **~/metaplex** *so the repository will be placed somewhere else on your machine. Be careful the paths for the other steps, therefore, need to also be updated*

<br>

This will create a directory `metaplex` in your home directory with the latest code from the repository. If you decide to clone the repository to a different location, you will need to change the path in subsequent instructions.

<br>

You will then need to install the dependencies. From outside the metaplex directory:

```bash
yarn install --cwd ~/metaplex/js/
```
<br>

You can check that everything is working by running the Candy Machine CLI command:

```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts --version
```

> **output**: 0.0.2

*:warning: Make sure you are using the `candy-machine-v2-cli.ts` script :warning:*

<br>

## Solana Wallet

The Candy Machine operates on the Solana blockchain. You will need a wallet with funds to create and deploy a Candy Machine. You can create and use a wallet using the [Solana Tool Suite](https://docs.solana.com/cli/install-solana-cli-tools). This guide will assume that you are using the Solana CLI commands.

<br>

## Solana Tool Suite :

After using the CLI, the most efficient way to install Solana Tool Suite is through [Homebrew](https://brew.sh/). If you didn't install it then previous steps, it is time now.

> *Homebrew is package manager on your MacOS or Linux machine.*

<br>

After installing Homebrew you can now enter the following command :

```bash
brew install solana
```

<br>

Confirm you have the desired version of `solana` installed by entering:

```bash
solana --version
```
> **output**: solana-cli 1.9.1

<br>

## Setting up a devnet wallet (for testing)

The steps described here will create a wallet to be used in the Solana `devnet` environment. In normal circumstances you would redact your mnemonic, store it somewhere safe and take advantage of the `--outfile` flag.

<br>

To create a new wallet, we will use the `solana-keygen` command:

```bash
solana-keygen new --outfile ~/.config/solana/devnet.json
```

<details><summary>Output</summary>

```
Generating a new keypair

For added security, enter a BIP39 passphrase

NOTE! This passphrase improves security of the recovery seed phrase NOT the keypair file itself, which is stored as insecure plain text

BIP39 Passphrase (empty for none):

Wrote new keypair to /Users/febo/.config/solana/devnet.json

=======================================================================

pubkey: 6j4nNrozTJkk1zatiXHezSLZArnRUq3WkGKHACThXGpZ

=======================================================================

Save this seed phrase and your BIP39 passphrase to recover your new keypair:
## REDACTED ##

=======================================================================
```
</details>

<br>

The next step is to make this our default keypair:

```bash
solana config set --keypair ~/.config/solana/devnet.json
```

and make sure we are on the `devnet`:

```bash
solana config set --url https://metaplex.devnet.rpcpool.com/
```

If all the above steps are successfull, your configuration be similar to:

```bash
solana config get
```

<details><summary>Output</summary>

```
Config File: ~/.config/solana/cli/config.yml

RPC URL: https://metaplex.devnet.rpcpool.com/

WebSocket URL: wss://metaplex.devnet.rpcpool.com/ (computed)

Keypair Path: ~/.config/solana/devnet.json

Commitment: confirmed
```

</details>

<br>

## Funding your devnet wallet

In order to add SOL to your `devnet` wallet, you can request funds from a faucet : 

```bash
solana airdrop 2
```

> *The maximum that a user can airdrop to a devnet wallet is 2 SOL*

<br>

<details><summary>Output</summary>

```
Requesting airdrop of 2 SOL

Signature: 

41ZEZqpyNMLUy3kQahWSy349PeDz3Q82dNDHKiA7QcsrAzHs3f7YiDEZWjnFi434DoiiDiDkazkBRycRnctx1m6e

6 SOL
```

</details>

<br>

*If the command is successful, you will see the updated balance at the end. Make sure you are entering the airdrop amount that is within the airdrop limit. Currently the maximum airdrop request limit is **2 SOL** and there is a daily total limit of **24 SOL**.*

<br>

> :warning: The `solana airdrop` command is sometimes unreliable. If the command doesn't work, you can use the airdrop tool at https://solfaucet.com. :warning

<br>

## DO NOT SEND **REAL** SOL TO A `DEVNET` WALLET!

<br>
<br>

# Configuration

The configuration in `CMv2` is now specified in a single JSON file. This allows you to save and reuse the configuration across multiple drops. Additionally, there is a single account on-chain that holds all the configuration of a Candy Machine and the values can be updated at any point. The way the Candy Machine operates depends on the settings used, and therefore it is the **most important part in setting up your Candy Machine**. It is crucial to understand how the settings work to decide which ones to use for your project.

<br>

We will discuss a few examples on how to set up a Candy Machine, starting with the settings to configure a `CMv2` to operate in a similar way as a `CMv1`.

<br>

The link below provides an overview of the settings available:

- https://docs.metaplex.com/candy-machine-v2/configuration


<br>

> :warning: If you set noMutable to true, you **WILL NOT** be able to update your NFTs at any point in the future. :warning:

<br> 

> :bulb: Any setting that is not used must be set to null to avoid errors from the CLI.

<br>

## Minimal Configuration

A minimal Candy Machine config settings looks like this:

```json
{
    "price": 1.0,
    "number": 10,
    "gatekeeper": null,
    "solTreasuryAccount": "<YOUR WALLET ADDRESS>",
    "splTokenAccount": null,
    "splToken": null,
    "goLiveDate": "25 Dec 2021 00:00:00 GMT",
    "endSettings": null,
    "whitelistMintSettings": null,
    "hiddenSettings": null,
    "storage": "arweave-sol",
    "ipfsInfuraProjectId": null,
    "ipfsInfuraSecret": null,
    "nftStorageKey": null,
    "awsS3Bucket": null,
    "noRetainAuthority": false,
    "noMutable": false
}
```

> :warning: The number of items setting can only be updated after you create your CMv2 if you are using hiddenSettings. When hiddenSettings are not used, the number value is used to allocate the space required by the CMv2 account and therefore cannot be modified.

> :warning: In case you require to change the number of items after creating a CMv2 without hiddenSettings, you can withdraw rent of your current CMv2 and then create a new one. 

<br>

The above settings will configure a CMv2 to operate in a similar way as a CMv1 – although the mint order will be unpredictable. In other words, even the most simple v2 configuration provides an improvement over v1. You can view this as the minimum set of settings required to create a Candy Machine. Many projects will be using a similar set of settings, as this already provides a fully-working on-chain distribution mechanism.

The settings that are specified in this example are:

- price
- number
- solTreasureAccount
- goLiveDate
- noRetainAuthority
- noMutable

If this satisfies the requirement for your project, save these settings to a file (e.g., `config.json`) and you are ready to start uploading your items and create a Candy Machine. Below we will discuss other configuration examples that represent specific use-cases. These examples will use the settings above as a starting point and provide the settings section to be added/updated.

<br>

> :bulb: It is important that the number setting value matches the number of items in your Candy Machine.

<br>
<br>

## Gatekeeper Settings

While the unpredictable mint index provides some protection against bots, bots are still able to mint directly from the Candy Machine. If you want to make sure that only humans can mint from your project, you can enable the gatekeeper settings in your config.json with the following values:

```json
"gatekeeper": {
    "gatekeeperNetwork" : "<PROVIDER NETWORK ADDRESS>",
    "expireOnUse" : true
}
```

<br>

This will enable a gatekeeper challenge once the mint button is clicked—only after passing the challenge you will be allowed to mint.

When you use a gatekeeper, you will not be able to mint from the CLI command `mint_one_token`. If you want to pre-mint from a `CMv2` and are planning to use a gatekeeper, you should set the `goLiveDate` to `null` and turn `gatekeeper` (temporarily) off. This will allow you to mint from the command line, but only you as the `CMv2` authority. Once you complete the pre-mint, turn `gatekeeper` on and set the correct `goLiveDate`.

<br>

> :warning: If your Candy Machine is **live** and it has **no gatekeeper**, it is open to bots attacks. The unpredictable mint index only prevents knowing which item to mint, but bots can still snipe a large volume of items.

<br>

## Provider Networks

There are currently two supported gatekeepers (details below). If you want to become a supported gatekeeper please email contact@identity.org.

> [Learn more about the Identity Gateway Protocol](https://docs.identity.com/docs/overview/)

<br>

### Civic Captcha Pass


> Address: `ignREusXmGrscGNUesoU9mxfds9AiYTezUKex2PsZV6`

<br>

**Recommended**: maintain `expireOnUse: true`. Changing this setting increases the susceptibility of your project to bots.

Brings the familiar captcha challenge to web3 and combines it with user-transparent heuristics to protect your mint from bots.

With captcha enabled, a user will be issued a Civic Captcha Pass after successfully completing the captcha challenge and automatically checked by the Candy Machine prior to minting.

A Civic Captcha Pass remains active only for 10 minutes and for one mint to limit the options of malicious botters verifying multiple wallets. If a user tries to use an inactive pass, it will automatically prompt them to refresh it.

- Learn More
- Civic Ts&Cs

<br>

### Verify by Encore

<br>

> Address: `tibePmPaoTgrs929rWpu755EXaxC7M3SthVCf6GzjZt`

A web3 alternative to captcha that uses randomized challenge-response tests to filter out bots.
- [Learn More](https://encorefans.notion.site/Verify-0af40ff4b3324694abf336f185c9fad2)
- [Encore Ts&Cs](https://www.encore.fans/terms-conditions)

<br>

> :information_source: By using a gatekeeper, you agree to their terms and conditions.

<br>

## Hidden Settings

Hidden settings serve two purposes. First, it allows the creation of larger drops (20k+), since the metadata is not stored on-chain. In turn, this also allows the creation of hide-and-reveal drops, where users discover which item(s) they minted after the mint is complete.

To enable hidden settings, you need to provide the details for the *hiddenSettings* in your `config.json`:

```json
"hiddenSettings": {
    "name":"My Hidden Collection ",
    "uri":"uri",
    "hash":"44kiGWWsSgdqPMvmqYgTS78Mx2BKCWzd"
}
```

Once hidden settings are enabled, every mint will have the same URI and the name will be created by appending the mint number (e.g., “#45”) to the name specified. The hash is expected to be a 32 character string corresponding to the hash of a cache file that has the mapping between a mint number and the actual metadata URI. This allows the order of the mint to be verified by others after the mint is complete.

Since the metadata is not on-chain, it is possible to create very large drops. The only caveat is that there is a need for an off-chain process to update the metadata for each item. This is important otherwise all items will have the same metadata.

<br>

## End Settings


End Settings provides a mechanism to stop the mint if a certain condition is met without interaction. There are two conditions that can be specified.

Stop a mint at a specific timestamp (e.g., at the end of a specific day):

```json
"endSettings": {
    "endSettingType": { "date":true },
    "value":"25 Dec 2021 23:59:00 GMT"
}
```
Stop a mint after a certain amount of item have been minted (e.g., 10 items minted):
```json
"endSettings": {
    "endSettingType": { "amount":true },
    "value":10
}
```

This can be used in combination with other settings to create specific use cases. For example, you can run a whitelist presale either for a limited time or for a limited number of items; you can specify your sale period to be between the `goLiveDate` and the `endSettings`'s `date`.


<br>
<br>

## Whitelist Settings

Whitelist settings provide a variety of different use cases and revolve around the idea of using custom SPL tokens to offer special rights to token holders - how said SPL token is distributed is up to you. We will discuss a few scenarios below.

> In all the examples below, you will need to change the `mint` settings address `7nE1GmnMmDKiycFkpHF7mKtxt356FQzVonZqBWsTWZNf` with the mint address of your SPL token.

> :information_source: You can use the whitelist settings with the `presale` option set to `true` in combination with the gateway settings. This will restrict the mint to only whitelist users and require them to complete the Gatekeeper's challenge.

<br>

- Creating a whitelist **only** for presale (e.g., allow whitelist users to mint before the `goLiveDate`) and burning the whitelist token each time. Once the sales begin, whitelist users do not have any privileges.

<br>

```json
"whitelistMintSettings": {
    "mode" : { "burnEveryTime": true },
    "mint" : "7nE1GmnMmDKiycFkpHF7mKtxt356FQzVonZqBWsTWZNf",
    "presale" : true,
    "discountPrice" : null
}
```

<br>

- Creating a whitelist for presale, burning the whitelist token each time and provide whitelist users with a 0.5 SOL price tag instead (specified by the `discountPrice`). Once the sales begin (i.e., everyone can mint), the whitelist gets you only the discount.

<br>

```json
"whitelistMintSettings": {
    "mode" : { "burnEveryTime": true },
    "mint" : "7nE1GmnMmDKiycFkpHF7mKtxt356FQzVonZqBWsTWZNf",
    "presale" : true,
    "discountPrice" : 0.5
}
```

<br>

- Creating a whitelist for presale, not burning the whitelist token (you will be able to reuse it) and give whitelist users a 0.5 SOL price tag instead. Once the sales begin (i.e., everyone can mint), the whitelist gets you only the discount.

<br>

```json
"whitelistMintSettings": {
    "mode" : { "neverBurn": true },
    "mint" : "7nE1GmnMmDKiycFkpHF7mKtxt356FQzVonZqBWsTWZNf",
    "presale" : true,
    "discountPrice" : 0.5
}
```

<br>

- Creating a whitelist, not burning the whitelist token (you will be able to reuse it) and gives whitelist users a 0.5 SOL price tag instead - i.e., the whitelist only gets you the discount.

<br>

```json
"whitelistMintSettings": {
    "mode" : { "neverBurn": true },
    "mint" : "7nE1GmnMmDKiycFkpHF7mKtxt356FQzVonZqBWsTWZNf",
    "presale" : false,
    "discountPrice" : 0.5
}
```
<br>

- Creating a whitelist, burning the whitelist token each time, running the white list during the sale. This in effect restrict any user without the whitelist token from minting at all - this is why `presale` is set to `false` and `discountPrice` set to `null`. The only purpose of the whitelist is to **restrict** the mint.

<br>

```json
"whitelistMintSettings": {
    "mode" : { "burnEveryTime": true },
    "mint" : "7nE1GmnMmDKiycFkpHF7mKtxt356FQzVonZqBWsTWZNf",
    "presale" : false,
    "discountPrice" : null
}
```

## Finishing up
Once you have decided which settings are suitable for your project, save your settings in a json file - in this guide we will be using a file called `config.json`. At this point, you are ready to start uploading your assets to the Candy Machine.

<br>
<br>

# Preparing your Assets
The Candy Machine is a distribution program and in order to use it to mint NFTs, it needs to be loaded up with your project's artwork and metadata.

Your assets consist of a collection of images (e.g., `.png`) and metadata (`.json`) files organized in a 1:1 mapping - i.e., each image has a corresponding metadata file.

There are a multitude of unique ways to generate images and metadata, and in most scenarios, you will automate this process. In this guide we will cover the creation of a simple collection to illustrate the metadata requirements and Candy Machine distribution. You should familiarize yourself with the [Token Metadata Standard](https://docs.metaplex.com/programs/token-metadata/token-standard).

<br>

## Example NFT Collection

A 10-item collection will have 20 files in total:

| **Images** | **Metadata**|
|  --        |    --       |
|`1.png`     | `1.json`    |
|`2.png`     | `2.json`    |
|`3.png`     | `3.json`    |
|`4.png`     | `4.json`    |
|`5.png`     | `5.json`    |
|`6.png`     | `6.json`    |
|`7.png`     | `7.json`    |
|`8.png`     | `8.json`    |
|`9.png`     | `9.json`    |
|`10.png`    | `10.json`   |

<br>

>:warning: For some reason, having an image named `0.png` with its metadata in `0.json` seems to fail the creation of that NFT. Since `0` is a falsy value, it might create some issues in the code. Please avoir using `0` as a file name.

<br>

Each pair `0.png` and `0.json` are combined to represent the first NFT in this example collection; `1.png` and `1.json` describe the second NFT and so forth. These files are typically grouped into a single folder, usually named `assets`, but that is not a hard requirement. Grouping them into a single folder simplifies next steps and is highly encouraged.

The content of the image files reflect the artwork you would like to display for each NFT and the content of the metadata files describe each of these pieces of artwork using the schema defined in the [Token Metadata Standard](https://docs.metaplex.com/programs/token-metadata/token-standard).


<br>

> The first item in your collection must have the index `0`, the second `1` and so forth. In a `10000` NFT drop, will start with the pair `0.png` and `0.json`, and end with the pair `9999.png` and `9999.json`. The numbering must also be consecutive - i.e., should not have gaps in the numbering.

<br>

> :warning: It is important to double check that you do not skip any indices, e.g., 0.png, 2.png, 3.png (missing 1.png). Otherwise you will experience problems when minting your collection. 

<br>

**For the sake of this example, please start your file name to `1.png` and `1.json`**

<br>

## Sample Items of the Collection

Below are two simples examples of items in this collection:

- **Image**: `1.png`

![NFT #1](data:image/png;base64,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)

- **Metadata**: `1.json`
```json
{
  "name": "Number #0001",
  "symbol": "NB",
  "description": "Collection of 10 numbers on the blockchain. This is the number 1/10.",
  "seller_fee_basis_points": 500,
  "image": "1.png",
  "attributes": [
    { "trait_type": "Layer-1", "value": "0" },
    { "trait_type": "Layer-2", "value": "0" },
    { "trait_type": "Layer-3", "value": "0" },
    { "trait_type": "Layer-4", "value": "1" }
  ],
  "properties": {
    "creators": [
      { "address": "N4f6zftYsuu4yT7icsjLwh4i6pB1zvvKbseHj2NmSQw", "share": 100 }
    ],
    "files": [{ "uri": "1.png", "type": "image/png" }]
  },
  "collection": { "name": "numbers", "family": "numbers" }
}
```
<br>

- **Image:** `10.png`

![NFT #10](data:image/png;base64,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)

- **Metadata**: `10.png`

```json
{
  "name": "Number #0010",
  "symbol": "NB",
  "description": "Collection of 10 numbers on the blockchain. This is the number 10/10.",
  "seller_fee_basis_points": 500,
  "image": "10.png",
  "attributes": [
    { "trait_type": "Layer-1", "value": "0" },
    { "trait_type": "Layer-2", "value": "0" },
    { "trait_type": "Layer-3", "value": "1" },
    { "trait_type": "Layer-4", "value": "0" }
  ],
  "properties": {
    "creators": [
      { "address": "N4f6zftYsuu4yT7icsjLwh4i6pB1zvvKbseHj2NmSQw", "share": 100 }
    ],
    "files": [{ "uri": "10.png", "type": "image/png" }]
  },
  "collection": { "name": "numbers", "family": "numbers" }
}
```

<br>

Notice that the difference in the metadata between each image is on:

- `"name"` property: `"Number #0001"` in the first image and `"Number #0010"` in the last image
- `"description"` property: it shows `"number 1/10"` in the first image and `"number 10/10"` in the last image
- `"image"` property: `"1.png"` in the first image and `"10.png"` in the last image
- `"properties.files.uri"` property: `"1.png"` in the first image and `"10.png"` in the last image
- `"attributes"` property: the values for `"Layer-3"` and `"Layer-4"` trait-types are different, since they describe attributes of the images

It is also important to make sure that you set royalties percentage awarded to creators (`"seller_fee_basis_points"` property) is set and each creators' wallet is listed in the `"properties.creators"` property.

<br>

> :information_source: You can download the complete [sample collection](https://docs.metaplex.com/assets/files/assets-934a7281da49092b2a477733d067d8a0.zip) for testing and experimentation. Subsequent steps in this walkthrough will assume it's the collection in use.

<br>

## Verifying Assets

Once you completed your project's artwork and metadata preparation, it is important to verify that the files are ready to be uploaded. The Candy Machine CLI provides the `verify_assets` command to check that the files in the assets folder are in the correct format. This involves verifying that:

<br>

1. Files types are supported (e.g., png, jpg, mp4). Note that the command does not verify the content of the files; it does a lightweight verification that the extension of the files are from a supported type.

<br>

2. For each image/audio/video file, there is a correspondent json metadata file using the correct index naming in the `image` and `animation_url` properties.

<br>

3. Creators have been consistently added to all metadata files. The command expects that all assets have the same creators.

<br>

To proceed with the verification process, you will execute the `verify_assets` command:

```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts verify_assets ./assets
```

<br>

The only required parameter is the directory of the assets—in this example, ./assets is the name of the directory. Executing the command using the sample collection will produce the following output:

<br>

```bash
started at: 1646926416415

Verifying token metadata for 10 (img+json) pairs

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/0.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/1.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/2.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/3.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/4.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/5.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/6.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/7.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/8.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/9.json

ended at: Thu Mar 10 2022 15:33:36 GMT+0000 (Greenwich Mean Time). time taken: 00:00:00
```

<br>

The above represents an example of a successful verification. When the command finds any inconsistency, it will report an error under the filename (`0.json` in this case) where the error occurred, as shown below:

<br>

```bash
started at: 1646926416415
Verifying token metadata for 10 (img+json) pairs

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/0.json

We expected the `image` property in ~/metaplex/js/packages/cli/test/assets/0.json to be 0.jpg.

This will still work properly (assuming the URL is valid!), however, this image will not get uploaded to Arweave through the `metaplex upload` command.

If you want us to take care of getting this into Arweave, make sure to set `image`: "0.jpg"

The `metaplex upload` command will automatically substitute this URL with the Arweave URL location.

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/1.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/2.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/3.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/4.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/5.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/6.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/7.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/8.json

Checking manifest file: ~/metaplex/js/packages/cli/test/assets/9.json

ended at: Thu Mar 10 2022 15:33:36 GMT+0000 (Greenwich Mean Time). time taken: 00:00:00
```

<br>

**As soon as your assets are verified, you are ready to create your Candy Machine.**

<br>
<br>

# Creating the Candy Machine

Once you have your collection prepared, the next step is to upload your assets and create a Candy Machine. This step is completed by a single command via the Candy Machine CLI.

Before you can proceed, you need to check that:

- Your images and metadata are located in the same directory - in most cases this will be a directory named assets
- You have funds in your wallet - the command solana balance will tell your current balance
- You have created your Candy Machine configuration file (e.g., config.json)

<br>

> :warning: Caution :warning: 
> <br>
> To create a Candy Machine, space is allocated on chain to temporarily store the names and URI links (mirroring what is in your `.json` file in the `.cache` directory). To store this data on chain, you are required to pay on chain rent costs. After your mint (or whenever you want to end it), you can run the `withdraw` command to **reclaim all of the rent costs**. Check the [withdraw section](https://docs.metaplex.com/candy-machine-v2/withdraw) for more details. For a 10k collection, the rent costs are approximately **16.7 SOL**. This scales linearly with the number of items in your collection. Thus, you can get an approximate on chain rent cost estimate by multiplying the number of items in your collection by **0.00167 SOL**.

<br>

To proceeed, you will execute the `upload` command:

```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts upload \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -cp config.json \
    -c example \
    ./assets
```

> :stop_sign: WARNING :stop_sign:
> <br>
> The upload is a network-intensive command, in particular when dealing with larger collections. We highly recommend using a custom RPC, which can be specified by the switch --rpc-url <string> in the upload command. You can find a list of custom RPC services in our [community docs](https://docs.metaplex.com/community#rpc).

<br>

In this command we are specifying that we will run the upload in the `devnet` environment (`-e` option), we will use the wallet keypair `~/.config/solana/devnet.json` (`-k` option), the Candy Machine configuration file `config.json` (`-cp` option), the cache file suffix `example` (`-c` option) and upload our assets from the folder `./assets`.

<br>

Depending on the size of the collection - number of items and/or size of the images - this command has the potential to fail multiple times but should not be a problem when executed again, it will resume from the point it stopped in the previous execution.

Below is a sample output of a successful upload and Candy Machine creation:

```
WARNING: The "arweave" storage option will be going away soon. Please migrate to arweave-bundle or arweave-sol for mainnet.

Beginning the upload for 10 (img+json) pairs

started at: 1640191406699

Size 10 { mediaExt: '.png', index: '0' }

Processing asset: 0

initializing candy machine initialized config for a candy machine with publickey: ABceMmLMwmSfL5mL1cCrpPMKGupMXUezEY3JyZ1JSd6h

Processing asset: 0
Processing asset: 1
Processing asset: 2
Processing asset: 3
Processing asset: 4
Processing asset: 5
Processing asset: 6
Processing asset: 7
Processing asset: 8
Processing asset: 9

Writing indices 0-9

Done. Successful = true.

ended at: 2021-12-22T16:44:38.446Z. time taken: 00:01:11
```

<br>

Any execution that does not complete an upload successfully will have an output `Successful = false`. In this case, re-run the upload command until a successful execution is achieved.

<br>

> :information_source: It is common to receive `signatureUnsubscribe error: Invalid subscription id`. messages. This is not an error that affects the upload.

<br>

The command also outputs the Candy Machine PublicKey, which you can verify on the [Solana Explorer](https://explorer.solana.com/):

![Solana explorer](https://docs.metaplex.com/assets/images/solana-explorer-6d992d47ec7f4a7661d40bbd779b9099.png)



> :information_source: The example uses the `"arweave"` storage option as we are running it on the `devnet`. When running on `mainnet-beta`, check other storage options that better suit your project/needs.

<br>

## Candy Machine Collections

Candy Machine now allows you to set an on-chain collection which will be set during mint, following the [on-chain collections specification](https://docs.metaplex.com/programs/token-metadata/certified-collections) of the Token Metadata program.

<br>

> :information_source: Setting or removing a collection for a Candy Machine will only impact NFTs that have yet to be minted. This will not change NFTs from your Candy Machine that have already been minted.

<br>

To set the collection for your Candy Machine, run the set_collection command:

```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts set_collection \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -c example \
    -m C2eGm8iQPnKVWxakyo8QhwJUvYrZHKF52DPQuAejpTWG
```

Successful output example:

```
wallet public key: bob1upX2AoA7HAHzDTPMcYhWWnYJeMJturpswReqqP4
(node:7714) ExperimentalWarning: stream/web is an experimental feature. This feature could change at any time
(Use `node --trace-warnings ...` to show where the warning was created)
(node:7714) ExperimentalWarning: buffer.Blob is an experimental feature. This feature could change at any time
Candy machine address:  6KyiTBupdBKFRvppJFa7LHhNYyQet8uTci9PiMkb6Niw
Collection metadata address:  6KVxzViK7v3nMKJxsgTBCXoZAgWc7TPWUy5YszuPytDL
Collection metadata authority:  bob1upX2AoA7HAHzDTPMcYhWWnYJeMJturpswReqqP4
Collection master edition address:  8uK5BmKsGYyngQ81iFbXkSdbhN2cN4NZCzyXH18k6sBg
Collection mint address:  FyLAtLXi1UcyBNbmz6G9rcxT6Qg7HhoT9PsTitmkVsyE
Collection PDA address:  7ULQrCp4MWZ4dMoaGdY52cZucmq8vHJxpogFSJXK8ee1
Collection authority record address:  BHkQpLrDPq6JBAzW8nMHVP9Hz4L6P1rqtXNhR8EEo2Jq
set collection finished {
  collectionMetadata: '6KVxzViK7v3nMKJxsgTBCXoZAgWc7TPWUy5YszuPytDL',
  collectionPDA: '7ULQrCp4MWZ4dMoaGdY52cZucmq8vHJxpogFSJXK8ee1',
  txId: '2e9VytqDnDtATyK3tsAUQJSHuEHvZL2XDQmUEGm5MuTG7jSgMfZxUjXLosJnWc7WeQCyhpktZRJxpXFsN6rJDwPd'
}
```

The `-m` option is the mint account of the collection NFT you want to set for your Candy Machine. This is the same account as the one you would see in mint/hash lists.

<br>

If you have already set a collection for your Candy Machine, you can also remove it with the `remove_collection` command:

```shell
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts remove_collection \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -c example
```

Successful output example:

```
wallet public key: bob1upX2AoA7HAHzDTPMcYhWWnYJeMJturpswReqqP4
(node:14972) ExperimentalWarning: stream/web is an experimental feature. This feature could change at any time
(Use `node --trace-warnings ...` to show where the warning was created)
(node:14972) ExperimentalWarning: buffer.Blob is an experimental feature. This feature could change at any time
Candy machine address:  6KyiTBupdBKFRvppJFa7LHhNYyQet8uTci9PiMkb6Niw
Authority address:  bob1upX2AoA7HAHzDTPMcYhWWnYJeMJturpswReqqP4
Collection PDA address:  7ULQrCp4MWZ4dMoaGdY52cZucmq8vHJxpogFSJXK8ee1
Metadata address:  6KVxzViK7v3nMKJxsgTBCXoZAgWc7TPWUy5YszuPytDL
Mint address:  FyLAtLXi1UcyBNbmz6G9rcxT6Qg7HhoT9PsTitmkVsyE
Collection authority record address:  BHkQpLrDPq6JBAzW8nMHVP9Hz4L6P1rqtXNhR8EEo2Jq
remove collection finished {
  collectionMetadata: '6KVxzViK7v3nMKJxsgTBCXoZAgWc7TPWUy5YszuPytDL',
  collectionPDA: '7ULQrCp4MWZ4dMoaGdY52cZucmq8vHJxpogFSJXK8ee1',
  txId: '32EseQPvZzcyVtpj4Sse2RoeAsU5akwbLL2v36W6CBEx6Jh9okmH4yR4XyfRAQKujmt7aKvYJ4GjNhp7ddnowm7D'
}
```
<br>
<br>

# Verify Upload

The Candy Machine provides a command to verify if the metadata URI on chain has been successfully uploaded.

```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts verify_upload \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -c example
```
The command will check that each entry in the cache file matches the URI stored on-chain. A successful execution will generated an output similar to:

```
Key size 10
Name Number #0001 with https://arweave.net/AVmNYNiiJcsjMwICLnrZQacxn5duJJCQoEeksrz2VC4 checked out
Name Number #0002 with https://arweave.net/AQ5jvijKSIfiWt49w-Xf4OTwWS1WzXK2kq9gT8CCYeM checked out
Name Number #0003 with https://arweave.net/jC6Cz-6VtQSWp0kJMurdxp5BPeNHHoXmjOXl6G7bFeI checked out
Name Number #0004 with https://arweave.net/-u8Uikbe-K0RKTvJWXEf2s0vXkRJmbM-XxJb2ijCqD4 checked out
Name Number #0005 with https://arweave.net/oC0S6XNiAOo97SS0qhVbeoXEBC5TmlklWOZMJLD0URM checked out
Name Number #0006 with https://arweave.net/YoGpQYv7SGGF0_46n0pmLitXfjiY20mXDa8ezgpo0j4 checked out
Name Number #0007 with https://arweave.net/fvXr1-3RnTDj7C7rJ4I32SHbH_MDMs9O6Eunzzu1vk4 checked out
Name Number #0008 with https://arweave.net/lWnzWX_Mh7Lxy3f6drrJvtfi1_zN6xfNVS7gCF0hY1A checked out
Name Number #0009 with https://arweave.net/YtHXX8vJ-3dAFINUoeLEKpNBtP32LVyj6_kH6nFFdPw checked out
Name Number #0010 with https://arweave.net/FJDIqjMi1R-ut0n08QNCADvvfLKT-j7g2qNS2fkr5EQ checked out
uploaded (10) out of (10)
ready to deploy!
```
If any of the URI entries do not match the information on the chain, you will get an error:

```
Error: not all NFTs checked out. check out logs above for details
```
In this case, you will need to re-run the upload command. Only after the verify command succeeds should you make your Candy Machine live.

<br>
<br>

# Mint Tokens

At this point, your Candy Machine is ready to mint tokens. Depending on your configurations, it is either restricted to whitelist users or the `goLiveDate` has not been reached yet. In all cases, the owner (authority) of the Candy Machine - i.e., the wallet that created the Candy Machine - can mint tokens.

> The only exception is when captcha is enabled. In this case, it is not possible to mint tokens from the command line. If you would like to mint tokens, update the `goLiveDate` to `null` and temporarily disable the captcha settings.

<br>

## Mint One Token

Minting one token can be done using the command `mint_one_token`:

```
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts mint_one_token \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -c example
```
If successful, the output will be similar to:

```
wallet public key: N4f6zftYsuu4yT7icsjLwh4i6pB1zvvKbseHj2NmSQw
mint_one_token finished 3R9XADK91RWESj3FZdzB2QXHchpjwcS5khdwZVoSd3petHyqt2T6MjntMxozX2meRFyaFZEsqjPxbCUjxz5eL5z9
```

You can check that the mint was successful by using the spl-token command to check the accounts available on your wallet:

```
spl-token accounts
```
If the mint was successful, you will see a new account in your wallet:
```
Token                                         Balance
---------------------------------------------------------------
G1zDZMHjU6bs4ibrZdeaM85dHYtno1B1xUmZ1VR7XCsQ     1
```

<br>

## Mint Multiple Tokens

You can also mint multiple tokens using the command `mint_multiple_tokens` and specifying the `number` of tokens to be minted:

```
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts mint_multiple_tokens \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -c example \
    --number 2
```

If successful, the output will be similar to following output:
```
Minting 2 tokens...
wallet public key: N4f6zftYsuu4yT7icsjLwh4i6pB1zvvKbseHj2NmSQw
transaction 1 complete 37e4NjN5yPWevAus1m3XyCNgRPAxanQ5YdePn732U73XPa2MsHccJamoqkUFi6AtPwU8j3CATT84qq9G7ciAfRSU
minting another token...
wallet public key: N4f6zftYsuu4yT7icsjLwh4i6pB1zvvKbseHj2NmSQw
transaction 2 complete 5emunaycm99shUXuH3Xs6vCbTe6c8X6UqGoQYJ8qkwUd2mVppvojXyz2bxuYPmLVriuoqobBRNwFkp5Q2zCRV6pu
minted 2 tokens
mint_multiple_tokens finished
```
You can follow the steps above to verify that the tokens are in your wallet.

<br>
<br>

# A Front End Minting Experience

While the Candy Machine is ready to mint, in most cases you will want to provide a front end experience to allow your community the chance to mint, too.

You can use the Candy Machine v2 UI, which is already in the Metaplex repository and downloaded when you executed the `git clone` command.

<br>

## Setting up

Open the file `.env.example` located in the folder `~/metaplex/js/packages/candy-machine-ui` and modify the following:

- Set the value of REACT_APP_CANDY_MACHINE_ID to match the ID of your Candy Machine. The ID was in the output of the upload command and can also be found inside your Candy Machine cache file - this is located in the same directory that you executed the upload command (e.g., .cache/devnet-example)

- Specify the intended network you wish to use. In this example we are using the devnet:

```env
REACT_APP_CANDY_MACHINE_ID=<YOUR CANDY MACHINE PROGRAM ID>

REACT_APP_SOLANA_NETWORK=devnet
REACT_APP_SOLANA_RPC_HOST=https://metaplex.devnet.rpcpool.com/
```
Once your `REACT_APP_CANDY_MACHINE_ID` has been updated. Rename `.env.example` to `.env`

<br>

> :stop_sign: WARNING :stop_sign:
> <br>
> The public RPC endpoints (`https://api.mainnet-beta.solana.com` and `https://api.devnet.solana.com`) are not suitable for Candy Machine mints and may cause significant issues to your minting site. We strongly recommend that you use a custom RPC endpoint for your mint. You can find more information about the custom RPC solutions in the RPC section of our [community docs](https://docs.metaplex.com/community#rpc).

<br>

After these changes are made, run the command yarn install && yarn start inside the folder ~/metaplex/js/packages/candy-machine-ui. This will start a local server with a front end experience. From here, you should customize the mint page and deploy it in your host service.

<br>

> :stop_sign: WARNING :stop_sign:
> <br>
> We **strongly** recommend that you keep the standard implementation for the mint button functionality when using captcha (`gatekeeper`) settings. This will guarantee that the captcha tokens are issued at the correct time (e.g., after the mint begins). The `CMv2` is designed to reject captcha tokens that are created before the mint is live to avoid bots pre-solving captchas - your transaction will fail if the token is created at the wrong time.

<br>

## User Interface

The UI supports all different configurations of your Candy Machine v2, including whitelist (presale + discount) and end settings—e.g., it automatically adapts the UI components depending on whether the whitelist token is detected or not, discount for whitelist users is set and displays a countdown to the end of mint when end settings `"date"=true` is used.

<br>

### Default Mint

<br>

Before `goLiveDate` is reached:

![Before goLiveDate](https://docs.metaplex.com/assets/images/Mint-1-20fc223521cb4f1544a8b5c74c15b33c.png)

When mint is live:

![Mint is live](https://docs.metaplex.com/assets/images/Mint-2-c466fd221b90c55ec705339f003fb464.png)

<br>

### Whitelist Mint

<br>

Whitelist token not detected, mint is not active before `goLiveDate`:

![whitelist golivedate](https://docs.metaplex.com/assets/images/Whitelist-1-8be580595a13b6e0cd506666f81a2169.png)


Whitelist token detected and whitelist settings set to presale and discount price:

![Discount price](https://docs.metaplex.com/assets/images/Whitelist-2-55a3bec84d541b7426b909a29a41fdd0.png)


Whitelist only mint:

![Whitelist mint](https://docs.metaplex.com/assets/images/Whitelist-3-26eb5efaad6f5a28868115013ab58fdd.png)

Whitelist + presale and goLiveDate set to null:

![White + presale](https://docs.metaplex.com/assets/images/Whitelist-4-6ef1e637541184122e8fac0f774ee03f.png)

<br>

### End Settings Mint

<br>

Countdown to the end of the mint:

![End of mint](https://docs.metaplex.com/assets/images/EndSettings-1-a30fb4d205d08a828d0258fa5a67cd8c.png)

End settings date reached, mint stopped:

![End settings date](https://docs.metaplex.com/assets/images/EndSettings-2-a0cc26863ff1efa26e3211915d4b9a4a.png)

<br>
<br>

# Update the Candy Machine

**Most** configuration settings can be updated in a `CMv2` with a single command, with the exception of:

- `number` of items in the Candy Machine can only be updated when `hiddenSettings` are being used.

- switching to use `hiddenSettings` is only possible if the `number` of items is equal to `0`. After the switch, you will be able to update the `number` of items.

In case you require to change the `number` of items after creating a `CMv2` without `hiddenSettings`, you can withdraw rent of your current `CMv2` and then create a new one.

<br>

> :stop_sign: WARNING :stop_sign:
> <br>
> You need to be careful when updating a live Candy Machine, since setting a wrong value will immediately affect its functionality.

<br>

## Update Settings

You will need to prepare a config file with the updated setting values. For example, if we want to change the mint price from the original value of `1` to `0.5` SOL and keep all other values unchanged, we would modify our `config.json` file to:

```json
{
    "price": 0.5,
    "number": 10,
    "gatekeeper": null,
    "solTreasuryAccount": "<YOUR WALLET ADDRESS>",
    "splTokenAccount": null,
    "splToken": null,
    "goLiveDate": "25 Dec 2021 00:00:00 GMT",
    "endSettings": null,
    "whitelistMintSettings": null,
    "hiddenSettings": null,
    "storage": "arweave",
    "ipfsInfuraProjectId": null,
    "ipfsInfuraSecret": null,
    "awsS3Bucket": null,
    "noRetainAuthority": false,
    "noMutable": false
}
```
With the updated config file, we need to run the `update_candy_machine` command:

```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts update_candy_machine \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -cp config.json \
    -c example
```
If successful, the command will output the message with the update transaction confirmation:

```
update_candy_machine finished 

2zT344ZjS5FSJFsZRYE7Yu7Fg9sBtDQESSzPv1kNGezP7Mx8vDbf8geDQGvC3iMdbfo2GWCdPrZbsq58ZwmQ8136
```

<br>

## Update Authority

You can also update the authority of the Candy Machine, which is equivalent to giving away the control of the Candy Machine.

```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts update_candy_machine \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -cp config.json \
    -c example \
    --new-authority 7idYCnwadSG8quKNr2qqtt2WVTGy8xwTF5uFvAuHyY1g
```

The command above transfers the authority of the Candy Machine to the wallet `7idYCnwadSG8quKNr2qqtt2WVTGy8xwTF5uFvAuHyY1g`. After this point, only the owner of that wallet can operate the Candy Machine.

<br>

> :stop_sign: WARNING :stop_sign:
> <br>
> This operation is irreversible, once you change the authority of the Candy Machine, you will lose the right to operate it.

<br>

## Show Settings

To verify your updates were successful, you can run the `show` command:

```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts show \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -c example
```
This will get the candy machine settings and print them to the console.

<br>
<br>

# Withdraw Rent

Candy Machines use an account to store configuration and a (potentially) large list for pointers to assets to control the mint. To have this data stored on-chain, you need to pay rent in SOL - this is the cost associated to set up a Candy Machine. After a Candy Machine is fully minted, this data is useless and there is no need to continue to pay rent.

To drain the account of a Candy Machine and recover the rent SOL, you can use the `withdraw` command.

<br>

> :information_source: INFO :information_source:
> <br>
> The `withdraw` command is also useful in cases where you made mistakes in the creation of the `CMv2` as it provides a way to retrieve the SOL used in the set up of the Candy Machine.
> 
<br>

> :stop_sign: WARNING :stop_sign:
> <br>
> You should not withdraw the rent of a live Candy Machine, as the Candy Machine will stop working when you drain its account.

<br>

## Requirements 
The `withdraw` command must be executed with the keypair that created the Candy Machine and the Candy Machine ID you want to drain. Below is the argument and options for the `withdraw` command:

<br>

|argument|description|
|---     |        ---|
|  `<candy_machine_id>` | The Candy Machine ID you want to drain                |

<br>

|option                       |        description|
|---                          |                ---|
|  `-k, --keypair <PublicKey>`|                   |     SOL wallet that created the Candy Machine                         |
|`-e, --env <string>`         |	Solana cluster environment (default: devnet)                                           |
|`-d, --dry`                  |	Show the withdraw amount without withdrawing the rent                              |
|`-ch, --charity <PublicKey>` |	SOL wallet for donation|
|`-cp, --charityPercent <number>`|	Donation percentage of the total SOL drained                                           |
|`-r, --rpc-url <string>`     |	custom RPC as the withdraw is a network-intensive command                         |

<br>

The `withdraw_all` command will find all Candy Machines accounts made by this keypair and attempt to drain them. Below are the options used in most cases for the `withdraw_all` command:

<br>

|option|description|
|---    |---       |
|`-k, --keypair <PublicKey>`|	SOL wallet that created the Candy Machine|
|`-e, --env <string>	`|Solana cluster environment (default: devnet)|
|`-d, --dry`	|Show the withdraw amount without withdrawing the rent|
|`-ch, --charity <PublicKey>`|	SOL wallet for donation|
|`-cp, --charityPercent <number>`|	Donation percentage of the total SOL |drained |
|`-r, --rpc-url <string>`	| custom RPC as the withdraw is a network-intensive command |

<br>

> The `withdraw_all` command drains all Candy Machine accounts made by the specified keypair. You need to make sure that you want to drain all Candy Machines before you proceed. It is strongly advised that you first run the command with the option `--dry` to see how much you have locked up in those accounts and to make sure you are not draining an account you need.

<br>

You can also donate a percentage of the retrieved SOL to charity. But **BE CAREFUL**, this will actually take money out of the keypair you pass in and transfer it to the address you set as the `--charity` option.

<br>

## Execution

To start the withdraw process, execute the `withdraw` command:

```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts withdraw <candy_machine_id> \
    -e devnet \
    -k ~/.config/solana/devnet.json
```

To start the `withdraw_all` process, execute the `withdraw_all` command:

```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts withdraw_all \
    -e devnet \
    -k ~/.config/solana/devnet.json
```

<br>

> :bulb: TIP :bulb:
> <br>
> The example commands are directed at devnet with the `-e devnet` option. To target your withdraw command to Mainnet Beta, replace that option with `-e mainnet-beta`.

<br>

If there are Candy Machine accounts to be drained, you will see an output similar to:
```
Total Number of Candy Machine Config Accounts to drain 50.03644952 SOL locked up in configs
WARNING: This command will drain ALL of the Candy Machine config accounts that are owned by your current KeyPair, this will break your Candy Machine if its still in use.
...
HSLcb56y2wQEdaTcNoybcPJRrXuxRe3AnAXhpvJmZkMo has been withdrawn. 
...
Congratulations, 1 config accounts have been successfully drained.
Now you kinda rich, please consider supporting Open Source developers.
```
<br>
<br>

# Signing Your NFTs
Once you have finished minting, you'll want to proceed to this step. Signing your NFTs allows you to verify the creator. This is important since anyone can list an arbitrary address as a creator. Being verified means that the creator with that wallet address has signed the NFT, proving that they are the actual creator. It is also suggested to use a custom RPC for this step because it is a heavy command.

<br>

## Sign
```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts sign \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -m <metadata Address>
```
<br>

## Sign All
The command that uses `sign_all` can be used to sign an entire collection with the specified keypair.

```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts sign_all \
    -e devnet \
    -k ~/.config/solana/devnet.json \
    -c example
```
<br>

## Verified
Once verified, the verified value for the second creator will be changed from `0` to `1` as shown below. Remember that in the list of creators the first creator is the Candy Machine. If needed, you can specify the batch size using `-b`.
```json
"address": //address of the Candy Machine
"verfied": 1
"share": 0

"address": //Adress of the creator
"verfied": 1 //This creator has been verified.
"share": 100 //Share of the creator. If you added multiple creators this may be different
```
While the collection hasn't been signed, the verified creator will be the Candy Machine by default. This has the benefit of allowing allowing storefronts, marketplaces, and CLIs to query for NFTs that were minted by a Candy Machine.

<br>

For more information about this command use `-h` or `--help`:
```bash
ts-node ~/metaplex/js/packages/cli/src/candy-machine-v2-cli.ts sign_all -h
```

</details>
