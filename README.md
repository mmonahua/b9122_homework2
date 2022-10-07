# b9122_homework2
Author: Yimeng Hua

The repository contains two files for web crawling homework.

webcrawler: the sample we used in class

WebCrawl_covid: Crawl pages whose seed url is the press releases page of the Federal Reserve System:
https://www.federalreserve.gov/newsevents/pressreleases.htm and collect pages that contain the
word “covid” found within the page. The goal is to collect at least 10 such urls. At the end of the
crawling the code should output the urls of the webpages found to contain the word “covid”. When
checking whether the word is present on the webpage you should consider lower- and upper-case
word versions (Covid, COVID, covid). One way to do this is to lowercase the webpage text prior
to doing word matching.

WebCrawl_charges: Crawl pages whose seed url is the press releases page of the Securities and Exchange Commission: https://www.sec.gov/news/pressreleases and collect urls of press releases that contain the word “charges”. The code should output the first 20 such links that it finds. For each link output the url and the text. Similar to the previous task, when checking for the presence of the word “charges”
you should consider lower- and upper-case versions.
