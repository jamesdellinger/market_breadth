# Calculating SPX Market Breadth
Lately, I've been using [Breadth.app](https://breadth.app/breadth)'s excellent SPX breadth indicator to get a feel for where we are in the market's [breadth cycle](https://www.investopedia.com/terms/m/market_breadth.asp) (thanks to [San](https://twitter.com/sanntrades)'s prior [recommendation](https://twitter.com/sanntrades/status/1345944235971928065)).

Unfortunately, seeing as how the site loads in Chinese and has a link to an English version that only appears sporadically, it wasn't immediately clear to me exactly how their market breadth score was calculated. Thankfully, it turns out that calculating market breadth is really easy, and after a bit of trial and error I was able to replicate [Breadth.app](https://breadth.app/breadth)'s numbers on my own and from scratch in Python.

The notebook in this repo demonstrates how write some Python functions that'll generate the same market breadth graph that you'll find on the breadth.app website. This might be useful if **(a)** you'd like to learn how to do this from scratch, and or **(b)** you're interested in experimenting with using a different baseline like the 50 day EMA (Breadth.app uses the 20 day SMA). 

* [Ipython Notebook](https://github.com/jamesdellinger/market_breadth/blob/main/market_breadth.ipynb)

#### Acknowledgements
Breadth.app was originally created by [@lonecapital](https://twitter.com/LoneCapital) and as best as I can tell, uses a [codebase](https://github.com/bankrollhunter/market-breadth) written by [hk-lei](https://github.com/hk-Lei) and [kentio](https://github.com/kentio). The site also incorporates design work done by [jchang274](https://github.com/jchang274) and [tianyuan09](https://github.com/tianyuan09/financialdataInR). With the exception of the Wikipedia scraping function, which I [borrow directly](https://github.com/bankrollhunter/market-breadth/blob/70df4e75b17c2c462cdb2cb06b50e482083fc275/tools/util/us.py#L26) from hk-lei, all of the code that follows below is my own creation. 

Nonetheless, the authors' [repo](https://github.com/bankrollhunter/market-breadth) was a crucial reference that helped me confirm, generally-speaking, what steps are necesssary to generate SPX market breadth data from scratch. Their work clued me in to the fact that the [TA-Lib](https://mrjbq7.github.io/ta-lib/) library makes it easy to calculate SMAs, EMAs, etc., and that [yfinance](https://pypi.org/project/yfinance/) makes for a user-friendly and free way to download the market data for all SPX stocks.

#### Dependencies
* [environment.yml](https://github.com/jamesdellinger/market_breadth/blob/master/environment.yml)