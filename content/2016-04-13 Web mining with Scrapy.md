Title: Web mining with Scrapy
Subtitle: Exploring capabilities of the most popular crawling tool <br/>(work in progress...)
Category: Web mining
Tags: scrapy, web mining, crawling, python
Date: 2016-04-13



There was [a recent Talk Python To Me podcast with the founder of Scrapy](https://talkpython.fm/episodes/show/50/web-scraping-at-scale-with-scrapy-and-scrapinghub), Pablo Hoffman.
What shocked me most was how robust the solution already is. Even Michael, the podcast host, was surprised when asking
how big is the company got the answer: "At the moment we are 130 working fully which to me is pretty big, but of course, not huge."
130 people working for a web scraping company!? There must be much more behind it than I originally thought.

![Scrapy Logo](images/scrapylogo.png)

I admit so far I've been using the simplest solutions available: `requests` and `beautiful soup`.
But more and more I need a more comprehensive tool for gathering big amounts of data.
Therefore I decided to learn more about the tool.

What worked for me
------------------

Installing scrapy works smoothly for python `2.7`:

```
mkvirtualenv scrapy -p /usr/bin/python2.7  # important, always isolate your projects
pip install scrapy
```

However it still generates issues with version `3.5`.

### XPath and Chrome DevTools

Scraping a single information from a website is probably the simplest usage scenario for Scrapy.
Chrome DevTools (the developers console built in the Chrome browser) has a great feature that helps with targeting elements that we
want to scrape.

To use it:

* Right-click on an element you want to scrape.
* Click `Inspect`
* In the source code that has just appeared, right-click the highlighted part.
* Click `Copy` then `Copy Xpath`
* Then you can test the copied path:
  * Click the `Console` tab
  * Type `$x('')` and copy the path between apostrophes, i.e.: `$x('/html/body/div[2]/h3')`
  * It will return a list of one or more elements that match the given criteria.

### XPath and Scrapy Shell

You can achieve the same with the scrapy shell.

Example:

`scrapy shell http://www.computon.pl`

This will open the given web page and you can start extracting information you need.

Examples:

`response.xpath('/html').extract()`
`response.xpath('//a/text()').extract()`

##(To Be Continued....)