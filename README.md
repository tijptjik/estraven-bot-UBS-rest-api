[![Get professional and fast support](https://raw.githubusercontent.com/LUCIT-Systems-and-Development/unicorn-binance-suite/master/images/support/LUCIT-get-professional-and-fast-support.png)](https://www.lucit.tech/get-support.html)

[![Github](https://img.shields.io/badge/source-github-cbc2c8)](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api)
[![GitHub Release](https://img.shields.io/github/release/LUCIT-Systems-and-Development/unicorn-binance-rest-api.svg?label=github)](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/releases)
[![GitHub Downloads](https://img.shields.io/github/downloads/LUCIT-Systems-and-Development/unicorn-binance-rest-api/total?color=blue)](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/releases)
[![Conda Release](https://img.shields.io/conda/vn/conda-forge/unicorn-binance-rest-api.svg?color=blue)](https://anaconda.org/conda-forge/unicorn-binance-rest-api)
[![Conda Downloads](https://img.shields.io/conda/dn/conda-forge/unicorn-binance-rest-api.svg?color=blue)](https://anaconda.org/conda-forge/unicorn-binance-rest-api)
[![PyPi Release](https://img.shields.io/pypi/v/unicorn-binance-rest-api?color=blue)](https://pypi.org/project/unicorn-binance-rest-api/)
[![PyPi Downloads](https://pepy.tech/badge/unicorn-binance-rest-api)](https://pepy.tech/project/unicorn-binance-rest-api)
[![License](https://img.shields.io/github/license/LUCIT-Systems-and-Development/unicorn-binance-rest-api.svg?color=blue)](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/LICENSE)
[![Supported Python Version](https://img.shields.io/pypi/pyversions/unicorn_binance_rest_api.svg)](https://www.python.org/downloads/)
[![PyPI - Status](https://img.shields.io/pypi/status/unicorn_binance_rest_api.svg)](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/issues)
[![CodeQL](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/actions/workflows/codeql-analysis.yml/badge.svg)](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/actions/workflows/codeql-analysis.yml)
[![Unit Tests](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/actions/workflows/unit-tests.yml/badge.svg)](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/actions/workflows/unit-tests.yml)
[![Azure Pipelines](https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/unicorn-binance-rest-api-feedstock?branchName=main)](https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=15697&branchName=main)
[![codecov](https://codecov.io/gh/LUCIT-Systems-and-Development/unicorn-binance-rest-api/branch/master/graph/badge.svg?token=5I03AZ3F5S)](https://codecov.io/gh/LUCIT-Systems-and-Development/unicorn-binance-rest-api)
[![Read the Docs](https://img.shields.io/badge/read-%20docs-yellow)](https://unicorn-binance-rest-api.docs.lucit.tech/)
[![Read How To`s](https://img.shields.io/badge/read-%20howto-yellow)](https://medium.lucit.tech)
[![Telegram](https://img.shields.io/badge/chat-telegram-41ab8c)](https://t.me/unicorndevs)
[![Gitter](https://badges.gitter.im/unicorn-binance-suite/unicorn-binance-rest-api.svg)](https://gitter.im/unicorn-binance-suite/unicorn-binance-rest-api?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

[![LUCIT-UBRA-Banner](https://raw.githubusercontent.com/lucit-systems-and-development/unicorn-binance-rest-api/master/images/logo/LUCIT-UBRA-Banner-Readme.png)](https://www.lucit.tech/unicorn-binance-rest-api.html)

# UNICORN Binance REST API

[Description](#description) | [Installation](#installation-and-upgrade) | [How To](#howto) |
[Documentation](#documentation) | [Examples](#examples) | [Change Log](#change-log) | [Wiki](#wiki) | [Social](#social) |
[Notifications](#receive-notifications) | [Bugs](#how-to-report-bugs-or-suggest-improvements) | 
[Contributing](#contributing) | [Leave a review](#you-want-to-say-thank-you) | [Disclaimer](#disclaimer) | [Commercial Support](#commercial-support)

An unofficial Python API to use the Binance REST API`s (com+testnet, com-margin+testnet, com-isolated_margin+testnet, 
com-futures+testnet, us, tr) in a easy, fast, flexible, robust and fully-featured way. 

Part of ['UNICORN Binance Suite'](https://www.lucit.tech/unicorn-binance-suite.html).

```
from unicorn_binance_rest_api.manager import BinanceRestApiManager

api_key = "aaa"
api_secret = "bbb"
ubra = BinanceRestApiManager(api_key, api_secret, exchange="binance.com")

# get market depth
depth = ubra.get_order_book(symbol='BNBBTC')
print(f"{depth}")

# get all symbol prices
prices = ubra.get_all_tickers()
print(f"{prices}")

# get the used weight: 
# https://github.com/binance-us/binance-official-api-docs/blob/master/rest-api.md#limits
print(f"Used weight: {ubra.get_used_weight()}")
```

### Get the right [logger](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/example_logging.py):
```
logging.getLogger("unicorn_binance_rest_api")
```

## Description
This is a fork of Sam McHardy`s [python-binance 0.7.10](https://github.com/sammchardy/python-binance) - package. 
Extended, cleaned up and reduced to pure REST tasks, with PRs added and improved. No asyncio support!!

The Python module [UNICORN Binance REST API](https://www.lucit.tech/unicorn-binance-rest-api.html) 
provides an API to the Binance REST API`s of 
[Binance](https://github.com/binance-exchange/binance-official-api-docs) 
([+Testnet](https://testnet.binance.vision/)), 
[Binance Margin](https://binance-docs.github.io/apidocs/spot/en/#user-data-streams) 
([+Testnet](https://testnet.binance.vision/)), 
[Binance Isolated Margin](https://binance-docs.github.io/apidocs/spot/en/#listen-key-isolated-margin)
([+Testnet](https://testnet.binance.vision/)), 
[Binance Futures](https://binance-docs.github.io/apidocs/futures/en/#websocket-market-streams) 
([+Testnet](https://testnet.binancefuture.com)), 
[Binance COIN-M Futures](https://binance-docs.github.io/apidocs/delivery/en/#change-log),
[Binance US](https://github.com/binance-us/binance-official-api-docs) and
[Binance TR](https://www.trbinance.com/apidocs) and needs to be used with a valid 
[api_key and api_secret](https://medium.lucit.tech/how-to-create-a-binance-api-key-and-api-secret-3bb5f47e360d)
from the Binance Exchange 
[www.binance.com](https://www.binance.com/userCenter/createApi.html), 
[testnet.binance.vision](https://testnet.binance.vision/) or
[www.binance.us](https://www.binance.us/userCenter/createApi.html).

Be aware that the Binance REST API is request based. if you want to send and receive high frequency and high volume data, you can use the [UNICORN Binance Websocket API](https://www.lucit.tech/unicorn-binance-websocket-api.html) in combination. 

### What are the benefits of the UNICORN Binance REST API?
- Supported exchanges: 

| Exchange                                                           | Exchange string                       | 
|--------------------------------------------------------------------|---------------------------------------| 
| [Binance](https://www.binance.com)                                 | `binance.com`                         |
| [Binance Testnet](https://testnet.binance.vision/)                 | `binance.com-testnet`                 |
| [Binance Margin](https://www.binance.com)                          | `binance.com-margin`                  |
| [Binance Margin Testnet](https://testnet.binance.vision/)          | `binance.com-margin-testnet`          |
| [Binance Isolated Margin](https://www.binance.com)                 | `binance.com-isolated_margin`         |
| [Binance Isolated Margin Testnet](https://testnet.binance.vision/) | `binance.com-isolated_margin-testnet` |
| [Binance USD-M Futures](https://www.binance.com)                   | `binance.com-futures`                 |
| [Binance USD-M Futures Testnet](https://testnet.binancefuture.com) | `binance.com-futures-testnet`         |
| [Binance Coin-M Futures](https://www.binance.com)                  | `binance.com-coin_futures`            |
| [Binance US](https://www.binance.us)                               | `binance.us`                          |
| [Binance TR](https://www.trbinance.com)                            | `trbinance.com`                       |

- Helpful management features like 
[`get_used_weight()`](https://unicorn-binance-rest-api.docs.lucit.tech/unicorn_binance_rest_api.html#unicorn_binance_rest_api.manager.BinanceRestApiManager.get_used_weight), 


- Integration of [test cases](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/actions/workflows/unit-tests.yml) and [examples](#examples).

- Customizable base URL and request timeout.

- *Socks5 Proxy* support:
  ```
  ubra = BinanceRestApiManager(exchange="binance.com", socks5_proxy_server="127.0.0.1:9050") 
  ```
  Read the [docs](https://unicorn-binance-rest-api.docs.lucit.tech/unicorn_binance_rest_api.html#unicorn_binance_rest_api.manager.BinanceRestApiManager)
  or this [how to](https://medium.com/@oliverzehentleitner/how-to-connect-to-binance-com-rest-api-using-python-via-a-socks5-proxy-638dbbecacfd) 
  for more information or try 
  [example_socks5_proxy.py](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/example_socks5_proxy.py).

- Excessively tested on Linux, Mac and Windows

If you like the project, please [![star](https://raw.githubusercontent.com/lucit-systems-and-development/unicorn-binance-rest-api/master/images/misc/star.png)](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/stargazers) it on 
[GitHub](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api)!

## Installation and Upgrade
The current dependencies are listed 
[here](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/requirements.txt).

If you run into errors during the installation take a look [here](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/wiki/Installation).

### A wheel and a source file of the latest release with `pip`  from [PyPI](https://pypi.org/project/unicorn-binance-rest-api/)
`pip install unicorn-binance-rest-api --upgrade`

### A conda package of the latest release with `conda` from [Anaconda](https://anaconda.org/conda-forge/unicorn-binance-rest-api) via [CONDA-FORGE](https://conda-forge.org).
`conda install -c conda-forge unicorn-binance-rest-api`

`conda update -c conda-forge unicorn-binance-rest-api`

### From source of the latest release with PIP from [Github](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api)
#### Linux, macOS, ...
Run in bash:

`pip install https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/archive/$(curl -s https://api.github.com/repos/lucit-systems-and-development/unicorn-binance-rest-api/releases/latest | grep -oP '"tag_name": "\K(.*)(?=")').tar.gz --upgrade`

#### Windows
Use the below command with the version (such as 1.9.0) you determined 
[here](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/releases/latest):

`pip install https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/archive/1.9.0.tar.gz --upgrade`

### From the latest source (dev-stage) with PIP from [Github](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api)
This is not a release version and can not be considered to be stable!

`pip install https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/tarball/master --upgrade`

### [Conda environment](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html), [Virtualenv](https://virtualenv.pypa.io/en/latest/) or plain [Python](https://www.python.org)
Download the [latest release](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/releases/latest) 
or the [current master branch](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/archive/master.zip)
 and use:
 
- ./environment.yml
- ./requirements.txt
- ./setup.py

## Change Log
[https://unicorn-binance-rest-api.docs.lucit.tech/CHANGELOG.html](https://unicorn-binance-rest-api.docs.lucit.tech/CHANGELOG.html)

## Documentation
- [General](https://unicorn-binance-rest-api.docs.lucit.tech/)
- [Modules](https://unicorn-binance-rest-api.docs.lucit.tech/modules.html)

## Examples
- [example_doing_something.py](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/example_doing_something.py)
- [example_easy_migration_from_python-binance.py](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/example_easy_migration_from_python-binance.py)
- [example_historical_data.py](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/example_historical_data.py)
- [example_logging.py](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/example_logging.py)
- [example_orders.py](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/example_orders.py)
- [example_socks5_proxy.py](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-websocket-api/blob/master/example_socks5_proxy.py)
- [example_version_of_this_package.py](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/example_version_of_this_package.py)

## Howto
- [Restful Binance Requests in Python with UNICORN Binance REST API](https://medium.lucit.tech/restful-binance-requests-in-python-with-unicorn-binance-rest-api-288f364e92a8)
- [How to Download Klines from Binance using Python?](https://medium.lucit.tech/how-to-download-data-from-binance-using-python-8f1b6e8f19f3)
- [How to Connect to binance.com REST API using Python via a SOCKS5 Proxy](https://medium.lucit.tech/how-to-connect-to-binance-com-rest-api-using-python-via-a-socks5-proxy-638dbbecacfd)

## Project Homepage
[https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api)

## Wiki
[https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/wiki](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/wiki)

## Social
- [Discussions](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/discussions)
- [https://t.me/unicorndevs](https://t.me/unicorndevs)
- [https://dev.binance.vision](https://dev.binance.vision)
- [https://community.binance.org](https://community.binance.org)

## Receive Notifications
To receive notifications on available updates you can 
[![watch](https://raw.githubusercontent.com/lucit-systems-and-development/unicorn-binance-rest-api/master/images/misc/watch.png)](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/watchers) 
the repository on [GitHub](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api), write your 
[own script](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/example_version_of_this_package.py) 
with using 
[`is_update_availabe()`](https://unicorn-binance-rest-api.docs.lucit.tech/unicorn_binance_rest_api.html?highlight=is_update_availabe#unicorn_binance_rest_api.manager.BinanceRestApiManager.is_update_availabe).

Follow us on [Twitter](https://twitter.com/LUCIT_SysDev) or on [Facebook](https://www.facebook.com/lucit.systems.and.development) for general news about the [unicorn-binance-suite](https://www.lucit.tech/unicorn-binance-suite.html)!

To receive news (like inspection windows/maintenance) about the Binance API`s subscribe to their telegram groups: 

- [https://t.me/binance_api_announcements](https://t.me/binance_api_announcements)
- [https://t.me/binance_api_english](https://t.me/binance_api_english)
- [https://t.me/Binance_USA](https://t.me/Binance_USA)
- [https://t.me/TRBinanceTR](https://t.me/TRBinanceTR)
- [https://t.me/BinanceDEXchange](https://t.me/BinanceDEXchange)
- [https://t.me/BinanceExchange](https://t.me/BinanceExchange)

## How to report Bugs or suggest Improvements?
[List of planned features](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/issues?q=is%3Aissue+is%3Aopen+label%3Aenhancement) - 
click ![thumbs-up](https://raw.githubusercontent.com/lucit-systems-and-development/unicorn-binance-rest-api/master/images/misc/thumbup.png) if you need one of them or suggest a new feature!

Before you report a bug, [try the latest release](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api#installation-and-upgrade). If the issue still exists, provide the error trace, OS 
and Python version and explain how to reproduce the error. A demo script is appreciated.

If you dont find an issue related to your topic, please open a new [issue](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/issues)!

[Report a security bug!](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/security/policy)

## Contributing
[UNICORN Binance REST API](https://www.lucit.tech/unicorn-binance-rest-api.html) is an open 
source project which welcomes contributions which can be anything from simple documentation fixes and reporting dead links to new features. To 
contribute follow 
[this guide](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/blob/master/CONTRIBUTING.md).
 
### Contributors
[![Contributors](https://contributors-img.web.app/image?repo=lucit-systems-and-development/unicorn-binance-rest-api)](https://github.com/LUCIT-Systems-and-Development/unicorn-binance-rest-api/graphs/contributors)

We ![love](https://raw.githubusercontent.com/lucit-systems-and-development/unicorn-binance-rest-api/master/images/misc/heart.png) open source!

## You want to say Thank You?
We hope you are enjoying using our libraries and that they are proving to be useful to you. If you have a moment, we would greatly appreciate it if you could leave us a [review on Google](https://g.page/r/CbfHlcs8BfG8EAg/review). Thank you for your support!

## Disclaimer
This project is for informational purposes only. You should not construe this information or any other material as 
legal, tax, investment, financial or other advice. Nothing contained herein constitutes a solicitation, recommendation, 
endorsement or offer by us or any third party provider to buy or sell any securities or other financial instruments in 
this or any other jurisdiction in which such solicitation or offer would be unlawful under the securities laws of such 
jurisdiction.

### If you intend to use real money, use it at your own risk!

Under no circumstances will we be responsible or liable for any claims, damages, losses, expenses, costs or liabilities 
of any kind, including but not limited to direct or indirect damages for loss of profits.

### SOCKS5 Proxy / Geoblocking
We would like to explicitly point out that in our opinion US citizens are exclusively authorized to trade on Binance.US 
and that this restriction must not be circumvented!

The purpose of supporting a SOCKS5 proxy in the UNICORN Binance Suite and its modules is to allow non-US citizens to use 
US services. For example, Github actions with UBS will not work without a SOCKS5 proxy, as they will inevitably run on 
servers in the US and be blocked by Binance.com. Moreover, it also seems justified that traders, data scientists and 
companies from the US analyze binance.com market data - as long as they do not trade there.

## Commercial Support

[![Get professional and fast support](https://raw.githubusercontent.com/LUCIT-Systems-and-Development/unicorn-binance-suite/master/images/support/LUCIT-get-professional-and-fast-support.png)](https://www.lucit.tech/get-support.html)

***Do you need a developer, operator or consultant?*** [Contact us](https://www.lucit.tech/contact.html) for a non-binding initial consultation!
