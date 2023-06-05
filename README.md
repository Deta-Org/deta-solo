<<<<<<< HEAD
<p align="center"><img src="https://s3.amazonaws.com/deta-assets/logo_large_white.png" width="256" /></p>

<div align="center">
  <a href="https://circleci.com/gh/detaprotocol/workflows/solo/tree/master" style="text-decoration:none;">
    <img src="https://img.shields.io/circleci/project/github/detaprotocol/solo.svg" alt='CI' />
  </a>
  <a href='https://www.npmjs.com/package/@detaprotocol/solo' style="text-decoration:none;">
    <img src='https://img.shields.io/npm/v/@detaprotocol/solo.svg' alt='NPM' />
  </a>
  <a href='https://coveralls.io/github/detaprotocol/solo' style="text-decoration:none;">
    <img src='https://coveralls.io/repos/github/detaprotocol/solo/badge.svg?t=toKMwT' alt='Coverage Status' />
  </a>
  <a href='https://github.com/detaprotocol/solo/blob/master/LICENSE' style="text-decoration:none;">
    <img src='https://img.shields.io/github/license/detaprotocol/protocol.svg?longCache=true' alt='License' />
  </a>
  <a href='https://t.me/joinchat/GBnMlBb9mQblQck2pThTgw' style="text-decoration:none;">
    <img src='https://img.shields.io/badge/chat-on%20telegram-9cf.svg?longCache=true' alt='Telegram' />
  </a>
</div>

> Ethereum Smart Contracts and TypeScript library used for the deta Solo Trading Protocol. Currently used by [trade.deta.exchange](https://trade.deta.exchange)

**Full Documentation at [docs.deta.exchange](https://docs.deta.exchange)**

## Table of Contents

 - [Documentation](#documentation)
 - [Install](#install)
 - [Contracts](#contracts)
 - [Security](#security)
 - [Development](#development)
 - [Maintainers](#maintainers)
 - [Contributing](#contributing)
 - [License](#license)

## Documentation

Check out our full documentation at [docs.deta.exchange](https://docs.deta.exchange)

## Install

`npm i -s @detaprotocol/solo`

## Contracts

The current contract addresses can be found in [deployed.json](./migrations/deployed.json).

|Contract Name|Description|
|-------------|-------------|
|[`SoloMargin`](./contracts/protocol/SoloMargin.sol)|Main deta contract|
|[`PayableProxyForSoloMargin`](./contracts/external/proxies/PayableProxyForSoloMargin.sol)|WETH wrapper proxy|
|[`DoubleExponentInterestSetter`](./contracts/external/interestsetters/DoubleExponentInterestSetter.sol)|Sets interest rates|
|[`PolynomialInterestSetter`](./contracts/external/interestsetters/PolynomialInterestSetter.sol)|Sets interest rates|
|[`Expiry`](./contracts/external/traders/Expiry.sol)|Handles account expiries|
|[`ExpiryV2`](./contracts/external/traders/ExpiryV2.sol)|Handles account expiries (version 2)|
|[`FinalSettlement`](./contracts/external/traders/FinalSettlement.sol)|Handles final settlement of all accounts|
|[`DaiPriceOracle`](./contracts/external/oracles/DaiPriceOracle.sol)|Price oracle for DAI or SAI|
|[`WethPriceOracle`](./contracts/external/oracles/WethPriceOracle.sol)|Price oracle for WETH|
|[`UsdcPriceOracle`](./contracts/external/oracles/UsdcPriceOracle.sol)|Price oracle for USDC|
|[`AdminImpl`](./contracts/protocol/impl/AdminImpl.sol)|SoloMargin library containing admin functions|
|[`OperationImpl`](./contracts/protocol/impl/OperationImpl.sol)|SoloMargin library containing operation functions|
|[`LiquidatorProxyV1ForSoloMargin`](./contracts/external/proxies/LiquidatorProxyV1ForSoloMargin.sol)|Proxy contract for liquidating other accounts|
|[`LimitOrders`](./contracts/external/traders/LimitOrders.sol)|Contract for making limit orders using deta funds|
|[`StopLimitOrders`](./contracts/external/traders/StopLimitOrders.sol)|Contract for making stop limit orders using deta funds|
|[`CanonicalOrders`](./contracts/external/traders/CanonicalOrders.sol)|Contract for making canonical limit and canonical stop-limit orders using deta funds|
|[`SignedOperationProxy`](./contracts/external/proxies/SignedOperationProxy.sol)|Contract for sending signed operations on behalf of another account owner|
|[`Refunder`](./contracts/external/traders/Refunder.sol)|Allows sending of funds to other accounts|
|[`DaiMigrator`](./contracts/external/traders/DaiMigrator.sol)|Converts SAI positions to DAI positions|

## Security

### Independent Audits

The smart contracts were audited independently by both
[Zeppelin Solutions](https://zeppelin.solutions/) and Bramah Systems.

**[Zeppelin Solutions Audit Report](https://blog.zeppelin.solutions/solo-margin-protocol-audit-30ac2aaf6b10)**

**[Bramah Systems Audit Report](https://s3.amazonaws.com/deta-assets/deta_Audit_Report_Bramah_Systems.pdf)**

### Code Coverage

All production smart contracts are tested and have 100% line and branch coverage.

### Vulnerability Disclosure Policy

The disclosure of security vulnerabilities helps us ensure the security of our users.

**How to report a security vulnerability?**

If you believe you’ve found a security vulnerability in one of our contracts or platforms,
send it to us by emailing [security@deta.exchange](mailto:security@deta.exchange).
Please include the following details with your report:

* A description of the location and potential impact of the vulnerability.

* A detailed description of the steps required to reproduce the vulnerability.

**Scope**

Any vulnerability not previously disclosed by us or our independent auditors in their reports.

**Guidelines**

We require that all reporters:

* Make every effort to avoid privacy violations, degradation of user experience,
disruption to production systems, and destruction of data during security testing.

* Use the identified communication channels to report vulnerability information to us.

* Keep information about any vulnerabilities you’ve discovered confidential between yourself and
deta until we’ve had 30 days to resolve the issue.

If you follow these guidelines when reporting an issue to us, we commit to:

* Not pursue or support any legal action related to your findings.

* Work with you to understand and resolve the issue quickly
(including an initial confirmation of your report within 72 hours of submission).

* Grant a monetary reward based on the [OWASP risk assessment methodology](https://medium.com/detaderivatives/announcing-bug-bounties-for-the-deta-margin-trading-protocol-d0c817d1cda4).


## Development

### Compile Contracts

Requires a running [docker](https://docker.com) engine.

`npm run build`

### Compile TypeScript

`npm run build:js`

### Test

Requires a running [docker](https://docker.com) engine.

**Start test node:**

`docker-compose up`

**Deploy contracts to test node & run tests:**

`npm test`

**Just run tests (contracts must already be deployed to test node):**

`npm run test_only`

**Just deploy contracts to test node:**

`npm run deploy_test`

## Maintainers

 - **Brendan Chou**
 [@brendanchou](https://github.com/BrendanChou)
 [`brendan@deta.exchange`](mailto:brendan@deta.exchange)

 - **Antonio Juliano**
 [@antoniojuliano](https://github.com/AntonioJuliano)
 [`antonio@deta.exchange`](mailto:antonio@deta.exchange)

## License

[Apache-2.0](./blob/master/LICENSE)
=======

>>>>>>> 924b5db3fd7cb9563efbb369b546bbbf7e73b71a
