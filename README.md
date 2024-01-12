## Vulnerability
Vault shares can be inflated by donating ERC20 token to the vault.

Attacker can exploit this behavior to steal other user's deposits.

## results
[source!](/results/results.png)


## Source_link 
[source!](https://solidity-by-example.org/hacks/vault-inflation/)


## Example Scenario
User 0 front runs user 1's deposit.

User 0 deposits 1. <br>
User 0 donates 100 * 1e18. This inflates the value of each share.<br>
User 1 deposits 100 * 1e18. This mints 0 shares to user 1.<br>
User 0 withdraws all 200 * 1e18 + 1.<br>
<br>

## Protections
Min shares -> protects from front running<br>
Internal balance -> protects from donation<br>
Dead shares -> contract is first depositor<br>
Decimal offset (OpenZeppelin ERC4626)<br>

## Foundry

**Foundry is a blazing fast, portable and modular toolkit for Ethereum application development written in Rust.**

Foundry consists of:

-   **Forge**: Ethereum testing framework (like Truffle, Hardhat and DappTools).
-   **Cast**: Swiss army knife for interacting with EVM smart contracts, sending transactions and getting chain data.
-   **Anvil**: Local Ethereum node, akin to Ganache, Hardhat Network.
-   **Chisel**: Fast, utilitarian, and verbose solidity REPL.

## Documentation

https://book.getfoundry.sh/

## Usage

### Build

```shell
$ forge build
```

### Test

```shell
$ forge test
```

### Format

```shell
$ forge fmt
```

### Gas Snapshots

```shell
$ forge snapshot
```

### Anvil

```shell
$ anvil
```

### Deploy

```shell
$ forge script script/Counter.s.sol:CounterScript --rpc-url <your_rpc_url> --private-key <your_private_key>
```

### Cast

```shell
$ cast <subcommand>
```

### Help

```shell
$ forge --help
$ anvil --help
$ cast --help
```
