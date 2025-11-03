## Setup your development environment 

Follow the steps [here](https://docs.arbitrum.io/stylus/quickstart#setting-up-your-development-environment) to set up your development environment.


## Guide to WEEK2 HOMEWORK 1

This task involves filling in the missing parts of the stylus contracts in `push-based-distributor/src/lib.rs`.

Example:
```rust
// Get count from a different contract
let count = match /* 1. _______ */ {
    Ok(value) => value,
    Err(_) => return Err(Error::NoCount(NoCount {})),
};
```

Solution:
```rust
let count = match diff_contract.getCount(&mut *self) {
    Ok(value) => value,
    Err(_) => return Err(Error::NoCount(NoCount {})),
};
```

### push-based-distributor

1. `/* 1______ */` (line 38)

    Hint: Replace with the macro that allows us to declare Solidity-like errors or events.

2. `/* 2______ */` (line 46)

    Hint: Match the `InsufficientBalance` variant to its custom error.

3. `/* 3______ */` (line 54)

    Hint: Wrap the `_token` address around `IERC20` interface.

4. `/* 4______ */` (line 61)

    Hint: Replace with the `InsufficientBalance` custom error.

5. `/* 5______ */` (line 73)

    Hint: Make a cross-contract call to transfer tokens to the recipient.


## Test
Run the following command
```
cargo stylus check
```

if no error then the contract is valid and deployable on-chain.