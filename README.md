# Scrapyng - Scrapy - Study
Reference: https://docs.scrapy.org/en/latest/intro/tutorial.html

- pip install scrapy

## scraping url
`scrapy shell 'http://quotes.toscrape.com/page/1'`

- terminal
```
2021-09-24 20:12:09 [scrapy.utils.log] INFO: Scrapy 2.5.0 started (bot: tutorial)
2021-09-24 20:12:09 [scrapy.utils.log] INFO: Versions: lxml 4.6.3.0, libxml2 2.9.10, cssselect 1.1.0, parsel 1.6.0, w3lib 1.22.0, Twisted 21.7.0, Python 3.8.10 (default, Jun  2 2021, 10:49:15) - [GCC 9.4.0], pyOpenSSL 20.0.1 (OpenSSL 1.1.1f  31 Mar 2020), cryptography 2.8, Platform Linux-5.11.0-36-generic-x86_64-with-glibc2.29
2021-09-24 20:12:09 [scrapy.utils.log] DEBUG: Using reactor: twisted.internet.epollreactor.EPollReactor
2021-09-24 20:12:09 [scrapy.crawler] INFO: Overridden settings:
{'BOT_NAME': 'tutorial',
 'DUPEFILTER_CLASS': 'scrapy.dupefilters.BaseDupeFilter',
 'LOGSTATS_INTERVAL': 0,
 'NEWSPIDER_MODULE': 'tutorial.spiders',
 'ROBOTSTXT_OBEY': True,
 'SPIDER_MODULES': ['tutorial.spiders']}
2021-09-24 20:12:09 [scrapy.extensions.telnet] INFO: Telnet Password: 899ea1db5fcbfe60
2021-09-24 20:12:09 [scrapy.middleware] INFO: Enabled extensions:
['scrapy.extensions.corestats.CoreStats',
 'scrapy.extensions.telnet.TelnetConsole',
 'scrapy.extensions.memusage.MemoryUsage']
2021-09-24 20:12:09 [scrapy.middleware] INFO: Enabled downloader middlewares:
['scrapy.downloadermiddlewares.robotstxt.RobotsTxtMiddleware',
 'scrapy.downloadermiddlewares.httpauth.HttpAuthMiddleware',
 'scrapy.downloadermiddlewares.downloadtimeout.DownloadTimeoutMiddleware',
 'scrapy.downloadermiddlewares.defaultheaders.DefaultHeadersMiddleware',
 'scrapy.downloadermiddlewares.useragent.UserAgentMiddleware',
 'scrapy.downloadermiddlewares.retry.RetryMiddleware',
 'scrapy.downloadermiddlewares.redirect.MetaRefreshMiddleware',
 'scrapy.downloadermiddlewares.httpcompression.HttpCompressionMiddleware',
 'scrapy.downloadermiddlewares.redirect.RedirectMiddleware',
 'scrapy.downloadermiddlewares.cookies.CookiesMiddleware',
 'scrapy.downloadermiddlewares.httpproxy.HttpProxyMiddleware',
 'scrapy.downloadermiddlewares.stats.DownloaderStats']
2021-09-24 20:12:09 [scrapy.middleware] INFO: Enabled spider middlewares:
['scrapy.spidermiddlewares.httperror.HttpErrorMiddleware',
 'scrapy.spidermiddlewares.offsite.OffsiteMiddleware',
 'scrapy.spidermiddlewares.referer.RefererMiddleware',
 'scrapy.spidermiddlewares.urllength.UrlLengthMiddleware',
 'scrapy.spidermiddlewares.depth.DepthMiddleware']
2021-09-24 20:12:09 [scrapy.middleware] INFO: Enabled item pipelines:
[]
2021-09-24 20:12:09 [scrapy.extensions.telnet] INFO: Telnet console listening on 127.0.0.1:6023
2021-09-24 20:12:09 [scrapy.core.engine] INFO: Spider opened
2021-09-24 20:12:11 [scrapy.core.engine] DEBUG: Crawled (404) <GET http://quotes.toscrape.com/robots.txt> (referer: None)
2021-09-24 20:12:11 [scrapy.downloadermiddlewares.redirect] DEBUG: Redirecting (308) to <GET http://quotes.toscrape.com/page/1/> from <GET http://quotes.toscrape.com/page/1>
2021-09-24 20:12:12 [scrapy.core.engine] DEBUG: Crawled (200) <GET http://quotes.toscrape.com/page/1/> (referer: None)
[s] Available Scrapy objects:
[s]   scrapy     scrapy module (contains scrapy.Request, scrapy.Selector, etc)
[s]   crawler    <scrapy.crawler.Crawler object at 0x7f6a10f85040>
[s]   item       {}
[s]   request    <GET http://quotes.toscrape.com/page/1>
[s]   response   <200 http://quotes.toscrape.com/page/1/>
[s]   settings   <scrapy.settings.Settings object at 0x7f6a11001c40>
[s]   spider     <DefaultSpider 'default' at 0x7f6a10c91700>
[s] Useful shortcuts:
[s]   fetch(url[, redirect=True]) Fetch URL and update local objects (by default, redirects are followed)
[s]   fetch(req)                  Fetch a scrapy.Request and update local objects 
[s]   shelp()           Shell help (print this help)
[s]   view(response)    View response in a browser
>>> response.css('title')
[<Selector xpath='descendant-or-self::title' data='<title>Quotes to Scrape</title>'>]
>>> response.css('title::text')
[<Selector xpath='descendant-or-self::title/text()' data='Quotes to Scrape'>]
>>> response.css('title::text').get()
'Quotes to Scrape'
>>> response.css('title::text').getall()
['Quotes to Scrape']


```
## Create file

`scrapy crawl quotes -o quotes.json`