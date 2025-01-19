# Project Automation with Makefile

This project uses a `Makefile` to automate various development tasks such as building, testing, deploying, and managing dependencies. Below is a guide to understanding and using the available commands.

## Prerequisites

- [Foundry](https://github.com/foundry-rs/foundry) installed on your system.
- Ensure you have `.env` file configured with necessary variables like `SEPOLIA_RPC_URL`, `ACCOUNT`, and `ETHERSCAN_API_KEY`.

## Commands Overview

### General Commands

| Command         | Description                                                                      |
|-----------------|----------------------------------------------------------------------------------|
| `make all`      | Cleans, removes modules, installs dependencies, updates, and builds the project. |
| `make clean`    | Cleans the repository by removing build artifacts.                               |
| `make remove`   | Removes git submodules and library dependencies.                                 |
| `make install`  | Installs required dependencies without committing changes.                       |
| `make update`   | Updates the project's dependencies.                                              |
| `make build`    | Builds the project using Foundry.                                                |
| `make test`     | Runs tests using Foundry.                                                        |
| `make snapshot` | Takes a snapshot of the current state for testing purposes.                      |
| `make format`   | Formats the code using Foundry.                                                  |

### Local Development

| Command         | Description                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| `make anvil`    | Starts a local Ethereum node with deterministic accounts.                   |

### Deployment

| Command                  | Description                                                          |
|--------------------------|----------------------------------------------------------------------|
| `make deploy`            | Deploys the `DeployFundMe` script locally.                           |
| `make deploy-sepolia`    | Deploys the `DeployFundMe` script on Sepolia testnet.                |

### Interactions

| Command         | Description                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| `make fund`     | Executes `FundFundMe` interaction script with the sender's address.         |
| `make withdraw` | Executes `WithdrawFundMe` interaction script with the sender's address.     |

## Environment Variables

To ensure proper functionality, create a `.env` file in the root directory and define the following variables:

- **SEPOLIA_RPC_URL**: The RPC URL for Sepolia testnet
`https://eth-sepolia.g.alchemy.com/v2/OXgy0cZ2Nax7iFQr3D_DkkRptv_byTa_`.
- **ACCOUNT**: Your foundry account. You can use:
    ```bash 
    cast wallet import <new acc name> --interactive
- **ETHERSCAN_API_KEY**: API key for verifying contracts on Etherscan.

## Notes

- **Default Private Keys**:
  - Anvil: `0xac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80`

- Replace `<sender's address>` in `make fund` and `make withdraw` commands with the actual sender's address.

## Help

To list all available commands, run:

```bash
make help
