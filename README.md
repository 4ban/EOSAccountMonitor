# eosaccountmonitor
[<img src="https://raw.githubusercontent.com/4ban/EOSAccountMonitor/master/.github/black_img.png">](https://www.buymeacoffee.com/4ban)

[![standard-readme compliant](https://img.shields.io/badge/standard--readme-OK-green.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

> A simple tool that monitor resources and sends daily reports about states for all accounts.

<img width="706" alt="Screen Shot 2019-05-21 at 7 32 32 PM" src="https://user-images.githubusercontent.com/2269864/58137831-d319b680-7c01-11e9-839a-c21945ab59a3.png">

Since the percentage of RAM is not very reliable metric, the estimated number of remaining transactions based on the average RAM per transaction size is used.

Using online blockchain monitor, for the considered accounts, the average value of the used RAM for the `transfer` action is taken (`160 bytes`).
Based on this, the estimated number of remaining transactions is calculated.

In my case there was an account which took `747 bytes` of RAM for each `transfer` action. This account marked as `heavy` and the estimated number of remaining transactions is calculated based on this number.

Such options will be added in the future release soon. For now you can modify it by directly changing the code.

## Table of Contents

- [Install](#install)
- [Usage](#usage)
- [Maintainers](#maintainers)
- [Contribute](#contribute)
- [License](#license)

## Background

## Install

The script is written by using Python 3.

```
pip3 install requests
pip3 install tabulate
```

## Usage

Fill the config file:
```bash
[DEFAULT]
# The timeout for checking accounts in hours
TIMEOUT=5

# The timeout for sending statistics in hours
STATS_TIMEOUT=24

# Producer
PRODUCER=https://eos.greymass.com

ACCOUNTS=eosio.token,whaleextoken,community123,prospectorsg

# Credentials (Gmail server)
MAIL_LOGIN={email@gmail.com}
MAIL_PASS={password}

# Recipients
RECIPIENTS=email1@gmail.com,email2@gmail.com

# Common transaction (bytes)
TR_USE=160

# Heavy transaction (bytes)
HEAVY_TR_USE=747
HEAVY_ACCOUNTS=accountname
```

Run: `python3 app.py`

## Maintainers

[@sylvaincormier](https://github.com/sylvaincormier)

## Contribute

See [the contribute file](contribute.md)!

PRs accepted.

Small note: If editing the README, please conform to the [standard-readme](https://github.com/RichardLitt/standard-readme) specification.

## License

MIT © 2019 Volentix Labs Inc
