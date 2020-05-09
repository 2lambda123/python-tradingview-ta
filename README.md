# python-tradingview-ta [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.png?v=103)](https://github.com/ellerbrock/open-source-badges/)
 A python module to scrape tradingview's technical analysis.
 
## Features
 Scrape analysis from TradingView, ex: from [XLMBTC](http://s.tradingview.com/embed-widget/technical-analysis/?locale=en#%7B%22interval%22%3A%221m%22%2C%22width%22%3A%22100%25%22%2C%22isTransparent%22%3Afalse%2C%22height%22%3A%22100%25%22%2C%22symbol%22%3A%22BINANCE%3AXLMBTC%22%2C%22showIntervalTabs%22%3Atrue%2C%22colorTheme%22%3A%22dark%22%2C%22utm_medium%22%3A%22widget_new%22%2C%22utm_campaign%22%3A%22technical-analysis%22%7D), to a list. Works by using selenium webdriver to scrape elements from tradingview's technical analysis widget.
 
## Requirements
 - Python
 - [Selenium](https://www.selenium.dev/selenium/docs/api/py/#installing)
 - [Webdriver](https://www.selenium.dev/selenium/docs/api/py/#drivers)
## Quickstart
```python
import tradingview_ta

analysis = tradingview_ta("xlmbtc", "1m")

print(analysis)
#Example output: ["Buy", 3, 10, 17]
```
## Usage
#### Import module
```python
import tradingview_ta
```

#### Set webdriver (optional, default: chrome)
```python
tradingview_ta.set_driver("WEBDRIVER NAME")
```
 Available webdriver: Chrome, Firefox, Safari, Edge. 
 See selenium's [documentation](https://www.selenium.dev/selenium/docs/api/py/#drivers) for webdriver installation.

#### Get analysis
```python
analysis = tradingview_ta.get_analysis("PAIR/TICKER/SYMBOL/WHATEVER YOU WANT TO CALL IT", "INTERVAL")
```
 Pair/Ticker/Symbol example: "btcusdt", "googl", "aapl", etc. 
 <br>
 You may use the exchanger's name too, for example: "binance:btcusdt" or "nasdaq:aapl"
 <br>
 <br>
 Available interval:
  - "1m" for 1 minute.
  - "5m" for 5 minutes.
  - "15m" for 15 minutes.
  - "1h" for 1 hour.
  - "4h" for 4 hours.
  - etc.
 
 #### List Details
  The ```get_analysis()``` function will return a list, containing the following value.
  - The first index (string) shows the recommendation from TradingView, the value can contain "Buy", "Strong Buy", "Neutral", "Sell", or "Strong Sell".
  - The second index (int) shows the number/count of Sell analysis
  - The third index (int) shows the number/count of Neutral analysis
  - The fourth index (int) shows the number/count of Buy analysis

## Contributing
 You can fork this repository or submit a pull request. Any pull request (documentation, bug fix, features, etc) are welcomed.
 
## License
 Please see the LICENSE file.
