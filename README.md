Abyss Finance Eth2 Depositor
=========

Abyss Eth2 Depositor allows convenient way to send 1 to 100 deposits in one transaction to Eth2 Deposit Contract.

Contracts
=========

Below is a list of contracts we use for this service:

<dl>
  <dt>SafeMath, Ownable, Pausable</dt>
  <dd>Openzepellin smart contracts. The first contract allows for processing mathematical calculations safely. The second contract allows for managing ownership. The last contract allows for pausing the contract and vice versa.</dd>
</dl>

<dl>
  <dt>AbyssEth2Depositor</dt>
  <dd>A smart contract that accepts up to 3200 ETH and sends up to 100 transactions with required collateral (32 ETH) to Eth2 Deposit Contract.</dd>
</dl>

Installation
------------

To run lockup service, install [Homebrew](https://brew.sh), [Node.js](https://nodejs.org), [Truffle](https://www.trufflesuite.com), [OpenZeppelin](https://openzeppelin.com) and pull the repository from `GitHub`:

    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
    brew install node
    npm install -g truffle
    npm install -g @openzeppelin/contracts
    mkdir projects
    cd projects
    git clone https://github.com/abyssfinance/abyss-eth2depositor
    cd abyss-eth2depositor
    truffle init


Setup your `truffle` environment, write migrations:

    truffle develop
    migrate --reset

Deployment (Mainnet)
------------

Smart contracts should be deployed with such constructor parameters:

1. `AbyssEth2Depositor.sol` _(0x00000000219ab540356cBB839Cbe05303d7705Fa)_

How to Use
------------

1. Choose amount of Eth2 validator nodes you want to create.
2. Create array with your pubkeys, withdrawal_credentials, signatures and calldata deposit_data_roots.
3. Use _deposit()_ function on `AbyssEth2Depositor` with required ETH value to make deposits to Eth2 Deposit Contract.

License
=========

MIT

Discussion
----------

For any concerns or suggestions visit us on [Telegram](https://t.me/abyssfinance) to discuss.

For security concerns, please email [security@abyss.finance](mailto:security@abyss.finance).

_© Copyright 2020, Abyss Finance_
