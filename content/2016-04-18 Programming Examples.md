Title: Dev examples
Subtitle: A list of programming activities I recently performed.
Slug: cv-programming
Date: 2016-04-18
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

* it is implemented in `Python`, compatible with both `2.7` and `3.5`
* uses a console interface (I discovered [docopt](http://docopt.org) and instantly fell in love),
* applies `OOP`: the abstract market and inheriting implementations; which allows to easily shuffle the markets,
* communicates with markets' `APIs`,
* and scrapes web data from exchanges not providing any APIs,
* it (naturally) uses `git` as an SCM,
* from which updates are being deployed to a `Raspberry PI`,
* which sits at my home under the TV set and every few seconds collects data from all tracked markets,
* and analyses market changes,
* and logs the changes in a format ready to be consumed my `Tableau` dashboards for visual analysis,
* and automatically reacts (or may react) to appearing opportunities with simultaneous transactions.


Twitter Thought Leaders
-----------------------

#### tl;dr

The goal was to define a list of the top thought leaders in the blockchain community.
It was done by analysing the network of Twitter accounts of the starting list of leaders
and by following their relationships to discover additional ones. Then they were ranked by
the number of followers from the list.

#### In detail

The goal was to define a list of the top thought leaders in the blockchain space.

We had a starting list of candidates - a short list of authorities recognized by the community.

Since extensive use of Twitter is a very common thing among these people, I decided to go this way.

The idea was the following: if recognized leaders follow a twitter user, he/she is likely another leader in this space.

I used Twitter's API to calculate numbers of followers and who is following who within the shortlist.
Then we were adding new users iteratively.
After a few iterations we had a long list of potential leaders
and then we calculated the rank of top leaders by their popularity within the community.

In the end we proved ourselves that our initial list was quite comprehensive,
but we also found a few new interesting people who we added to the top list.

Blockchain was just a focus topic, but this may be applied to finding thought leaders in any community.

Another advantage is you can rerun this software cyclically to adjust the list as the network changes.


#### Tech details

* Keywords: `Python`, `Tweepy`, `Twitter API`, `rest`, `json`
* We used a `cli` interface and then `ipython notebooks` for the analysis.


Crunchbase Scraper
------------------

A small application I made to save time on gathering fintech companies' details and lists of their investors.
It takes a list of companies' names and used Crunchbase's API to collect data in CSV for further analysis.

Tech details:

* Keywords: `Ruby`, `Sinatra`, `Bootstrap`, `Crunchbase API`, `rest`, `json`
* Implemented both `web` and `cli` interfaces


Reporting data transformation
-----------------------------

Python scripts for cleaning, transforming and merging data in monthly reporting processes that were performed manually before.

`Jupyter notebooks` were used to combine scripts with the process documentation.
