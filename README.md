# Rocket Pool Contract v1.2 Verification

This repo allows third parties to easily verify that the contracts deployed for the v1.2 upgrade of Rocket Pool
match the source code of the contracts in the `v1.2` branch of the Rocket Pool smart contract repository.

# How it works

1. It clones the `v1.2` branch from the official Rocket Pool GitHub repository at https://github.com/rocket-pool/rocketpool
2. It compares the source for `RocketUpgradeOneDotOne.sol` against the verified source on Etherscan at the following addresses:
   1. Goerli: 0xd3d74b3532f393f381e18f3b0cdacfde23d669a6
   2. Mainnet: 0x9a0b5d3101d111EA0edD573d45ef2208CC97984a
3. It calls each of the view methods on the upgrade contract to retrieve the address of each of the new contracts
4. It compares the verified source on Etherscan of each of these addresses to confirm they match the code in the git repo

# How to run it

Copy `.env.example` to `.env` and fill out the appropriate values.

The `verify.sh` script performs the required setup and executes the verification script. Simply run:

```bash
./verify.sh
```