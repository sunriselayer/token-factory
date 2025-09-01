# Token Factory Module

This repository contains a standalone version of the `tokenfactory` module, forked from the [Osmosis](https://github.com/osmosis-labs/osmosis) blockchain.

## Overview

The `tokenfactory` module provides a flexible and powerful way for any account on a Cosmos SDK-based blockchain to create new, native tokens. These tokens are identified by a unique denomination format: `factory/{creator address}/{subdenom}`.

This module is designed to be easily integrated into other Cosmos SDK applications, providing a core piece of functionality for projects that require dynamic token creation.

## Key Features

- **Permissionless Token Creation**: Any user can create a new token by paying a creation fee.
- **Full Control for Creators**: The original creator of a token is designated as its "admin" and has exclusive rights to:
  - **Mint** new tokens of that denomination.
  - **Burn** existing tokens of that denomination.
  - **Transfer Admin Rights**: Change the designated admin to another account, allowing for DAOs or multisigs to manage a token.
- **Bank Module Integration**: All tokens created by this module are native assets, fully compatible with the standard `x/bank` module for transfers and balance management.

## Usage

To integrate this module into your own Cosmos SDK application, you will need to:

1.  Add this repository to your application's `go.mod` file.
2.  Include the `TokenFactory` module in your application's module manager (`app.go`).
3.  Configure the necessary keepers and genesis state.
4.  Run migrations if you are adding this to an existing chain.

## Disclaimer

This module has been extracted from a live, production blockchain. However, the process of isolating it into a standalone repository may introduce issues. Thorough testing is highly recommended before using this in a production environment.
