Title: Me As A Developer
Date: 2016-04-18
Subtitle: A list of programming activities I recently performed.
Slug: testing-pelican-ipynb
Category: CV
Tags: cv, python, programming
Author: Dominik Piekarczyk

BCCB - financial arbitrage
-------------------------

This is my private project I was developing as a hobby in the last few months. It implements
[a financial arbitrage](https://en.wikipedia.org/wiki/Arbitrage) (which is the simultaneous purchase and sale of an
asset in order to profit from a difference in the price).

I will *not* reveal the business logic behind it, but there are several fiat and crypto-currency exchanges engaged.
With my research of the markets and understanding how blockchain-based currencies work, I was able to prove possible
profitability at a level reaching 2-3% in a single cycle with a near-to-zero risk.

![BCCB](images/bccb-part.png)

Technical details worth highlighting:

* it is implemented in Python, compatible with both `2.7.10` and `3.5.1`
* uses a console interface,
* applies OOP: the abstract market and inheriting implementations; which allows to easily shuffle the markets,
* communicates with markets' APIs,
* and scrapes web data from exchanges not providing any APIs,
* it (naturally) uses git as a SCM,
* from which updates are being deployed to a Raspberry PI,
* which sits at my home under the TV set and every few seconds collects data from all tracked markets,
* and analyses market changes,
* and logs the changes in a format ready to be consumed my Tableau dashboards for visual analysis,
* and automatically reacts (or may react) to appearing opportunities with simultaneous transactions.


Twitter Thought Leaders
-----------------------

I was asked to prepare a list of top thought leaders in the blockchain space. We had a starting list of candidates -
people active in this space and well known in the community. But we wanted to make sure we're not missing anybody
important.

The idea was to use Twitter and its API to find out who is following who. Itratively e
By doing this we could

In effect we got a list that su

Crunchbase Scraper
------------------

A small application I made to save time on gathering fintech companies' details and lists of their investors.
It takes a list of companies' names and used Crunchbase's API to collect data in CSV for further analysis.

Tech details:

* Keywords: `Ruby`, `Sinatra`, `Bootstrap`, `Crunchbase API`, `rest`, `json`
* Implemented both `web` and `cli` interfaces


