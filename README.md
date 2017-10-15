### About
Forknote is innovative way to create Cryptonote (https://cryptonote.org) based cryptotokens. It gives the users the ability to create cryptotokens just by creating a simple configuration file.

### Dependencies
* GCC 4.7.3 or later     (http://gcc.gnu.org/)
* CMake 2.8.6 or later   (http://www.cmake.org/)
* Boost 1.55 or later    (http://www.boost.org/)
* MSVC 2013 (Windows only)

Step by step Windows instructions:
https://github.com/forknote/cryptonote-generator/blob/master/docs/windows-requirements-install.md

Ubuntu (tested on Ubuntu 14.04) / Mac dependencies install script:
https://github.com/forknote/cryptonote-generator/blob/master/configure.sh


### Usage
0. Download http://forknote.net/download/ or compile the binaries
* To use forknotecoin.conf
1. Create New folder and rename configs
2. create forknotecoin.conf using the parameters below and save as forknotecoin.conf
3. Use forknotecoin.conf configuration file.
4. Start the daemon: forknoted --config-file configs/forknotecoin.conf from command line or create .forknoted.bat file
5. Allow block chain to fully sync and leave open before launch of simplewallet
6. Start the simplewallet: simplewallet --config-file configs/forknotecoin.conf from command line or create simplewallet.bat file
7. Simplewallet options
8. [O]pen existing wallet, [G]enerate new wallet file, [I]mport wallet or [E]xit.
9. To use [I]mport wallet option you will need to have "Spend secret key" and "View secret key"
10. To transfer coins: use "transfer" command
* [uint] mixin_count (number of transaction to mix your with from 0-4)
* [string] address (receiving party wallet address)
* [double] amount (amount of coins to send)
* [string] -p payment_id (unique ID "optional")
* [double] -f fee (amount of fee to spend sending tx "optional")
###  example:
a) transfer 0 Ftwkidoisij 10
* will transfer 10 coins to address Ftwkidoisij

b) transfer 0 Ftwkidoisij 10 -p 475iuoj -f .001
* will transfer 10 coins to address Ftwkidoisij with ID 475iuoj

c) transfer 0 Ftwkidoisij 10 -p 475iuoj Ftwieojfso 30 -p 7364rjfuiei-f .1
* will transfer 10 coins to address Ftwkidoisij with ID 475iuoj and 30 coins to Ftwieojfso

11. Solo mining using CPU
* miner --daemon-address localhost:43302 --address yourwalletaddresshere --threads 4 --log-level 5 from command line or create miner.bat file
* --threads 4 (max number of CPUs to use)
* --log-level 5 (can be set 1-5)

```
Always close both simplewallet and daemon using "exit" command
```

### Configuration parameters
To use forknotecoin.conf
1. Create New folder and rename configs
2. create forknotecoin.conf using the parameters below and save as forknotecoin.conf

forknotecoin.conf:
```
EMISSION_SPEED_FACTOR=30
DIFFICULTY_TARGET=110
CRYPTONOTE_DISPLAY_DECIMAL_POINT=10
MONEY_SUPPLY=3500000000000000000
GENESIS_BLOCK_REWARD=3465000000000000000
SYNC_FROM_ZERO=1
DEFAULT_DUST_THRESHOLD=100000
MINIMUM_FEE=100000
CRYPTONOTE_MINED_MONEY_UNLOCK_WINDOW=11
CRYPTONOTE_BLOCK_GRANTED_FULL_REWARD_ZONE=100000
MAX_TRANSACTION_SIZE_LIMIT=100000
CRYPTONOTE_PUBLIC_ADDRESS_BASE58_PREFIX=86
DIFFICULTY_CUT_V1=60
DIFFICULTY_CUT_V2=60
DIFFICULTY_CUT=0
DIFFICULTY_LAG_V1=15
DIFFICULTY_LAG_V2=15
DIFFICULTY_LAG=0
DIFFICULTY_WINDOW_V1=786
DIFFICULTY_WINDOW_V2=786
DIFFICULTY_WINDOW=17
ZAWY_DIFFICULTY_V3=1
ZAWY_DIFFICULTY_DIFFICULTY_BLOCK_VERSION=3
p2p-bind-port=13036
rpc-bind-port=13037
BYTECOIN_NETWORK=883c76c0-7be2-8eab-d326-f7714f71aa14
CRYPTONOTE_NAME=forknote
GENESIS_COINBASE_TX_HEX=010b01ff00018080ea95c4e4898b30020d0916153c6d071630b124b18f63fe001800fbcd4b643cda5af7582e7eab0db22101055e53bf962c675d20d34ede2798d3a2107281d10c6044ef6fe94a45a5430141
MAX_BLOCK_SIZE_INITIAL=100000
UPGRADE_HEIGHT_V2=1
UPGRADE_HEIGHT_V3=30
seed-node=174.77.124.17:13036
seed-node=72.192.72.147:13036
seed-node=107.77.161.12:13036

// simplewallet parameters
wallet-rpc-bind-ip=127.0.0.1        // instead rpc-bind-ip
wallet-rpc-bind-port=33671          // instead rpc-bind-port
SYNC_FROM_ZERO=1                    // to sync the wallet from block 0. Used for premine coins or brain wallets
```

---
To learn more about cryptonote technology and view CRYPTONOTE White Paper - https://cryptonote.org/inside/
