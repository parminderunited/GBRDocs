# Getting started as a validator

## Pre-requirements

In order to be a Medifakt validator, you first must see that you meet the pre-requirements:

* You know what it means to be a Medifakt validator - How to become a validator
* You have at least 100K FAKT tokens or you will have an aggregated delegation of at least 100K FAKT tokens (you can purchase FAKT token on [Uniswap](https://uniswap.exchange/swap/0x970b9bb2c0444f5e81e9d0efb84c8ccdcdcaf84d)).
* You have an always-on hardware that meets the pre-requisites -[ How to run network nodes](https://developers.medifakt.network/fuse-dev-docs/network/how-to-run-network-nodes)

## How to become a Medifakt validator

To quickly become a validator, follow this steps:

### Step 1: Download the \`quickstart.sh\` script and an \`.env\` example file:

```
mkdir fuse-validator
cd fuse-validator
wget -O quickstart.sh https://raw.githubusercontent.com/MedifaktDev/Medifakt/master/scripts/quickstart.sh
chmod 777 quickstart.sh
wget -O .env https://raw.githubusercontent.com/MedifaktDev/Medifakt/master/scripts/examples/.env.validator.example
```

### Step 2: Update the \`.env\` file:

```
set "sudo" on `PERMISSION_PREFIX` if running docker/docker-compose requires root

(optional) set 'VAL_NAME' to display a custom name on health.medifakt.network (cannot contain spaces)
```

### Step 3: Run the script as a validator:

```
./quickstart.sh
```

{% hint style="success" %}
After running the script successfully, you will see your address in the [health](https://health.medifakt.network/) site.
{% endhint %}

### Step 5: Stake and/or delegate!

#### Stake

To stake FAKT tokens, all you should do is send your FAKT tokens to the Medifakt Consensus contract address over the Medifakt network from the validator address.

{% hint style="success" %}
The Medifakt Consensus contract address: `0x786Aa3227317A2e513cFE20c5897F122650bd671`
{% endhint %}

The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to Medifakt and send the FAKT tokens (native tokens) to the Consensus contract address.

{% hint style="info" %}
You can find your key-store (containing your private key) and the password for the created account in:

`$HOME/fusenet/config/keys/FuseNetwork/UTC--xxxx`

`$HOME/fusenet/config/pass.pwd`
{% endhint %}

#### Delegate

To delegate, just send the FAKT tokens from any address to the Consensus contract address with the data: `0x5c19a95c000000000000000000000000<address without 0x>`.

{% hint style="success" %}
Example:

For the address: `0xb8ce4a040e8aa33bbe2de62e92851b7d7afd52de`\
Use: `0x5c19a95c000000000000000000000000b8ce4a040e8aa33bbe2de62e92851b7d7afd52de` as the data.

`5c19a95c` is for the `delegate(address)` function signature.

`b8ce4a040e8aa33bbe2de62e92851b7d7afd52de`in this example is an address you're delegating to (without the `0x` prefix)
{% endhint %}

### Step 6: Wait for 1 cycle (approximately 48 hours).

Wait until the next cycle is started.

{% hint style="success" %}
You can see that you are validating both in the [health](https://health.medifakt.network/) site and on the [explorer](https://explorer.medifakt.network) site.
{% endhint %}

For live support, contact us on [Telegram](https://t.me/fuseio) or [Discord](https://discord.gg/tz7ArR). Good luck and happy validating!
